# Professional Requirements — Revision Questions

## Part A — Definitions and Recall

Source: [[Actuarial Standards]], [[Credibility]], [[Data]], [[Documentation]], [[Expenses and Profit]], [[Rate Regulation]], [[Trend]]

### A1. What is the purpose of a Code of Professional Conduct (Specific Jurisdiction)?

> [!answer]- Answer
> - Identifies the professional and ethical standards that actuaries must follow.

### A2. What is the goal of Actuarial Standards of Practice (ASOPs/Specific Jurisdiction)?

> [!answer]- Answer
> - Promote greater consistency of approach between different situations to increase the confidence of clients and the public in actuarial work, without placing unnecessary constraints on professional judgment or creativity.

### A3. List three purposes of ASOPs.

> [!answer]- Answer
> - Ensure actuarial services are performed professionally and with due care.
> - Ensure results are relevant to user needs, presented clearly and understandably, and complete.
> - Ensure assumptions and methodologies are disclosed appropriately.

### A4. When do actuaries take credibility into account?

> [!answer]- Answer
> - Projecting ultimate claims.
> - Estimating unpaid claims.
> - Pricing products.

### A5. What makes data sufficient and reliable?

> [!answer]- Answer
> - Sufficient: includes appropriate information for the work.
> - Reliable: substantially accurate.

### A6. What is the standard for documentation completeness?

> [!answer]- Answer
> - Documentation is complete if another qualified actuary could redo the work and assess the judgments made.

### A7. What are the three rate regulation objectives stated in the notes?

> [!answer]- Answer
> - Maintain insurer solvency.
> - Protect insurance consumers.
> - Ensure availability of coverages.
> - Regulate insurance rates. (Also implied; at least three of these.)

### A8. Distinguish economic inflation from social inflation in the context of trend.

> [!answer]- Answer
> - Standards define trend considerations and differentiate economic inflation from social inflation.

### A9. What does "rates are not unfairly discriminatory" mean?

> [!answer]- Answer
> - Insurers cannot charge a price that does not reasonably reflect the expected cost for a customer.

### A10. How is profit defined in relation to cost of capital?

> [!answer]- Answer
> - Profit is equal to cost of capital if accepted by legislation.


## Part B — Explain, Compare, Advantages and Disadvantages

Source: [[Actuarial Standards]], [[Credibility]], [[Data]], [[Expenses and Profit]], [[Rate Regulation]], [[Trend]]

### B1. Explain how the "users and intended uses" of actuarial work shape ASOPs.

> [!answer]- Answer
> - Users and intended uses are crucial in shaping actuarial work.
> - This consideration helps ensure results are relevant to user needs, presented clearly and understandably, and complete.
> - It also guides appropriate disclosure of assumptions and methodologies.

### B2. Compare fixed and variable expenses and explain how they are treated in rate provisions.

> [!answer]- Answer
> - Expenses should be split between fixed and variable expenses.
> - Fixed expenses may need to be adjusted for trend.
> - Reinsurance costs may be included as expense provisions.

### B3. Explain the considerations for choosing the complement of credibility.

> [!answer]- Answer
> - The complement of credibility should be similar to the insurer's own experience.
> - Considerations include: volume of claims (number/amounts, premiums, exposures), number of years of claim data, stability/variability, presence of large/unusual claims, internal/external changes, age/relevance/reliability of the experience, age/relevance/reliability of data for the complement.

### B4. Explain why an actuary must be aware of changes in the insurer's environment.

> [!answer]- Answer
> - The actuary needs to be aware of operations and changes in operations.
> - They need to understand how those changes will affect the actuarial work.

### B5. Explain the trade-off between stability and responsiveness when selecting trend data.

> [!answer]- Answer
> - Stability favors looking at a longer period of time.
> - Responsiveness favors looking at the most recent experience.
> - The balance depends on line (short-tail: typically 4-5 years of exposure since ultimates more certain; long-tail: consider short- and long-tail indications, may not want most recent points due to high leverage).

### B6. Explain how deductible leveraging affects trend.

> [!answer]- Answer
> - If the deductible is stable and there is inflation, the deductible becomes less useful as it eliminates fewer claim dollars, creating deductible leveraging.

### B7. Compare linear vs exponential trend models and when linear may be less appropriate.

> [!answer]- Answer
> - Linear: trend increases/decreases by a constant amount (may not be appropriate for decreasing trends).
> - Exponential: constant rate of change.
> - Models should be compared using R-squared ($R^2$), F-statistics, or p-values.

### B8. Explain the three rate regulation criteria and their impacts.

> [!answer]- Answer
> - Adequate: sufficient for future claims and expenses; inadequacy threatens policyholders, public, and industry.
> - Not excessive: insurers should not earn excessive/unreasonable profits; insurance must remain affordable.
> - Not unfairly discriminatory: price must reasonably reflect expected cost; certain factors may be restricted by jurisdiction.


