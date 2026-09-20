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
- Make Budget the first substantive section after the hero. The background material is collapsed by default behind the centred divider-toggle labelled `Some background information on home purchase for the normie` and exposes a plus/minus state.
- The collapsed background group contains Modes of sale, Standard/Plus/Prime, Exercise timeline, Staying on top of it, and a short plain-English Loans and HFE + EHG explainer. HFE must be expanded as HDB Flat Eligibility and EHG as Enhanced CPF Housing Grant.

## SBF price explorer

- The primary SBF question is: **what did a flat of this type start from in this town?** The explorer therefore prioritises a dated, town-level historic snapshot over an islandwide aggregate price table.
- The current reference is February 2026, the latest SBF exercise for which we captured town-level listings. The table must include a town/estate column, flat type, classification where published, and the historical starting price. It is filterable by town and flat type, searchable, sortable, resettable, and shows a matching-row count.
- Use the official HDB launch release for the exercise-level count and price context. If detailed historical town rows rely on a preserved secondary record, identify it as such and link it. Do not present those rows as a live HDB inventory.
- EHG is **not** an SBF or town-specific discount. HDB determines a household's actual eligibility, CPF housing grant amount and HDB loan amount through its HFE (HDB Flat Eligibility) letter, for both BTO and SBF. Static “after EHG” release examples must not be implied to apply to every reader.
- The explorer may show “after your estimated EHG” only as a calculator scenario based on the income input, with a prominent note that the HFE letter controls the actual grant, loan and eligibility.
- Explain that SBF financing is broadly the same as BTO: a valid HFE is required before applying, and the chosen HDB/FI loan rules apply. State the material SBF difference: older or completed balance units can have a shorter remaining lease, which can reduce CPF use or loan amount; exact lease and stock are checked in the Flat Portal.
- HDB's public process calls for signing the Agreement for Lease within nine months of booking. A completed SBF flat can reach key collection within that window. Keep this timing separate from a BTO construction estimate.
- Historical town data must never be used to predict the next SBF exercise. Exact current block, unit availability, remaining lease, price, completion stage, application rates and ethnic quota must be checked in the HDB Flat Portal.
