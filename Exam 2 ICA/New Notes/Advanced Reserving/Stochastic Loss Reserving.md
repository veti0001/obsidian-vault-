## Mack Model

- Stochastic distribution free Chain ladder model
- No specified probability distribution
- Only mean and variance are produced

### Data

- Cumulative loss triangles
### What it produces

- Chain‑ladder expected ultimate losses
- **Analytical formulas** for:
    
    - process variance
    - parameter variance
    - MSEP of ultimate losses
### Strengths

- Minimal assumptions
- Closed‑form MSEP
- Easy to implement

### Weaknesses (from Meyers)

Meyers shows Mack **fails validation** on incurred triangles in the CAS database:
> “These models do not accurately predict the distribution of outcomes… the percentiles are not uniformly distributed.”

Reason: Mack cannot capture calendar effects, correlation, operational changes, or skewness.

## ODP Mack Model
Taylor & McGuire show that chain‑ladder can be written as a **generalized linear model** with:

- **Distribution**: Over‑dispersed Poisson (ODP)
- **Link**: log
- **Mean structure**: ln⁡(μw,d)=αw+βd

This is quoted in the monograph:

> “There are two families of stochastic model which generate the chain ladder algorithm… Both families may be formulated as generalized linear models.”

- Variance is implied by the GLM distributional assumptions

### Data

- Incremental loss triangles
### Why this matters

The GLM representation provides:

- parameter estimates
- dispersion parameter
- residuals
- deviance
- diagnostics
- ability to extend the model (trend, calendar effects, interactions)
### Relationship to Mack

- Mack is **distribution‑free**
- ODP GLM is **parametric**
- Both produce the same **mean chain‑ladder estimates**
- But ODP GLM provides a **likelihood**, enabling bootstrap and Bayesian extensions

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

## ODP bootsraping

### Data

- Incremental loss triangles
- Enough data to compute residuals
### Core idea

Use the fitted ODP GLM and **resample residuals** to simulate:

- parameter uncertainty
- process uncertainty
- full predictive distribution of unpaid losses
    

### Steps (from Taylor & McGuire)

> “GLM formulation naturally invites the use of a bootstrap to estimate prediction error… The bootstrap estimates the entire distribution of loss reserve rather than just the mean square error.”

### Workflow

1. Fit ODP GLM to incremental triangle
2. Extract Pearson residuals
3. Adjust residuals using hat‑matrix (to equalize variance)
4. Resample residuals with replacement
5. Reconstruct pseudo‑triangles
6. Refit GLM → parameter uncertainty
7. Simulate future increments using ODP variance → process uncertainty
8. Aggregate → predictive distribution

### Strengths

- Easy to implement
- Captures parameter + process variance
- Widely used in practice

### Weaknesses (from Meyers)

Meyers shows bootstrap ODP **fails validation** on paid triangles:

> “For paid losses, both methods tend to overstate the range of expected outcomes.”

Reason: residual bootstrap assumes i.i.d. residuals and no calendar effects.

## MCMC

### Core idea

Instead of resampling residuals, **simulate from the posterior distribution** of all parameters using MCMC (JAGS).

### Why MCMC is needed

Meyers explains:

> “Bayesian MCMC models have provided actuaries with unprecedented flexibility… complex Bayesian stochastic loss reserve models are now practical.”

### What MCMC allows that bootstrap cannot

Meyers introduces four key enhancements:

1. **Accident‑year correlation** Bootstrap assumes independence; MCMC can model correlation structures.
2. **Skewed distributions allowing negative increments** Paid data often have negative incremental values; MCMC can use skew‑normal or t‑distributions.
3. **Payment‑year trend** Calendar effects (inflation, operational changes) can be modeled directly.
4. **Changing settlement rate** MCMC can incorporate dynamic claim closure patterns.
    

### Workflow

1. Specify likelihood (e.g., skew‑normal, t, ODP, lognormal)
2. Specify priors for parameters
3. Use MCMC (Metropolis‑Hastings, Gibbs) to simulate posterior
4. For each posterior draw, simulate future increments
5. Aggregate → full predictive distribution

### Strengths

- Handles correlation
- Handles skewness
- Handles calendar trends
- Handles operational changes
- Produces full posterior predictive distribution
- Validates better on CAS database
### Weaknesses

- Requires modeling choices
- Requires convergence diagnostics
- Computationally heavier

## Combine stochastics model outputs

- Use the same random variable for each model
	- the final incremental value of each models can be weighted together
- Run models with independent random variables
	- weights are selected to randomly select a model for each iteration by AY
- Apply correlation
	- Calculated correlation is almost always close to 0 witch is not ideal
	- Contagion is not suited to the following calculation (contagion between different lines of business)
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