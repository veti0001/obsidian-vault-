## 1. Assumptions

- Claims recorded to date will continue to develop in a similar manner in the future (past development is indicative of future development).
- The relative change in a given accident year’s claims from one evaluation point to the next is similar to the relative change observed in prior years at similar maturities.
- No change in claim settlement philosophy.
- No change in the process or timing of claim payments.
- Stability in the process surrounding claim reopenings.
- Consistency in the distribution of policyholders:
    - Geographic area
    - Classification
    - Policy deductibles and limits
    - Reinsurance program 
## 2. Paid vs. Reported Claims

### Additional assumptions when using **reported** claims

- No changes in the insurer’s internal or external environment
- Consistency in claim reporting patterns.
- Consistency in the process for establishing case estimates.
- Consistency in the adequacy of case reserves over time.

### Advantages of **paid** claims

- Changes in case estimates do not influence paid claims.
### Advantages of **reported** claims

- Reported claims are typically more credible and less volatile due to higher volume.
- Are not affected by changes in settlement pattern
## 3. Selection of Average Age‑to‑Age Factors

### Types of averages

- **Simple average**
    
- **Volume‑weighted average**
    
    - Reduces standard error due to higher data volume.
    - Volume may correlate with time, giving more weight to recent observations.
- **Medial average** (exclude high and low values)
    
    - Reduces impact of outliers but reduces sample size.
- **Geometric average**
### Time period selection criteria

- **Credibility of data**
    
    - High credibility → use fewer years to reflect recent trends.
    - Low credibility → use longer‑term averages for stability.
    - Medial averages may help increase credibility.
- **Operational changes**
    
    - Consider excluding years affected by operational shifts.
- **Changes in policy characteristics**
- **Presence of large claims**
- **External environment changes**
## 4. Selection of Age‑to‑Age Factors

Considerations:

- Volume of experience and credibility of insurer data.
- Stability of individual factors at each maturity interval and similarity of averages.
- Trends in individual or average factors.
- Number of recent factors exceeding the selected average.
- Known internal or external changes affecting development.
- Influence of large claims.
- Relevance of industry benchmarks.
- Prior actuarial selections.
    

### Tail Factor Selection

#### Bondy Method

- **Advantage:** Simple.
- **Disadvantage:** May significantly underestimate tail development for long‑tail lines.
#### Algebraic Method

- **Assumptions:**
    
    - Paid and incurred ultimate estimates are equal.
    - Incurred estimate for the oldest year is accurate.
    - Other years will follow similar tail development as the oldest year.    
- **Advantage:** No additional data required.
- **Disadvantage:** Relies heavily on the accuracy of the most mature incurred estimate.
#### Benchmark Data

- Use industry or external benchmarks when internal data is insufficient.
## 5. Large Loss Treatment

- Exclude large losses when calculating age‑to‑age factors (cap claims).
- Adjust ultimate claims as:
	- (Claims−Large Claims)×CDF + Large Claims
## 6. ALAE Treatment

Two approaches when combining ALAE with claims:

- Reporting and payment patterns are similar to claims.
- Differences between ALAE and claim patterns are stable across years.

Consider ALAE separately when:

- Reporting or payment patterns differ materially from claims.
- ALAE volume is large relative to claims (e.g., 40%).
## 7. Seasonality

- Consider seasonality when selecting CDFs.
- Review half‑year age‑to‑age averages for patterns.
- If seasonality exists, select ratios corresponding to the projection period.
## 8. Reinsurance

Two approaches:

- Project ultimate claims **gross** and **net**, then derive ceded ultimate as the difference.
- Project ultimate **ceded** claims directly.
### Quota Share

- Apply ceded percentage directly to ultimate claims.

### Excess of Loss

Analysis depends on:
- Volume of available data.
- Changes in attachment points or limits.

Possible approaches:
- Select development factors **gross** of reinsurance and apply them to **net** claim data.
## 9. Common Usage

- Paid and reported claims, as well as claim counts.
- Applicable to short‑tail and long‑tail lines.
## 10. When to Use

- Insurer operates in a stable environment.
- Large volume of historical claims experience is available.
- Well understood and accepted method
## 11. When Not to Use

- Presence of large claims that distort development.
- Insufficient credible data:
    - New line of business or new territory.
    - Small insurers with limited portfolios.
    ### Negative point in using this method
    
	- Development for the most recent year can be very unstable and an unreliable predictor of ultimate claims
	- Projection is dependent on the last value on the diagonal of the triangle
	- Relationship between claims at successive age may not be best explain by multiplicative factor
	- Change in operation can result in historical relationship that are no longer predictive of future claim activity
	- implicit assumptions that inflation in claim payments has been consistent and stable and that it will continue at the same rate in the future
	- it does not measure or adjust for calendar-year effects
	- it includes a significant number of parameters and many would argue that it over-fits the model to the data.
## 12. Impact of Changes in Assumptions

### Increasing Claim Ratio

- No change in projection; age‑to‑age factors remain consistent.
### Increase in Case Outstanding Strength

- Reported method **overstates** ultimate claims and IBNR:
    - Higher case adequacy → higher CDFs.
    - Higher reported × higher CDF → overstated unpaid claims.
- Paid method remains accurate.
### Increasing Claim Ratio + Increase in Case Strength

- Paid method remains accurate.
- Reported method responds to higher claim ratios but still overstates due to case adequacy changes.
### Change in Product Mix

- If distribution across categories remains stable, method remains accurate.
- Reported method more responsive than paid due to faster reporting.
- Both methods underestimate IBNR if mix shifts significantly.
### Increase in Settlement Rate

- Paid method over‑projects ultimate losses (historical factors reflect slower settlement).
- Reported method remains appropriate.