## Part C — Application and Calculation

Source: [[Credibility]], [[Trend]], [[Expenses and Profit]], [[Rate Regulation]], [[Data]]

### C1. Credibility-weighted estimate (two bases)

Given: Pure premium based on insurer's own experience = $320$ per exposure. Complement (industry/class) pure premium = $280$ per exposure. Assigned credibility $Z = 0.60$.

Compute the credibility-weighted pure premium.

> [!answer]- Answer
> - Credibility-weighted = $Z \times (\text{Own}) + (1-Z) \times (\text{Complement}) = 0.60 \times 320 + 0.40 \times 280 = 192 + 112 = 304$ per exposure.

### C2. Credibility with different weights

Given: Unpaid claims estimate from own data = $4,500,000$. Complement estimate = $5,000,000$. Credibility $Z = 0.75$.

Compute the credibility-weighted unpaid claims estimate.

> [!answer]- Answer
> - $0.75 \times 4,500,000 + 0.25 \times 5,000,000 = 3,375,000 + 1,250,000 = 4,625,000$.

### C3. Linear trend projection

Given: Historical average claim cost (years 1-4): Year 1=$250$, Year 2=$265$, Year 3=$280$, Year 4=$295$ (increasing by $15$ per year). Project average claim cost for Year 6 assuming linear trend continues.

> [!answer]- Answer
> - Annual linear increase = $15$.
> - From Year 4 to Year 6 = $2$ years: Projected = $295 + 15 \times 2 = 325$.

### C4. Exponential trend projection

Given: Average claim cost in Year 0 = $200$. Exponential trend rate = $4\%$ per year. Project cost for Year 3.

> [!answer]- Answer
> - Projected = $200 \times (1.04)^3 = 200 \times 1.124864 = 224.97$.

### C5. Trend with deductible leveraging effect

Given: Base claim cost trend (economic inflation) = $5\%$. Deductible remains $500$. Before inflation, $40\%$ of claims exceeded deductible. After $5\%$ inflation, expected proportion exceeding deductible becomes $45\%$ (approx). Explain the effective trend impact on claims net of deductible and compute approximate effective factor on the portion affected.

> [!answer]- Answer
> - Deductible leveraging: stable deductible + inflation means deductible eliminates fewer dollars; higher proportion now exceeds deductible.
> - Effective trend on claims net of deductible is higher than $5\%$ for the excess layer.
> - Approx effective factor on affected claims = $(1.05) \times (45/40) = 1.05 \times 1.125 = 1.18125$ (18.125%) for the excess portion (illustrative of leveraging effect).

### C6. Expense adjustment and trend

Given: Fixed expenses for experience period = $1,200,000$. Variable expenses = $800,000$ (on $10,000,000$ premium, $8\%$ rate). Project fixed expenses forward 2 years with annual trend $3\%$ on fixed expenses. Compute projected fixed and total expense provision (fixed + variable) assuming same volume/premium rate for variable.

> [!answer]- Answer
> - Projected fixed = $1,200,000 \times (1.03)^2 = 1,200,000 \times 1.0609 = 1,273,080$.
> - Variable = $800,000$ (8% of premium).
> - Total expense provision = $1,273,080 + 800,000 = 2,073,080$.

### C7. Rate adequacy check (loss ratio + expense ratio)

Given: Projected loss ratio = $72\%$. Expense ratio (fixed+variable, including reinsurance as applicable) = $25\%$. Target profit/load = $5\%$. Assess rate adequacy.

> [!answer]- Answer
> - Total ratio = $72\% + 25\% + 5\% = 102\% > 100\%$.
> - Rates are not adequate (shortfall of $2\%$ of premium).

### C8. "Not excessive" profit constraint

Given: Required return/cost of capital equivalent profit = $4\%$ of premium. Indicated profit margin = $6\%$. Under regulation where profit must equal cost of capital if accepted, assess excessiveness.

> [!answer]- Answer
> - Indicated $6\%$ exceeds cost-of-capital-based profit of $4\%$; if regulation limits profit to cost of capital, $2\%$ would be considered excessive/unreasonable.

### C9. Data sufficiency/reconciliation check

Given: Reported paid claims = $5,000,000$. Case reserves = $2,000,000$. Total incurred claims as reported = $7,000,000$. Reconciliation against ledger shows unallocated adjustment of +$100,000$. Determine adjusted incurred and what data validation step is needed.

> [!answer]- Answer
> - Adjusted incurred = $7,000,000 + 100,000 = 7,100,000$.
> - Data reconciliation required: verify unallocated adjustment, ensure sufficiency/reliability, and report on data validation.

### C10. Selecting trend period (short-tail vs long-tail)

Given: Short-tail line with stable environment, long-tail line with high uncertainty in recent points. Recommend trend periods.

