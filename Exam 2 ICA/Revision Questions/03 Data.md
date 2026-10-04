# Data — Revision Questions

Source: [[Aggregation of claim data]], [[Claim data at alternate limit]], [[Exposure Data]], [[Homogeneity and statistical reliability of data]], [[Reinsurance Analysis]], [[ULAE vs ALAE]], [[Validation]]

## Part A — Definitions and Recall

### A1. What is the main reason actuaries work with aggregated claim data rather than raw claim-level records?

> [!answer]- Answer
> - Aggregated data is less granular and voluminous than raw claim-level records, making it more practical for day-to-day analysis.

### A2. Define "calendar year" aggregation for claim and transaction data.

> [!answer]- Answer
> - Calendar year aggregates all transactions (paid losses, incurred losses, premiums) occurring in a given year, regardless of policy effective date or when events occurred.

### A3. Define "accident year" aggregation.

> [!answer]- Answer
> - Accident year aggregates all claims from accidents occurring in the same year, regardless of report date.

### A4. Define "policy (underwriting) year" aggregation.

> [!answer]- Answer
> - Policy (underwriting) year aggregates all claims associated with policies that are effective during the calendar year.

### A5. Define "report year" aggregation.

> [!answer]- Answer
> - Report year aggregates all claims reported in a year.

### A6. What is the formula given for calendar year reported claims in terms of case estimates and payments?

> [!answer]- Answer
> - CY reported claims = case estimate end of year - case estimate beginning of year + payment in year.

### A7. Define homogeneity and statistical reliability in the context of data grouping.

> [!answer]- Answer
> - Homogeneity: groups exhibit similar characteristics (reporting/settlement patterns, claim severity/frequency, relationship between claim-related expenses and indemnity, propensity for large claims).
> - Statistical reliability (credibility): sufficient volume of homogeneous claims in each group to produce statistically stable and meaningful results.

### A8. Distinguish between ALAE and ULAE, giving examples of each.

> [!answer]- Answer
> - ALAE (Allocated Loss Adjustment Expenses): expenses directly attributable to a specific claim (e.g., claim investigation, defense attorneys, medical evaluation, expert review, record copying).
> - ULAE (Unallocated Loss Adjustment Expenses): claim-related expenses of a general nature that cannot be allocated to a specific claim (e.g., salaries, administrative costs of claims department).

### A9. State the classical paid-to-paid formula for unpaid ULAE as presented.

> [!answer]- Answer
> - Unpaid ULAE = (ULAE ratio × IBNR) + (ULAE ratio × multiplier × case estimate).

### A10. What is the purpose of analyzing claims at an alternate limit?

> [!answer]- Answer
> - To reduce volatility caused by large losses.

## Part B — Explain, Compare, Advantages and Disadvantages

Source: [[Aggregation of claim data]], [[Exposure Data]], [[Homogeneity and statistical reliability of data]], [[Reinsurance Analysis]], [[ULAE vs ALAE]]

### B1. Compare calendar year, accident year, policy year, and report year across key uses and limitations.

> [!answer]- Answer
> - Calendar Year: groups by transaction date; used for accounting/financial reporting/operational monitoring; key limitation: misaligned with risk period, development patterns not meaningful.
> - Accident Year: groups by accident date; used for unpaid claim estimation and development triangles; key limitation: premium proxy (CY earned premium) introduces mismatch.
> - Policy (UW) Year: groups by policy effective date; used for pricing/ratemaking; key limitation: slow emergence, less timely for reserving.
> - Report Year: groups by report date; used for claims-made covers/claims-handling monitoring; key limitation: excludes IBNR.

### B2. Explain why accident year is generally preferred for unpaid claim estimation while policy year is preferred for pricing.

> [!answer]- Answer
> - Accident year balances timeliness and risk alignment (faster than policy year, aligns losses to period of risk) and is standard with CY earned premium for development/triangulation.
> - Policy year provides the most precise match of premium and claims for the covered policy cohort, making it best for pricing/ratemaking despite slow emergence.

### B3. Explain the trade-off between homogeneity and statistical reliability when subdividing data.

> [!answer]- Answer
> - Subdividing too much increases homogeneity but decreases statistical reliability (smaller sample sizes).
> - Keeping groups too broad increases reliability but sacrifices homogeneity.
> - Actuaries must balance these competing needs for ratemaking, reserving, and data analysis.

### B4. Contrast gross/net of reinsurance analysis approaches and when each is chosen.

