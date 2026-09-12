# BF (Bornhuetter–Ferguson)

## Assumptions

- Ultimate claims can be better estimated based on an a priori estimate than using the experience observed to date for that period.
- A reasonable claim ratio can be obtained.

## Common Usage

- When there are random fluctuations or large claims at early maturities.
- When entering new LOBs or geographical areas.
- When estimating ultimate at early maturities for long-tailed lines of business where the early age-to-ultimate factors are heavily leveraged.
- When the experience period is immature.

## Advantages (When to Use)

- Provides more stable estimates than the development technique and more responsive estimates than the expected method.
	- Help mitigate the issue of highly leverage development factor applied to immature year (even more important for long tail covers)
- Benktander is even more responsive than BF while being more stable than the development method, though not as stable as BF.
- Easy to apply and to explain to non-actuaries.
- It is intuitive to give more weight to actual claims as years mature.
- External information can easily be incorporated in the analysis.

## Disadvantages (When Not to Use)

- When CDFs are lower than one, this needs to be taken into account.
	- capped at 0 the weighting or do nothing

## Change in Assumptions

### Speed up or slowdown of settlement of claims

- Reported will still be accurate.
- Paid will overestimate when there is a speedup and underestimate when there is a slowdown, but the magnitude will not be as big as when development techniques are used, because of the weight given to the expected method.

### Change in case reserve adequacy

- Paid will be accurate.
- Reported will overestimate when there has been an increase and underestimate when there has been a decrease, but the magnitude will not be as big as when development techniques are used, because of the weight given to the expected method.

### Change in claim ratio

- These methods do not fully react to a change in claim ratio, because of the weight given to the expected method.
- Reported will be more precise since more weight is given to the development method.

### Exposure growth

- Methods are unaffected by exposure growth on their own.
- If changes in the average accident date occur, the estimates will be in the same direction as chain ladder but lower.

### Change in mix of business

- Will be impacted if one of the following is true:
  - Segments of the business that are changing have a different claim ratio (change in claim ratio).
  - Segments of the business that are changing have the same claim ratio, but a different development pattern.