> [!answer]- Answer
> - Short-tail: 4-5 years of exposure (ultimates more certain).
> - Long-tail: consider both short- and long-tail trend indications; may not use most recent points due to high leverage; balance stability vs responsiveness and assess reliability of recent data.


## Part D — Exam-Style Questions

Source: [[Actuarial Standards]], [[Credibility]], [[Data]], [[Documentation]], [[Expenses and Profit]], [[Rate Regulation]], [[Trend]]

### D1. Actuarial Standards and Professional Judgment

You are pricing a new coverage in a jurisdiction. Explain the role of ASOPs (goals/purposes) and how they interact with professional judgment and the users/intended uses of the work. Include documentation requirements.

> [!answer]- Answer
> - **ASOP goals**: Promote consistency across situations, increase public/client confidence, without unnecessary constraints on judgment/creativity.
> - **Purposes**: Ensure professional due care; results relevant to user needs, clear/understandable/complete; assumptions/methodologies disclosed appropriately.
> - **Users/intended uses**: Crucial in shaping work (jurisdiction where work applied must be followed).
> - **Documentation**: Integral; complete if another qualified actuary could redo the work and assess judgments made.
> - **Application**: Balance compliance with standards while exercising professional judgment tailored to intended users/uses.

### D2. Credibility and Complement Selection

An insurer has limited own experience for a niche product. Describe key considerations when assigning credibility and selecting a complement of credibility. Give a numeric example showing impact.

> [!answer]- Answer
> - **When to use credibility**: Projecting ultimates, estimating unpaid claims, pricing.
> - **Assignment considerations**: Volume (claims/premiums/exposures), years of data, stability/variability, large/unusual claims, internal/external changes, age/relevance/reliability of own data and complement data.
> - **Complement**: Must be similar to insurer's own experience.
> - **Example**: Own pure premium $300$, complement $250$, $Z=0.40$: Weighted = $0.40\times300 + 0.60\times250 = 120 + 150 = 270$.

### D3. Data Quality and Reliance on Others

You are reviewing data supplied by a third party for a pricing exercise. Outline your responsibilities for data selection, validation, reliance, and disclosure.

> [!answer]- Answer
> - **Selection**: Data must be sufficient (appropriate) and reliable (substantially accurate); actuary responsible for gathering needed data.
> - **External differences**: Understand definitions, claim management, LOB, underwriting, geographic mix, coding, deductibles/limits, legal precedents, reinsurance practices.
> - **Validation/reliance**: Validate for sufficiency, reliability, appropriateness; disclose reliance on others.
> - **Review/reconciliation**: Be certain data sufficient/reliable; report on validation; consider impact of deficiencies.
> - **Environment**: Be aware of operational changes and effects on work; document/report data quality processes.

### D4. Trend: Balancing Stability vs Responsiveness

You need to select a trend period for both short-tail and long-tail lines. Explain considerations, adjustments, and model choice.

> [!answer]- Answer
> - **Considerations**: Credibility of data, time period available, relationship to items trended, known biases/distortions; economic/social inflation, deductible leveraging, utilization, mix changes, tech advances.
> - **Adjustments**: Remove outliers; adjust for large claims, unusually large number of large claims, catastrophes, seasonality, tort/product reform, legislated benefit changes; account for regional/product/demographic variations.
> - **Periods**: Short-tail 4-5 years (ultimates certain). Long-tail consider short/long-tail indications; may avoid most recent points (high leverage); balance stability (longer) vs responsiveness (recent).
> - **Models**: Linear (constant amount; may be inappropriate for decreasing trends) vs exponential (constant rate). Compare via $R^2$, F-statistics, or p-values. Judgment-based; results can differ.

### D5. Expenses, Profit, and Rate Regulation

A filing shows projected loss ratio $75\%$, expense ratio $22\%$, indicated profit $6\%$. Cost of capital-based profit limit is $4\%$ (if accepted by legislation). Discuss expense treatment, profit definition, and rate regulation compliance (adequate, not excessive, not unfairly discriminatory).

> [!answer]- Answer
> - **Expenses**: Split fixed/variable; adjust fixed for trend; reinsurance costs may be included; review historical for relevant period, apply trend, or rely on budget/planned; ensure representative of future.
> - **Profit**: If accepted by legislation, profit = cost of capital.
> - **Regulation**: Adequate (sufficient for claims/expenses; solvency protection). Not excessive (no unreasonable profits; affordability). Not unfairly discriminatory (price reflects expected cost; restrictions possible).
> - **Assessment**: Total $75+22+6=103\%$ indicates inadequate rates (shortfall $3\%$). However, indicated profit $6\% > 4\%$ cost-of-capital limit would be excessive under that constraint; need to reconcile (adequacy shortfall vs profit cap). Consider residual market provisions if applicable.