> [!answer]- Answer
> - Separate direct/assumed/ceded (gross/ceded): advantages include understanding recoveries, detailed reinsurance term analysis, stress testing; disadvantages include complexity, sensitivity to data quality, recoveries may lag.
> - Gross and net basis (net = direct + assumed - ceded): advantages include direct estimation, alignment with IFRS-17; disadvantages include recoveries not modeled, requires net-to-gross ratio assumption.
> - Choices depend on reinsurance program, data segregation available, volume, impact of reinsurance, professional judgment, standards.

### B5. Explain the rationale for the multiplier in the classical paid-to-paid ULAE formula.

> [!answer]- Answer
> - A substantial amount of ULAE occurs when claims are opened; already-reported claims should have lower unpaid ULAE than unreported claims.
> - The multiplier (typically 0.5) reflects this timing difference between reported (open case) and unreported (pure IBNR) claims.

### B6. Outline key weaknesses of the classical paid-to-paid ULAE method and how Kittel/Mango-Allen/count-based approaches address them.

> [!answer]- Answer
> - Classical weaknesses: biased/overstates in exposure growth (ULAE reacts faster than paid claims) and inflation (inflation impacts ULAE more); 0.5 multiplier/static assumptions may be inaccurate; formula can be refined to include development on case estimates.
> - Kittel: considers both reported and paid claims (helps with exposure growth) but same multiplier/inflation issues persist.
> - Mango-Allen: useful for long-tail, changing exposure volume, large-claim distortion, low variable volume, or limited credible paid/reported; assumes payment/reporting patterns and estimated ultimates are accurate.
> - Count-based: recognizes ULAE varies by transaction type/counts (not just claim amount), less sensitive to claim estimate fluctuations; weaknesses include lower estimates than classical, count categories not exclusive, open duration doesn't always predict ULAE, difficulty determining open/closed during year.

## Part C — Application and Calculation

Source: [[Aggregation of claim data]], [[Claim data at alternate limit]], [[Exposure Data]], [[ULAE vs ALAE]], [[Validation]], [[Homogeneity and statistical reliability of data]]

### C1. Calendar year reported claims (numeric). For AY1, case estimate at beginning of year is $500k, case estimate at end of year is $800k, payments in year are $300k. Compute CY reported claims and state which aggregation the diagonal-difference refers to.

> [!answer]- Answer
> - CY reported claims = case estimate end of year - case estimate beginning of year + payment in year = $800k - $500k + $300k = $600k.
> - CY reported claims = difference in two diagonals of a claim triangle.

### C2. Claim development at alternate limit. Given ultimate claims at full limit of $1.8M (includes a $900k large loss), project/assess using an alternate limit of $250k: large loss capped at $250k gives $1.15M total, with an unadjusted alternative projection of $1.15M. If the large loss load (excess over limit) is $650k, compute the combined projection and explain treatment.

> [!answer]- Answer
> - Capped claims = $1.15M; add back large loss load = $650k → combined projection = $1.15M + $650k = $1.80M (restoring the effect of large losses).
> - Treatment: cap claims at alternate limit, project at limit, add back large loss load; document treatment of ALAE (included/excluded).

### C3. Exposure basis selection. A block has written premium in PY1 of $1.2M, unearned premium end of PY1 of $300k. Compute policy year earned premium for PY1. Also state when CY earned premium is used as a proxy.

> [!answer]- Answer
> - Policy year: EP_x = WP_x - UEP_x → EP_{PY1} = $1.2M - $300k = $900k.
> - CY earned premium is used as a proxy for accident year risk period (since AY earned premium for the risk period is not directly available when needed).

### C4. ULAE classical calculation. Given IBNR = $400k, case estimate = $600k, ULAE ratio = 8%, multiplier = 0.5. Compute unpaid ULAE using classical paid-to-paid.

> [!answer]- Answer
> - Unpaid ULAE = (ULAE ratio × IBNR) + (ULAE ratio × multiplier × case estimate) = (0.08 × $400k) + (0.08 × 0.5 × $600k) = $32k + $24k = $56k.

### C5. ULAE refined formula intuition. Using C4, suppose development on case estimates = $100k and IBNYR=$300k (so IBNR = IBNYR + IBNER). Show the more appropriate formula form and compute.

> [!answer]- Answer
> - More appropriate: Unpaid ULAE = (ULAE ratio × IBNYR) + (ULAE ratio × multiplier × (case estimate + development on case estimate)).
> - = (0.08 × $300k) + (0.08 × 0.5 × ($600k + $100k)) = $24k + $28k = $52k.

