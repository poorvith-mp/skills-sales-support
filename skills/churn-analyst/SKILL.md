---
name: churn-analyst
description: >-
  Analyzes customer churn patterns, identifies at-risk accounts through behavioral signals, and designs proactive retention interventions with health scoring models. Use when building churn prediction models, analyzing retention cohorts, or designing proactive save campaigns.
---

# Churn Analyst

Generic retention tactics (discount offers, "we miss you" emails) underperform because they treat all churn as the same problem. Real churn analysis segments by *why* customers left, since the fix for "never onboarded successfully" is completely different from "found a cheaper competitor" or "outgrew the product."

## Workflow

1. **Get the data**: churn events with timestamps, and ideally account attributes (plan tier, tenure, usage/engagement metrics, support ticket history) alongside them. Read attached data directly rather than asking the user to describe it.
2. **Segment churn by tenure first.** Early churn (within the first 30-90 days, roughly) almost always indicates an onboarding/activation problem — the customer never reached the point of experiencing real value. Late churn (established, engaged accounts leaving) indicates a different problem — competitive pressure, changing needs, or a specific negative experience. Don't propose the same fix for both.
3. **Look for leading indicators before the churn event itself** — declining usage/login frequency, a drop in a key engagement metric, a support ticket that went unresolved, a missed renewal conversation. These are what make churn *predictable* rather than only explainable after the fact, and they're what a retention intervention should actually trigger on.
4. **Correlate churn rate against account attributes** — plan tier, acquisition channel, company size/segment — to find which sub-populations churn at meaningfully different rates. A blended overall churn rate often hides a specific segment driving most of the problem.
5. **Distinguish voluntary from involuntary churn** (e.g. failed payment/card expiration vs. an active decision to cancel) — involuntary churn has a completely different, often much simpler fix (better payment retry logic, proactive card-expiration outreach) than voluntary churn does, and conflating the two understates how fixable a chunk of "churn" actually is.
6. **Propose interventions tied to the specific driver found**, not a generic playbook — e.g. if early churn correlates with never completing a specific onboarding step, the intervention is fixing that step or adding a nudge at that point, not a blanket "improve onboarding" recommendation.

## Anti-Patterns & Constraints

- Don't recommend a discount/win-back offer as the default fix without first identifying whether price was actually the churn driver — offering a discount to someone who left because the product didn't fit their need doesn't address anything and trains customers to churn strategically for discounts.
- Don't report a single blended churn rate as the whole finding — always segment, since the aggregate number usually obscures the more useful and actionable pattern.
- Don't manufacture a root cause the data doesn't support — if the data doesn't clearly point to a driver, say so and recommend what additional data (e.g. exit surveys, a support ticket audit) would help isolate it.

## Output format

```markdown
## Churn analysis: <period>

**Overall churn rate:** [with voluntary/involuntary split if determinable]

**Segments found:**
| Segment | Churn rate | Likely driver | Evidence |

**Leading indicators identified:** [what predicts churn before it happens, if found]

**Recommended interventions:** [tied specifically to the drivers above, ranked by likely impact]
```

## Verification & Quality Checklist

- [ ] Every input figure traced to a named source with an as-of date.
- [ ] Arithmetic reconciles: components tie to totals, periods tie to the annual figure.
- [ ] Each assumption stated explicitly with a plausible range, not a single point.
- [ ] Sensitivity shown on the three drivers with the largest effect on the result.
- [ ] Units, currency, and time period labelled on every figure presented.
