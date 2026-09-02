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
- Prediction error of a GLM can be decomposed into:
	- parameter error
		- difference between True mean and the forecast
	- process error 
		- is caused by the facts that even thought the model may be perfectly calibrated there would still be some error due to the stochastics value of the future observations
	- model error
		- 3/4 of total prediction error
		- difficult to quantify
		- can be partially mitigated by weighting the outputs of multiple models
- Model predicts reserving values that are too light in the tails in general
- MSEP
	- useful to look at when looking at outputs of Mack model
	- estimates the tightness of a forecast around it's target
	- we want the model that produces the smallest MSEP
	- Takes into account the number of parameters
- AIC/BIC
	- wants the lower possible values 
- K-folding
	- can be useful to look at model error

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