### C6. Validation checks. You have claim data for two periods: Period 1 paid claims $800k, case $200k; Period 2 paid $820k, case $190k, with total reported premiums up 2% and policy count up 5%. Identify which validation activities apply and a potential inconsistency.

> [!answer]- Answer
> - Validation activities: reconcile against audited financials/trial balances/records if available; test reasonableness against external/independent data; test internal consistency; compare with prior period.
> - Potential inconsistency: policy count up 5%, premiums up 2% (rate/average premium change), but reported claim volume (paid+case) relatively flat ($1.0M vs $1.01M) — warrants reasonableness/internal consistency check.

### C7. Homogeneity vs reliability trade-off numeric. A portfolio split into 4 homogeneous groups gives each ~100 claims (reliable? small). Combined into 1 broad group gives 400 claims. If splitting improves homogeneity score from 5/10 to 9/10 but reduces effective credibility measure from 8/10 to 6/10, explain the actuarial choice.

> [!answer]- Answer
> - Splitting: higher homogeneity (better reflects similar characteristics) but lower statistical reliability/credibility (smaller volume per group).
> - Combining: higher reliability but lower homogeneity.
> - Choice depends on use: pricing may favor more homogeneity if groups remain credibly sized; reserving may accept broader groups for stability — actuaries must balance per the specific context.

### C8. Reinsurance treatment. Given direct claims $500k, assumed $100k, ceded $150k, compute net claims. Also state whether gross triangles or net triangles better support reinsurance negotiation vs financial reporting.

> [!answer]- Answer
> - Net claims = direct + assumed - ceded = $500k + $100k - $150k = $450k.
> - Gross triangles support pricing and reinsurance negotiation; net triangles support reserve adequacy and financial reporting (and align with IFRS-17).

### C9. Exposure aggregation forms. For calendar year EP: WP_x + UEP(x-1) - UEP_x = $1.5M + $400k - $500k. Compute CY EP and contrast with PY EP form EP_x = WP_x - UEP_x.

> [!answer]- Answer
> - CY EP = $1.5M + $400k - $500k = $1.4M.
> - CY form adjusts for change in unearned premium (includes prior year UEP brought into earn, removes current UEP); PY form is simpler (written minus unearned for policies written in the year).

### C10. Count-based ULAE intuition. If 1 large $500k claim and 10 small $50k claims total same indemnity, count-based method would likely produce higher/lower relative ULAE than a pure ratio-to-indemnity approach? Justify.

> [!answer]- Answer
> - Count-based would typically produce higher relative ULAE than ratio-to-indemnity, because ULAE does not depend only on claim amount (handling 10 claims involves more transactions/activities than handling 1 claim of same total). Ratio-to-indemnity would allocate same ULAE regardless of claim count.

## Part D — Exam-Style Questions

Source: [[Aggregation of claim data]], [[Exposure Data]], [[Homogeneity and statistical reliability of data]], [[Reinsurance Analysis]], [[ULAE vs ALAE]], [[Validation]], [[Claim data at alternate limit]]

### D1. Aggregation choice (essay). "For a rapidly growing commercial auto book, which aggregation basis would you prefer for reserving and which for ratemaking? Justify your choices, noting the key tradeoffs."

> [!answer]- Answer
> - Reserving: prefer Accident Year. It aligns losses with the period of risk and is timely (faster than Policy Year), making development triangles meaningful. The key tradeoff is using CY earned premium as a proxy for AY exposure.
> - Ratemaking: prefer Policy (Underwriting) Year. It provides the most precise match of premium and claims for the covered policy cohort, which is essential for pricing adequacy. Tradeoff: slow emergence (extends across two calendar years), making it less practical for timely reserving.
> - Note CY is appropriate for accounting/reporting but not for building development patterns; RY only relevant for claims-made covers.

### D2. Homogeneity vs statistical reliability (essay). "You are asked to split a small book into more homogeneous groups. Explain the tradeoff, risks of over-splitting, and how you might decide when to stop subdividing."

> [!answer]- Answer
> - Tradeoff: increasing homogeneity improves similarity (reporting/settlement, severity/frequency, expense relationships, large claim propensity) but reduces statistical reliability/credibility due to smaller sample sizes; broadening increases reliability but sacrifices homogeneity.
> - Risks of over-splitting: unstable estimates, excessive parameter uncertainty, spurious differences, difficulty in pattern selection, and impractical implementation.
> - Decision criteria: assess credibility per group (volume), stability of development patterns/severity/frequency over time, materiality, operational feasibility, and whether differences are statistically/actuarially significant; consider combining groups with similar characteristics when credibility is insufficient.

