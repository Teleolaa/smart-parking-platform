# Post Mortem: TSB Bank's 2018 IT Platform Migration

**Prepared by:** Omoteleola Oyebiyi | **Course:** CIS 4374 | **Date:** 11/05/2026

TSB moved about 5 million customers to a new banking platform in one weekend in April 2018, the platform failed immediately, and normal service took about eight months to return. Regulators later fined TSB £48.65m for poor migration planning, weak governance and inadequate control of its IT supplier.

## Timeline

| Date | Event |
|------|-------|
| Late April 2018 | TSB moves about 5 million customer records to the new Proteo4UK platform in a single weekend. The data moves, but the platform fails straight away. |
| April-December 2018 | Branch, phone, online and mobile banking are disrupted. TSB returns to normal operations in December 2018, about eight months later. |
| 19 November 2019 | TSB publishes the independent review by Slaughter and May. |
| 20 December 2022 | The FCA and PRA fine TSB £48.65m for operational resilience failings. |

## Impact

The failure hit customers, the bank's finances and its regulatory standing.

- **Customers:** All branches and a large share of TSB's 5.2 million customers were affected, including vulnerable customers. Customers had difficulty accessing services and contacting the bank.
- **Fraud:** Fraud attempts against TSB customers peaked at about 70 times the usual level during the disruption.
- **Redress:** TSB has paid £32.7m to customers who suffered detriment.
- **Fines:** £48.65m in total (FCA £29.75m, PRA £18.9m). That is after a 30% settlement discount; the full penalty would have been £69.5m.

## Root Causes

The independent review and the regulators both point to project management and governance, not a single bug.

- **Untested migration approach:** TSB chose a one-weekend "big bang" migration instead of a phased one. The review found it never weighed this choice against alternatives or assessed and planned for its risks.
- **Weak testing:** The review found a lack of robust testing of the new platform before cutover.
- **Weak supplier oversight:** The project involved over 70 suppliers and more than 1,400 people. The regulators found TSB did not manage the operational risks of outsourcing to a critical third-party supplier, and the review found the board did not understand how the platform supplier's experience differed from what the project needed.
- **Board understanding and governance:** The review found gaps in the board's understanding of the platform's scope and complexity. The board did not substantively discuss the migration approach, and neither the board nor the executive sought external advice. The regulators found project governance was not robust enough.
- **TSB's own account:** TSB disputes parts of the review. It points to a technical fault in two data centres that were specified to be identical but were configured differently, plus coding and capacity issues, made worse by high customer contact volumes. It accepts that planning and preparation could have been done differently.

## Lessons Learned

These are my reading of the findings above, mapped to project management topics from this course.

1. **Risk management:** A risk nobody assessed cannot be managed. TSB never compared a big-bang cutover with a phased one, so no one owned the choice or its fallback.
2. **Quality management:** Testing has to be a gate with written pass criteria, not a milestone that gets ticked off. Thin testing meant the first real test of the platform was live customers.
3. **Third-party management:** Outsourcing delivery does not outsource accountability. TSB needed to check that the supplier's experience matched what the project demanded.
4. **Governance and stakeholders:** Executives and the board must understand what they approve. Gaps in understanding, and no outside challenge, let a high-risk plan go through unquestioned.
5. **Customer impact planning:** Customers, including vulnerable ones, bore most of the harm. Support capacity and fraud monitoring should have been sized for the failure case, not the success case.

## Recommendations for Similar Projects

What a project manager should do differently on a large system migration:

- **Phase the cutover.** Migrate a small pilot group first (staff, then a small customer cohort), then move in waves, with a tested rollback plan at each step.
- **Set written go/no-go criteria.** Tie them to test results and have someone independent of the delivery team sign off before cutover.
- **Check supplier fit.** Assess the supplier's capability against the project's real needs, run joint end-to-end tests, and agree escalation paths in the contract.
- **Brief leadership in plain language.** Give the board a short risk summary at each gate and bring in outside review for decisions this large.
- **Plan for failure.** Size support and communications for the failure scenario, protect vulnerable customers first, and monitor for fraud from day one.

## Sources

- [Bank of England: TSB fined for operational resilience failings](https://www.bankofengland.co.uk/news/2022/december/tsb-fined-for-operational-resilience-failings) (fines, redress, timeline, regulators' findings)
- [ITPro: TSB's IT disaster pinned on 'big bang' approach to migration](https://itpro.com/business-strategy/digital-transformation/354155/tsbs-it-disaster-pinned-on-big-bang-approach-to) (Slaughter and May review findings, supplier and board gaps, fraud levels, TSB's response)
- [Slaughter and May: Independent review of TSB's 2018 migration](https://www.slaughterandmay.com/news/slaughter-and-may-s-independent-review-of-tsb-s-2018-migration-to-a-new-it-platform/) (review of the April 2018 migration, published 19 November 2019)

*The Lessons Learned and Recommendations sections are my own analysis, not findings from these sources.*
