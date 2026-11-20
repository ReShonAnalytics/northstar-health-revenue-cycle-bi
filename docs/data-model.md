# Data Model & Architecture

## Model Purpose

The Northstar semantic model supports executive, claims, operational, and financial analysis from one governed analytical structure.

## Primary Tables

| Table | Role |
|---|---|
| Patients | Patient dimension |
| Departments | Department dimension |
| Providers | Provider dimension |
| Encounters | Patient encounter activity |
| Claims | Claim-level financial activity |
| Claim Transactions | Payment and transaction activity |
| Payers | Payer dimension |
| Denial Reasons | Denial classification |
| Date | Shared date dimension |
| Aging Buckets | A/R aging structure |
| KPI Measures | Centralized business measures |

## Relationship Design

Primary analytical relationships use one-to-many patterns with single-direction filtering where appropriate:

- Patients[PatientID] → Encounters[PatientID]
- Departments[DepartmentID] → Encounters[DepartmentID]
- Providers[ProviderID] → Encounters[ProviderID]
- Encounters[EncounterID] → Claims[EncounterID]
- Payers[PayerID] → Claims[PayerID]
- Denial Reasons[DenialReasonID] → Claims[DenialReasonID]
- Claims[ClaimID] → Claim Transactions[ClaimID]
- Date[Date] → Claims[SubmitDate]

Alternate date roles are supported with inactive relationships for events such as payment date and encounter date.

## Design Rationale

The model keeps descriptive dimensions separate from transactional facts so filters behave predictably across the report. A dedicated KPI Measures table centralizes business logic, while the Date dimension supports consistent time analysis across claims and encounters.
