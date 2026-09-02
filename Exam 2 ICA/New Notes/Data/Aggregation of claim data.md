## Why

- Actuaries mostly work with aggregated data — raw claim-level records are too granular and voluminous for day-to-day analysis.

## Types of Aggregation

Each basis groups losses differently, which changes how unpaid claims (IBNR) appear and which analytical questions the data can answer.

### Calendar Year

- **Definition:** Aggregate all transactions (paid losses, incurred losses, premiums) occurring in a given year, regardless of the effective date of the underlying policy or when the events giving rise to the claims occurred.
- **Usage:** Accounting, financial reporting, and other management purposes.
- **Advantages:**
    - Readily available from financial systems.
    - Useful for diagnosing operational/environmental changes.
- **Disadvantages:**
    - Poor indicator of pricing adequacy.
    - Misaligned with the risk period → development triangles on CY data are not meaningful for projecting ultimates.
- **Actuary Usage:** CY data is *not* appropriate for building development patterns, but it feeds reserving indirectly through loss ratios and volume measures (e.g., Bornhuetter–Ferguson, Cape Cod) and is the basis for monitoring reserve adequacy.

### Accident Year

- **Definition:** All claims from accidents occurring in the same year, regardless of report date (emphasis on losses).
- **Advantages:**
    - Faster availability than policy year.
    - Aligns losses with the period of risk.
- **Disadvantages:**
    - Earned premium for the accident-year risk period is not directly available when needed, so actuaries proxy it with **calendar-year earned premium** — a reasonable but imperfect match.
- **Actuary Usage:**
    - Most common aggregation pattern.
    - Typically used with CY earned premium to estimate unpaid claims via development triangles and loss ratio methods.
- **Actuarial Implication:** AY balances timeliness and risk alignment → preferred for unpaid claim estimation. AY losses = reported + IBNR + IBNER.

### Policy (Underwriting) Year Aggregation

- **Definition:** All claims associated with policies that are effective during the calendar year are combined (emphasis on exposure).
- **Advantages:** Precise match of premium and claims for the covered policy cohort.
- **Disadvantages:** Slow emergence — extends across two calendar years, as the last policies written in December generate claims well into the following year.
- **Actuary Usage:** Typically used with policy-year earned premium to estimate unpaid claims.
- **Actuarial Implication:** Best for pricing and ratemaking studies; less practical for timely reserving.

### Report Year Aggregation

- **Definition:** All claims reported in a year are aggregated together.
- **Advantages:** Limited outside claims-made coverage, but simplest basis to compile — no allocation of claims to accident years is required.
- **Disadvantages:** Does not capture IBNR by construction.
- **Actuary Usage:** Used with claims-made coverage, where the reporting period defines the covered risk.
- **Actuarial Implication:** Only useful when the reporting trigger defines coverage (e.g., claims-made liability).

## Comparison

| Basis | Groups by | Best used for | Key limitation |
|---|---|---|---|
| **Calendar Year** | Transaction date (when paid/incurred) | Accounting, financial reporting, operational monitoring | Misaligned with risk period; development patterns not meaningful |
| **Accident Year** | Accident date (when the loss occurred) | Unpaid claim estimation, development triangles | Premium proxy (CY earned premium) introduces mismatch |
| **Policy (UW) Year** | Policy effective date | Pricing and ratemaking | Slow emergence; not timely for reserving |
| **Report Year** | Report date (when the claim was reported) | Claims-made covers, claims-handling monitoring | Excludes IBNR |

> **Quick reference:** AY is the standard reserving basis; CY is the standard reporting basis; PY is the standard pricing basis; RY is the standard basis for claims-made covers.