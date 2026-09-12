## Mack Model

- Stochastic Chain ladder model
- Conditions:
	- AY are independent
	- AY different incremental value form a Markov chain
	- Cumulative value knowing past incremental value (for a given AY) follows a EDF(...) law
	- Same output as CL
- ODP Mack model happens when the conditional law is ODP
- Predict values that are too high
- **Disadvantages:**
	- The Mack model use the last value on the diagonal to calculate ultimate losses
	- The Mack model assumes that all the AY are independent
	- No information about the distribution of the predictor error
	- No clue about the accuracy of the MSEP
## Bootstrapping


- Estimate the entire distribution

- ### Semi-parametric bootstrapping
	- based on empirical residuals
	- involves repeated resampling from the available data
	- the residuals are resample and new datasets are created from these and fitted values
	- need the iid assumptions
	- Model is then fitted on new crated triangles
	- We get a distribution of possible values

- ### Parametric bootstrapping

	- based on theorical residuals (sampling from normal distribution for residuals)
	- easier to implement then semiparametric version. 
	- needs more assumptions to be true

- ### ODP Bootstrap

	- Incremental losses follows a ODP poison model
	- Need to use paid losses since ODP model only works for positive value
	- Predict values that are too high
	- #### Weakness:
		- only works for positive incremental value (can adjust link functions to overcome this issue)
		- only work for complete triangles
		- Another common issue with using the ODP bootstrap model is that the distribution for the most recent accident years can produce results with more variance than you would expect when compared to earlier accident years.
			- Can be fixed by doing BF or Cape-Cod
	- #### Advantages (GLM bootstrap)
		- The flexibility of the GLM framework allows the modeler to use enough parameters to capture the statistically relevant level and trend changes in the data without forcing a specific number of parameters.
			- too much parameter = over-fitting
		- this framework affords us the ability to add parameters for calendar-year trends
		- GLM bootstrap model can be used to model data shapes other than triangles
		- allow one to move away from the two basic assumptions of a deterministic chain ladder method
		
	- #### Assumptions

		- Same as Chain-Ladder
		- **Pearson residuals represent the error structure**
		- Residuals are i.i.d.
		- Zero residuals are excluded
		- **Residuals must be standardized**
		- **Incremental losses follow an ODP GLM** with log‑link.

## MCMC

- The distributions can have parameters that are distributions
- Used to overcome the shortcomings of both model presented above
-  Workings:
	- 1. The user specifies the prior distribution, p(y), and the conditional distribution, f ( xy).
	- 2. The user selects a starting vector, x1, and then, using a computer simulation, runs the Markov chain through a sufficiently large number, t1, of iterations. This first phase of the simulation is called the “adaptive” phase, where the algorithm is automatically modified to increase its efficiency.
	- 3. The user then runs an additional t2 iterations. This phase is called the “burn-in” phase. t2 is selected to be high enough so that a sample taken from subsequent t3 periods represents the posterior distribution.
	- 4. The user then runs an additional t3 iterations and then takes a sample, {xt}, from the (t2 + 1)th step to the (t2 + t3)th step to represent the posterior distribution f ( yx).
	- 5. From the sample, one then constructs various “statistics of interest” that are relevant to the problem addressed by the analysis.

## Combine stochastics model outputs

- Use the same random variable for each model
	- the final incremental value of each models can be weighted together
- Run models with independent random variables
	- weights are selected to randomly select a model for each iteration by AY
- Apply correlation
	- Calculated correlation is almost always close to 0 witch is not ideal
	- Contagion is not suited to the following calculation is contagion between different lines of business
	- Location mapping:
		- Use the same residuals for each resample triangles
		- Correlation of the original residuals is preserved in the sampling process
		- Advantages:
			- easy to implement
		- Drawbacks:
			- requires all of the business segments to use data triangles that are precisely the same size with no missing values or outliers when comparing each location of the residuals
			- The correlation of the original residuals is used in the model, and no other correlation assumptions can be used for stress testing the aggregate results
	- Resorting:
		- use copulas or Iman-Cover algorithm
		- advantages:
			- The triangles for each segment may have different shapes and sizes,
			- Different correlation assumptions may be employed, and
			- Different correlation algorithms may also have other beneficial impacts on the aggregate distribution.

## Stochastics Model

- Produce full probability distribution for unpaid claims
- Can calculate std of estimators
- #### Advantages
	- Quantify uncertanty explicitly
	- Statistical testing and diagnostics
	- Decompose sources of variability
		- Separate process risk and model risk
- #### Disadvantages
	- Model risk and over confidence
	- Data and computational requirements
	- communicational difficulty
## Scenario test

- Test multiple adverse scenarios
- #### Advantages
	- transparency and relevance
	- Focus on plausible severe outcomes 
	- Low data burden
- #### Disadvantages
	- Not probabilistic (No confidence interval)
	- Selection bias
	- Potential for incomplete coverages (Not all scenarios are taken into account)

## Use of alternative sets of assumptions

- produce a range of possible assumptions
- Show sensitivity and define a possible reasonable range of results
- #### Advantages
	- Simplicity and clarity
	- Quick to implement and interpret 
	- useful for governance and negotiation
- #### Disadvantages
	- Partial view of uncertainty
	- choice of alternative can be subjective
	- May give false sense of precision