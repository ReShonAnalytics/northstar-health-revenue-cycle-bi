# Governance & Data Quality

Northstar includes a governance layer in addition to dashboard design.

## Governance Areas

- identifier completeness
- referential integrity
- payer validation
- claim-status requirements
- allowed amount versus charge validation
- denial-reason completeness
- payment-date requirements
- outstanding-balance controls
- claim transaction validation
- data refresh expectations

## Data Quality Approach

Controlled missing values and exceptions were retained where useful for validation. The goal was not to make the source data artificially perfect, but to model how reporting logic should identify and handle quality issues.

## Privacy

The project uses synthetic data only. No real patient records, PHI, or confidential healthcare information are included.
