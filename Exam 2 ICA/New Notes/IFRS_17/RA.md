 ## Definition:
- “An entity shall adjust the estimate of the present value of the future cash flows to reflect the compensation that the entity requires for bearing the uncertainty about the amount and timing of the cash flows that arises from non-financial risk.”

## Non-financial risk
-  operational risks and market risks are types.
- Characteristics:
	- risks with low frequency and high severity will result in higher risk adjustments for non-financial risk than risks with high frequency and low severity;
	- for similar risks, contracts with a longer duration will result in higher risk adjustments for non-financial risk than contracts with a shorter duration;
	- risks with a wider probability distribution will result in higher risk adjustments for non-financial risk than risks with a narrower distribution;
	- the less that is known about the current estimate and its trend, the higher will be the risk adjustment for non-financial risk; and
	- to the extent that emerging experience reduces uncertainty about the amount and timing of cash flows, risk adjustments for non-financial risk will decrease and vice versa.

## General consideration

- RA may differ by company has it represent the assessment of the entity's own risk appetite
- Generally, entities require compensation for bearing the uncertainty, however, some entities might not require a compensation . RA = 0.
- Calculated at portfolio or entity level or at unit of account based on the relevant method

## Unit of account

- The RA is determined on initial recognition and at each reporting date and reported for each group
- RA influence CSM or LC 
- RA can be determine at higher level and then allocated to the group

## Disclosure

- approach used to determine RA
- confidence level of the reported RA
- disclose a reconciliation of the movement in the RA from the opening balance to the closing balance
- disclose significant judgements and changes in judgments used in the calculation of the RA

## Selection of the measurement approach

### Diversification
- diversification affects both the amount of the RA and the assessment of the confidence level of the RA
	- #### Allocation in an aggregate approach
		- aggregate risk distribution would reflect the benefits of diversification
		- can be done by:
			- statistical or empirical analyses
			- expert judgment
			- causal relationship
		- the more uncertain the diversification benefits are, the less likely those benefits would be reflected in the final distribution
		- usually quantify by correlation matrices and copulas.
		- benefits of diversifications would be allocated to the units 
	- #### Allocation in an unit of account approach
		- the RA for a unit may or may not reflect the diversification benefits between all the different units in the entity
		- if not all the diversification is reflected in the RA, the confidence in the RA will be higher (we are more conservative)

## Reinsurance 

- RA is reported as a positive assets
- RA represent the risk ceded to the reinsurer
- RA is reported separately for insurance contracts issued and reinsurance contracts held
- ceded RA (i.e., pertaining to reinsurance contracts held) represents the non-financial risk transferred from the entity to the reinsurer(s)
- How to determine:
	- Price of reinsurance = RA. We assumed that the price represent the compensation that would be required to keep the risk
	- difference between position with reinsurance and without reinsurance
	- if the price of reinsurance is proportional to the amount of risk ceded, then the ceded RA is proportional to the gross RA (ceding % similar for portfolio)

## Discount Rate

- no guidelines

## Time Horizon

- lifetime of the uncertainty of the insurance cash flows

## Calculation approach

### Quantile methods

- VaR and CTE
- #### Advantages
	- we directly get confidence level
- #### Disadvantages
	- if the results are misrepresented it could introduce spurious accuracy
	- need to specify a distribution
- #### How it works
	- use following method to produce a distribution
		- suitably skewed probability distribution (e.g., lognormal or gamma distribution) to projected future cash flows 
		- Monte Carlo simulation
		- bootstrapping
		- scenario modelling
	- if we use VaR, RA = VaR(x) - E(present value of probability weighted cash flow)
	- if we used CTE, RA = CTE(x) - E(present value of probability weighted cash flow)
- #### Method to calculate quantile
	- Monte Carlo
		- Advantages:
			- Need way less data than Bootstrap
			- work for data that is correlated (Not bootstrap)
	- Bootstrap
		- Advantages
			- More precise
		- Disadvantages
			- Need a lot of uncorrelated data
### Cost of capital method

- RA = compensation that the entity need to meet a target return
- #### Advantages
	- Conceptually close to the definition of the RA
	- allows allocation of the RA at a more granular level
- #### Disadvantages
	- operationally complex
- #### Capital
	- predicted by internal capital models
	- the predicted capital need to be adjusted for the following
		- removal of the capital component(s) related to risks other than the non-financial risks in scope of the RA (such as market risk or general operational risk);
		- diversification if not specifically addressed in the capital model being used; and
		- consideration of risk-sharing mechanisms (e.g., reinsurance and Facility Association) reflected in the estimates of future cash flows
- #### Cost of capital
	- weighted average rate of return on capital for an entity minus investment rate that could be earned on the capital
	- tactical approach is to use target rates of return on capital by capital source
### Margin Method

- only work under unit of account methods
- actuary would select margins that reflect the compensation the entity requires for uncertainty related to non-financial risk
- #### Disadvantages
	- how to determine confidence level

### Reinsurance held methods

- #### Quantile
	- RA can equal:
		- difference between gross and net
			- distribution are readily available
			- if reinsurance coverage is non-proportional, the difference may not represent the ceded risk
		- ceded data
- #### Catastrophe models
	- could provide useful information on ceded RA
- #### Proportional Scaling
	- only works when assessing the ceded RA for proportional coverages
		- use a fixed percent of gross RA
	- could be apply to non proportional reinsurance contracts if we can prove that the ceded RA is proportional RA
- #### CoC
	- need to have CoC rate on a gross of reinsurance basis

## Catastrophe reinsurance 

- Cat may impact the RA
- estimate net RA separately from ceded RA
- Quantile methods may not capture losses

## Combine multiple methods

- Multiple methods can be combined
- E.g. VAR for less skewed distribution and CoC for group with more skewed distributions
- ### Aggregate Approach
	- Main methods are:
		- Quantile
		- CoC

