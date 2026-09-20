# BTO Calculator research notes

Last updated: 20 September 2026

This file records the product decisions and source assumptions behind the calculator. Re-check official pages before changing values: HDB, CPF Board, and IRAS rules can change.

## Loan and budget assumptions

- LTV is user-configurable with a slider from 0% to 75%; the legal-mode default is 75%. Loan = flat price × selected LTV. Down payment = flat price × (1 − selected LTV).
- The calculator labels 75% as the current legal HDB housing-loan ceiling. The HFE letter is the authority for each household’s actual loan quantum; age, lease, income, and other debts can reduce it.
- HDB concessionary interest rate: 2.6% annually in the current source period, described as 0.1% above CPF OA interest.
- MSR check: 30% of gross monthly household income, stress-tested at 3.0% over no more than 25 years.
- Buyer’s Stamp Duty uses the residential tier schedule in the calculator and should be checked against IRAS before relying on an estimate.

Primary loan reference: [MND written answer on HDB loan considerations and quantums](https://www.mnd.gov.sg/newsroom/speeches/view/written-answer-by-ministry-of-national-development-on-hdb-s-considerations-for-housing-loan-applications-and-loan-quantums).

## CPF and grant assumptions

- CPF contributions: 37% of household income (20% employee + 17% employer) for members aged 55 and below.
- OA allocation used for the runway: 62.17% for the first 10 years, then 56.77% from year 11 onward.
- The 1Y/2Y/3Y/4Y/5Y cards add the early OA inflow × months to the current combined OA balance, then show the remaining cash needed at purchase.
- EHG bands are the first-timer household table effective 20 August 2024. Actual eligibility and grant amount come from the HFE letter.

## Official launch and SBF sources

- [HDB February 2024 BTO and SBF release](https://www.hdb.gov.sg/hdb-pulse/news/2024/hdb-launches-5714-flats-in-feb-2024-bto-and-sbf-exercises)
- [HDB February 2025 BTO and SBF release](https://www.hdb.gov.sg/hdb-pulse/news/2025/hdb-launches-10622-flats-in-february-2025-bto-and-sbf-exercises)
- [HDB February 2026 BTO and SBF release](https://www.hdb.gov.sg/hdb-pulse/news/2026/hdb-launches-9012-flats-in-february-2026-bto-and-sbf-exercises)
- [HDB June 2026 BTO release](https://www.hdb.gov.sg/hdb-pulse/news/2026/hdb-launches-6952-flats-across-7-projects-in-june-2026-bto-sales-exercise)
- [HDB Flat Portal](https://homes.hdb.gov.sg/home/landing) is the live source for current listings, exact SBF town/block, remaining lease, and availability.

The SBF explorer intentionally uses a dated February 2026 town-level snapshot rather than treating exercise-wide price ranges as a location guide. HDB's release confirms 4,320 SBF units and the official islandwide starting-price table; the preserved historical listing used for individual town rows is [99.co's February 2026 SBF table](https://www.99.co/singapore/insider/sale-of-balance-flats-hdb/), which attributes its listing to HDB. It is not live inventory.

### SBF, HFE and EHG

- SBF does **not** use a separate EHG or HDB-loan rule from BTO. HDB says the HFE letter tells a buyer their eligibility to buy a new or resale flat, CPF housing grants, and HDB housing loan, including the respective grant and loan amounts. A valid HFE letter is required to apply in an SBF sales exercise.
- HDB's “after EHG” launch-table prices are illustrative examples based on the maximum relevant grant, not an entitlement for every SBF buyer or a town-specific discount. The UI therefore calculates an explicitly labelled estimate from the calculator's income input and directs users to their HFE for the actual result.
- The meaningful SBF difference is the specific stock. A balance unit can be completed, still under construction, or have a remaining lease. HDB directs buyers to its Flat Portal for the remaining lease of each block; a shorter lease can affect CPF use and the loan quantum.
- HDB's new-flat process requires buyers to sign the Agreement for Lease within nine months after booking. HDB says a completed flat can be signed for and have its keys collected within that nine-month period.

Primary references: [HDB February 2026 release](https://www.hdb.gov.sg/hdb-pulse/news/2026/hdb-launches-9012-flats-in-february-2026-bto-and-sbf-exercises), [HDB application process](https://www.hdb.gov.sg/buying-a-flat/bto-sbf-and-open-booking-of-flats/process-for-buying-a-new-flat/application), [HDB key collection](https://www.hdb.gov.sg/buying-a-flat/bto-sbf-and-open-booking-of-flats/process-for-buying-a-new-flat/key-collection), and [HDB Flat Portal](https://homes.hdb.gov.sg/home/landing).

## Classification glossary

- **Standard**: the baseline new-flat classification.
- **Plus**: additional subsidies and tighter resale conditions.
- **Prime**: the most favourable-location classification, with the strongest restrictions.
- **PLH**: Prime Location Public Housing, the earlier model name used for central-location projects such as Tanglin Halt. Historical PLH rows are shown as Prime / PLH for filtering.

## UX decisions

- Sale-mode cards link to the HDB Flat Portal rather than stale deep links.
- FPPS and FCS notes link to HDB’s [priority schemes page](https://www.hdb.gov.sg/buying-a-flat/bto-sbf-and-open-booking-of-flats/process-for-buying-a-new-flat/application/priority-schemes).
- HDB eAlerts link to the [official subscription page](https://services2.hdb.gov.sg/webapp/BF08CESS/Subscription.jsp).
- Renovation is shown as a clearly labelled estimate (`S$20,000–60,000`), not an HDB-set fee.
