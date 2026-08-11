---
name: renewal-strategist
description: >-
  Designs customer renewal strategies with timeline-based outreach sequences, expansion opportunity identification, and QBR (Quarterly Business Review) preparation frameworks. Use when managing SaaS renewals, preparing customer QBRs, or building expansion revenue playbooks.
---

# Renewal Strategist

A renewal handled reactively — reaching out only when the contract is about to lapse — is already behind. Good renewal strategy starts well before the renewal date, uses the account's actual usage/relationship signal to shape the approach, and treats renewal as a checkpoint to deepen the relationship, not just a transaction to close.

## Workflow

1. **Start the renewal timeline early.** For most B2B contexts, the renewal conversation should begin 60-90 days out (longer for larger/more complex accounts), giving time to address any risk signals and build an expansion case rather than scrambling at the deadline.
2. **Assess account health before deciding the approach**: usage trends (growing, flat, declining), engagement with the product/team (active champion still there? turned over?), support ticket sentiment, and stated satisfaction from any recent check-ins. This determines whether the renewal conversation should lead with expansion, address risk, or both.
3. **For healthy, growing accounts** — lead with expansion. Identify where usage patterns suggest a natural upsell (approaching a plan limit, using a workaround for a feature in a higher tier, added users/teams beyond the current plan's assumption) and frame the renewal conversation around growing with them, not just renewing at the same terms.
4. **For at-risk accounts** — address the risk directly before any expansion conversation, and don't paper over a real problem with a renewal-time discount offer without first understanding what's actually driving the risk (see `churn-analyst` skill for root-cause analysis if the issue isn't clear). A renewal secured by discount alone, without addressing the underlying dissatisfaction, often just delays the churn to the next cycle.
5. **Identify the actual decision-maker and any champion turnover** — a renewal at risk because the original champion left the company needs a different approach (re-establishing value with new stakeholders) than one at risk due to a product gap.
6. **Position multi-year or expanded commitments as a genuine value exchange**, not just a sales tactic — e.g. better pricing or added support tier in exchange for a longer term should reflect real mutual benefit, not just locking in revenue.

## What NOT to do

- Don't default to a discount as the renewal lever without first diagnosing whether price is actually the issue — same caution as with churn interventions generally.
- Don't treat every renewal as an expansion opportunity regardless of account health — pushing upsell on an already-at-risk account before addressing their actual concern usually accelerates churn rather than preventing it.

## Output format

```markdown
## Renewal strategy: <account>

**Account health signal:** [growing / stable / at-risk, with evidence]

**Recommended approach:** [expansion-led / risk-mitigation-led / both]

**Specific opportunity or risk identified:** [tied to actual usage/relationship evidence]

**Suggested conversation framing:** [key points to lead with]
```

## Verification & Quality Checklist
- [ ] Code compiles cleanly and passes all automated tests and typechecks without warnings.
- [ ] Edge cases, boundary conditions, and error states handled explicitly.
- [ ] No hardcoded secrets, test credentials, or insecure defaults introduced.
- [ ] Performance and resource utilization verified against baseline constraints.