### D3. ULAE estimation (essay). "Compare classical paid-to-paid with Kittel and count-based approaches for ULAE. In a period of rapid exposure growth and rising inflation, which concerns arise and how might they be addressed?"

> [!answer]- Answer
> - Classical paid-to-paid: simple, widely used; unpaid ULAE = (ULAE ratio × IBNR) + (ULAE ratio × multiplier × case estimate); assumes proportionality, steady state, and that reported/unreported get multiplier treatment.
> - Kittel refinement: considers both reported and paid claims, helping address exposure growth distortion, but retains the 0.5 multiplier and doesn't fully resolve combined inflation/exposure effects.
> - Count-based: allocates ULAE by transaction counts/types, better reflects handling effort (not just amount), less sensitive to estimate fluctuations; data-intensive, count categories can be non-exclusive, duration-open doesn't always predict ULAE, can produce lower estimates.
> - Concerns in rapid growth + inflation: ULAE reacts faster than paid claims (growth overstates ratio), inflation impacts ULAE more than paid claims (overstates ratio), 0.5 multiplier may be inaccurate; address via refined formula including development on case estimates (IBNYR/IBNER split), consider Mango-Allen adjustments (long-tail/changing volume/large claims), use count-based or hybrid approaches, and validate assumptions regularly.

### D4. Reinsurance and data (essay). "A ceded reinsurance program materially affects results. Explain when you would analyze gross/ceded separately vs gross/net, the data implications, and how reinsurance features can complicate triangle analysis."

> [!answer]- Answer
> - Gross/ceded separately (direct+assumed vs ceded): better for understanding recoveries, reinsurance term details, stress testing; more complex, data quality sensitive, recoveries may lag closed claims.
> - Gross/net (net = direct+assumed-ceded): better for direct estimation, reserve adequacy, financial reporting (IFRS-17); recoveries not modeled explicitly, requires net-to-gross ratio assumptions.
> - Data implications: need clear segregation (direct/assumed/ceded), consistency in treatment, volume considerations, and reliable recovery data.
> - Complicating features: pro-rata (quota share/surplus share) vs excess of loss/aggregate stop loss affect how layers attach; risk-attaching vs loss-occurring terms affect accounting/timing; treatment of LAE (included in retention/limit?), reinstatement provisions, and claim-sensitive premium features can all affect how triangles are constructed/interpreted.

### D5. Data quality and validation (essay). "Describe a comprehensive validation plan for claim and exposure data before reserving analysis. Include specific checks, alternate-limit considerations, and actions if inconsistencies arise."

> [!answer]- Answer
> - Reconciliation: compare to audited financial statements, trial balances, or other relevant records.
> - External reasonableness: test against external/independent data sources.
> - Internal consistency: cross-verify totals/subtotals, relationships (paid+case=reported, EP forms correct), consistency across aggregations.
> - Temporal comparison: compare with prior periods, look for unexplained shifts.
> - Specific considerations: verify exposure basis/forms (CY EP vs PY EP, WP/UEP), confirm aggregation basis matches analysis (AY with CY EP proxy), check ALAE treatment when using alternate limits, document large loss capping and large loss load.
> - Actions if inconsistencies: investigate source, quantify impact, adjust/cleanse data with documentation, apply judgment, consider sensitivity testing, and escalate material issues before relying on results.

## Part E — Quick Recall (Bonus)

Source: [[Aggregation of claim data]], [[Claim data at alternate limit]], [[Exposure Data]], [[Homogeneity and statistical reliability of data]], [[Reinsurance Analysis]], [[ULAE vs ALAE]], [[Validation]]

### E1. Which basis excludes IBNR by construction?

> [!answer]- Answer
> - Report Year.

### E2. Which basis is standard for pricing/ratemaking?

> [!answer]- Answer
> - Policy (Underwriting) Year.

### E3. Which basis is standard for reserving?

> [!answer]- Answer
> - Accident Year.

### E4. Which basis is standard for accounting/financial reporting?

> [!answer]- Answer
> - Calendar Year.

### E5. Give two advantages of earned exposures over earned premiums as exposure base.

> [!answer]- Answer
> - No adjustment required for rate changes (unlike earned premiums).
> - Sometimes more directly reflective of exposure units without premium-related distortions.

### E6. What is the purpose of large loss load when projecting at alternate limit?

> [!answer]- Answer
> - To add back the excess of large losses over the cap so the capped projection reflects the full loss cost impact.