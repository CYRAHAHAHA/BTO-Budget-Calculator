# Product decisions

Last reviewed: 20 September 2026

This file is the source of truth for durable product choices. Update it in the same pull request or commit as any change that alters one of these decisions.

## Calculator rules

### HDB loan-to-value (LTV)

- The calculator models an **HDB concessionary housing loan**, not a financial-institution loan.
- For flat applications from the October 2024 sales exercise onwards, the applicable HDB housing-loan LTV ceiling is **75%**, not 80%. The slider must not exceed 75% and its legal-mode default must be 75%.
- The actual allowable loan can be below 75% because HDB also applies the HFE loan quantum, the Mortgage Servicing Ratio, age and remaining-lease rules. For a lease that does not cover the youngest buyer to age 95, the cap is pro-rated from 75%.
- A previous request proposed an 80% default. **Do not display 80% as the currently legal HDB maximum.** If an 80% scenario is ever added, it must be clearly labelled as a historical/pre-August-2024 comparison and must not be the legal HDB default.
- Primary sources: [HDB housing loan eligibility](https://www.hdb.gov.sg/buying-a-flat/flat-grant-and-loan-eligibility/housing-loan/housing-loan-from-hdb) and [HDB's August 2024 LTV announcement](https://www.hdb.gov.sg/hdb-pulse/news/2024/measures-to-cool-the-hdb-resale-market-and-provide-more-support-for-first-time-home-buyers).

## Interface and content decisions

- Keep `BTO-Budget-Calculator` on one line.
- Keep the subtitle `Four ways to get a flat, one financing decision, and a live number for what it costs you.` on one line at desktop widths.
- Centre the four "Modes of sale" cards as a group.
- External links use high-contrast white, an underline, and an external-link indicator; do not use low-contrast dark-blue links on the dark theme.
- The Budget section does not include a `S$1,000+ Moving & basic furnishing buffer` cost item.

## SBF starting-price section

- Keep the price table filterable by exercise and flat type, searchable by area or flat type, and sortable by before/after-EHG starting price.
- Keep a reset control and a visible matching-row count.
- Show per-exercise context above the table: units offered, coverage, completed-unit share, and direct links to the official HDB release.
- Treat the price table as a starting-price comparison. Exact block, unit availability, remaining lease, and live application rates must be sourced from the HDB Flat Portal for the relevant exercise; do not infer them from starting prices.

