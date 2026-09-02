| Expense Type                                | Description                                                                             | Examples                                                                                                                     | Estimation Method               |
| ------------------------------------------- | --------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------- | ------------------------------- |
| ULAE (Unallocated Loss Adjustment Expenses) | Claim-related expenses of a general nature that cannot be allocated to a specific claim | - Salaries  <br>- Administrative costs of having a claims department                                                         | Estimated on an aggregate basis |
| ALAE (Allocated Loss Adjustment Expenses)   | Expenses that are directly attributable to a specific claim                             | - Claim investigation expenses  <br>- Defense attorneys  <br>- Medical evaluation  <br>- Expert review  <br>- Record copying | Directly allocated per claim    |
## Unpaid ULAE 

- Estimated on an Aggregated basis for the whole company
- ULAE are almost neve ceded to reinsurer so they are calculated using gross claims

### Ratio based method

- Unpaid ULAE = (ULAE ratio X IBNR) + (ULAE ratio X multiplier X case estimate)
- There is a substantial amount of ULAE that happens when claim are opened. We assume that already reported claims should have a lower unpaid ULAE than unreported claims
- That is why we assign a multiplier to the second part of this formula (usually 0.5)

#### Classical Paid-to-Paid method

- Most widely used method
- CY paid ULAE are compared to CY paid claims
- Looks at CY since ULAE cannot be allocated to specific claims
- Assumptions:
	- Payments for ULAE are proportional to payments for claims;
	- The timing of payments for ULAE follow the timing of payments for claims;
	- The insurer's relationship of paid ULAE to paid claims has achieved a steady state such that the paid-to-paid ratio is a reasonable approximation of the relationship between ultimate ULAE and ultimate claims;
	- The historical relationship between paid ULAE and paid claims represents the relationship expected between future ULAE and future claim payments; and
	- The ULAE associated with open and pure IBNR claims are proportional to the case estimates and IBNR claims.
- Weakness:
	- useful in a steady state environment
	- During a time exposure growth the ULAE ratio is overstated:
		- ULAE reacts fairly quick to growth in exposures
		- Paid claims are less responsive to growth in exposures
	- During a period  of exposures the ULAE ratio is overstated:
		- inflation impact more the ULAE than paid claims
		- the 0.5 multiplier could also not be accurate
	- More appropriate formula would be:
		- Unpaid ULAE = (ULAE ratio X IBNYR) + (ULAE ratio X multiplier X (case estimate+ development on case estimate)
		- development on case estimate = IBNR - IBNYR
		- since IBNR = IBNER + IBNYR
	- the method is biased and often produce estimate that are too high

#### Kittel refinement

- Need to consider both reported and paid claims, since there are also ULAE when claims are reported
- Can fix the issue related to increase in exposure 
- Weakness:
	- The same 0.5 multiplier is still used
	- Inflation & exposure growth problem is still not fixed (both at the same time)

#### Mango and Allen adjustment

- Useful in the following situation:
	- Long-tail line of business
	- Changing exposure volume
	- When there are large claims that distort the CY paid and reported claims
	- When there is a low claim volume with a great variability in the averages
	- When there is not a lot of volume of credible paid or reported claims
- Assumptions:
	- payment, reporting patterns and estimated ult claims are accurate

#### Count based methods

- Average ULAE will differed based on the transaction type
- Advantages:
	- ULAE does not only depend on the claim amount. 1 500k claims will probably have lower ULAE than 10 50k claims  
	- ULAE will fluctuate to changes in claim estimates if ULAE ratio is used
	- ULAE will be similar for claims files that are similar if count based approach is used
- Data needed:
	- Triangles of reported and closed count
	- Selected ultimate count
	- Paid ULAE
- Weakness:
	- Estimated ULAE tend to be much lower than the estimated ULAE from classical paid-to-paid method
	- Count categories are not exclusive (claim can be open and closed in the same year)
	- It is not because a claim file is open longer than the ULAE will necessarily be higher
	- Difficult to determine the claim files that are open and closed during a year 
