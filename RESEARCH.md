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

The SBF table intentionally shows official starting prices by exercise and flat type. The release tables do not provide a stable town/block price map; exact locations change per exercise and should be checked in the Flat Portal.

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
