# Advanced Reserving — Revision Questions

## Part A — Definitions and Recall

Source: [[Claim Layer]], [[Latent Claims]], [[Machine Learning]], [[Error in prediction]], [[Stochastic Loss Reserving]]

### A1. Define a claim layer $L(d,p)$. Which end of the layer is truncated from below and which end is censored from above?

> [!answer]- Answer
> - $L(d,p)$ = claims layer truncated from below at $d$ and censored from above at $p$
> - The lower point $d$ is where the layer is truncated from below, and the upper point $p$ is where it is censored from above

### A2. What does LEV stand for, what does $\Phi_{i,j}$ represent, what is $S_{i,j}(L_a,L_b)$, and what is a Basic Limit $B$? Give the formula used to restate observed claim amounts onto the basic limit.

> [!answer]- Answer
> - LEV = limited expected value
> - $\Phi_{i,j}$ = assumed distribution
> - The limit adjustment factors $S(a,b)$ represent the ratio of expectations of claims between layer $L_a$ and $L_b$
> - Formula 1: $S_{i,j}(L_a,L_b) = \dfrac{LEV(p_a;\Phi_{i,j}) - LEV(d_a;\Phi_{i,j})}{LEV(p_b;\Phi_{i,j}) - LEV(d_b;\Phi_{i,j})}$
> - Formula 2: $S_{i,j}(L_a,L_b) = E[C_{i,j}L_a \mid C_{i,j}L_b]$
> - It is a **ratio of expectations**, not an expectation of a ratio
> - Basic limit $B$ = the threshold at which we believe the data is sufficiently credible for developing claims development patterns
> - Restatement: $E[C_{i,j}B' \mid C_{i,j}L] = C_{i,j}L \times \dfrac{LEV(B;\Phi_{i,j})}{LEV(L;\Phi_{i,j})}$, where $L$ = the limit of the data we actually have access to
> - We adjust observed claim amounts for differences in cost level and limit using the limited expected value function

### A3. State three cautions about trend factors when working with claim layer data.

> [!answer]- Answer
> - Trend that acts in the development period or calendar period direction is often not considered
> - If trend is estimated from claims data that is subject to policy limits or deductibles, we must first adjust the data to a ground-up, unlimited basis using the claim size model
> - The trend factor will be different for every value of the triangle (in theory)

### A4. What is a latent claim, and what types are given?

> [!answer]- Answer
> - A latent claim is a risk **not specifically considered when the policy was written**
> - Types:
>   - Bodily injury
>   - Pharmaceutical claims
>   - Environmental damage

### A5. What is RBNS, and how is machine learning (regression trees) used to produce the ultimate claim count?

> [!answer]- Answer
> - RBNS = Reported but not settled
> - Machine learning — specifically **regression trees (CART)** — is used to estimate the **transition probabilities** governing whether a claim will:
>   - remain open or close next period
>   - generate a payment next period
> - These probabilities are then iterated forward to obtain the **expected total number of future payments**, i.e. the **ultimate claim count**

### A6. Decompose the prediction error of a GLM into its components. Then state what the MSEP tells us, which direction we want it in, and which other model-comparison criteria favour lower values.

> [!answer]- Answer
> - Parameter error: the difference between the true mean and the forecast; uncertainty in estimated model parameters
> - Process error: even though the model may be perfectly calibrated, there is still error due to the stochastic nature of future observations
> - Model error:
>   - approximately 3/4 of total prediction error
>   - difficult to quantify
>   - can be partially mitigated by weighting the outputs of multiple models
> - Structural changes: past data is not representative of the future
> - Black Swan event risk: large or catastrophe claims
> - MSEP:
>   - useful to look at when examining the outputs of a Mack model
>   - estimates the tightness of a forecast around its target
>   - we want the model that produces the **smallest** MSEP
>   - takes into account the number of parameters
> - AIC/BIC: we want the **lowest possible values**
> - K-folding can be useful to look at model error

### A7. Describe the Mack model: its nature, the data it requires, and what it produces.

> [!answer]- Answer
> - Mack model = a stochastic, **distribution-free** chain ladder model
> - No specified probability distribution
> - Only mean and variance are produced
> - Data required: cumulative loss triangles
> - What it produces:
>   - chain-ladder expected ultimate losses
>   - **analytical formulas** for process variance, parameter variance, and MSEP of ultimate losses
> - Strengths: minimal assumptions, closed-form MSEP, easy to implement

### A8. Taylor & McGuire show chain ladder can be written as a GLM. Give the distribution, link, and mean structure, and explain why this GLM representation matters.

> [!answer]- Answer
> - Distribution: Over-dispersed Poisson (ODP)
> - Link: log
> - Mean structure: $\ln(\mu_{w,d}) = \alpha_w + \beta_d$
> - Data required: incremental loss triangles
> - The GLM representation provides parameter estimates, a dispersion parameter, residuals, deviance, diagnostics, and the ability to extend the model (trend, calendar effects, interactions)
> - Variance is implied by the GLM distributional assumptions
> - Mack is **distribution-free**; ODP GLM is **parametric**; both produce the same **mean chain-ladder estimates**, but the ODP GLM provides a **likelihood**, enabling bootstrap and Bayesian extensions

## Part B — Explain, Compare, Advantages and Disadvantages

Source: [[Stochastic Loss Reserving]], [[Latent Claims]], [[Claim Layer]], [[Machine Learning]], [[Model Validation]]

### B1. Compare the Mack model with the ODP GLM chain-ladder model.

> [!answer]- Answer
> - Distribution assumption:
>   - Mack is distribution-free, with no specified probability distribution
>   - ODP GLM is parametric (over-dispersed Poisson with a log link)
> - Data:
>   - Mack uses cumulative loss triangles
>   - ODP GLM uses incremental loss triangles
> - Outputs:
>   - Mack produces means plus analytical formulas for process variance, parameter variance and MSEP
>   - ODP GLM produces parameter estimates, a dispersion parameter, residuals, deviance and diagnostics, and allows extensions such as trend, calendar effects and interactions
> - Estimates: both produce the same mean chain-ladder estimates
> - The ODP GLM supplies a likelihood, so bootstrap and Bayesian extensions become possible
> - Mack strengths: minimal assumptions, closed-form MSEP, easy to implement
> - Mack weakness: it cannot capture calendar effects, correlation, operational changes, or skewness

### B2. Meyers shows both Mack and the bootstrap ODP failing validation on the CAS database. Explain the failures and the reasons given.

> [!answer]- Answer
> - Mack on **incurred** triangles: "These models do not accurately predict the distribution of outcomes… the percentiles are not uniformly distributed."
>   - Reason: Mack cannot capture calendar effects, correlation, operational changes, or skewness
> - Bootstrap ODP on **paid** triangles: "For paid losses, both methods tend to overstate the range of expected outcomes."
>   - Reason: the residual bootstrap assumes i.i.d. residuals and no calendar effects
> - Data needed for bootstrap ODP: incremental loss triangles and enough data to compute residuals
> - The GLM formulation "naturally invites the use of a bootstrap to estimate prediction error… The bootstrap estimates the entire distribution of loss reserve rather than just the mean square error"

### B3. What does MCMC do that the bootstrap cannot? List the four key enhancements Meyers introduces.

> [!answer]- Answer
> - Core idea: instead of resampling residuals, **simulate from the posterior distribution** of all parameters using MCMC (JAGS)
> - Four enhancements:
>   - Accident-year correlation — the bootstrap assumes independence; MCMC can model correlation structures
>   - Skewed distributions allowing negative increments — paid data often have negative incremental values; MCMC can use skew-normal or t-distributions
>   - Payment-year trend — calendar effects such as inflation and operational changes can be modeled directly
>   - Changing settlement rate — MCMC can incorporate dynamic claim closure patterns
> - MCMC workflow: specify likelihood (e.g. skew-normal, t, ODP, lognormal) → specify priors → use MCMC (Metropolis-Hastings, Gibbs) to simulate the posterior → for each posterior draw simulate future increments → aggregate to a full predictive distribution
> - MCMC strengths: handles correlation, skewness, calendar trends and operational changes; produces the full posterior predictive distribution; validates better on the CAS database
> - MCMC weaknesses: requires modeling choices, requires convergence diagnostics, computationally heavier

### B4. How can the outputs of multiple stochastic models be combined? Give the three approaches, the limitations of simply applying a calculated correlation, and compare location mapping with resorting.

> [!answer]- Answer
> - Approach 1 — use the same random variable for each model: the final incremental value of each model can be weighted together
> - Approach 2 — run models with independent random variables: weights are selected to randomly select a model for each iteration by accident year
> - Approach 3 — apply correlation:
>   - calculated correlation is almost always close to 0, which is not ideal
>   - contagion is not suited to the calculation (contagion between different lines of business)
> - Location mapping:
>   - use the same residuals for each resampled triangle
>   - the correlation of the original residuals is preserved in the sampling process
>   - Advantage: easy to implement
>   - Drawbacks: requires all business segments to use data triangles of precisely the same size with no missing values or outliers when comparing each location of the residuals; the correlation of the original residuals is used in the model, so no other correlation assumptions can be used for stress testing the aggregate results
> - Resorting:
>   - use copulas or the Iman-Conover algorithm
>   - Advantages: triangles for each segment may have different shapes and sizes; different correlation assumptions may be employed; different correlation algorithms may have other beneficial impacts on the aggregate distribution

### B5. Compare the advantages and disadvantages of stochastic models, scenario testing, and using alternative sets of assumptions.

> [!answer]- Answer
> - Stochastic models produce a full probability distribution for unpaid claims and can calculate the standard deviation of estimators
>   - Advantages: quantify uncertainty explicitly; enable statistical testing and diagnostics; decompose sources of variability, separating process risk from model risk
>   - Disadvantages: model risk and over-confidence; data and computational requirements; communication difficulty
> - Scenario testing tests multiple adverse scenarios
>   - Advantages: transparency and relevance; focus on plausible severe outcomes; low data burden
>   - Disadvantages: not probabilistic (no confidence interval); selection bias; potential for incomplete coverage, since not all scenarios are taken into account
> - Alternative sets of assumptions produce a range of possible assumptions, showing sensitivity and defining a possible reasonable range of results
>   - Advantages: simplicity and clarity; quick to implement and interpret; useful for governance and negotiation
>   - Disadvantages: partial view of uncertainty; choice of alternative can be subjective; may give a false sense of precision

### B6. How can a reserve for latent claims be determined? Compare the top-down and bottom-up approaches, and describe the "future" step.

> [!answer]- Answer
> - Top down:
>   - consider market-wide losses
>   - ignores all the differences between the different insurers
> - Bottom up:
>   - review every policy to see if it can be affected by the latent claims
> - Future:
>   - once the latent claims have happened, the insurer will change pricing or change policy wording
>   - there should then be no further issue

### B7. Describe the issues with the claim layer (basic limit) procedure, separating the "not too bad" issues from the "bad" issues. Also state how development factors at different cost levels and layers are related.

> [!answer]- Answer
> - Development factors at different cost levels and different layers are related to each other **based on claim size models and trend**
> - Issues (not too bad):
>   - the procedure requires the actuary to select a basic limit (most of the time taken into account that the basic limit is credible enough)
>   - the procedure requires the use of an (ultimate) claim size model
>   - the procedure requires that the data triangle be adjusted to a basic limit and common cost level
> - Issues (bad):
>   - claim size models at maturities prior to ultimate are generally not available
>   - the procedure requires the calculation of a triangle of trend indices in order to implement a development method analysis

### B8. What is the goal of machine learning in reserving, what advantages does it have over aggregate methods, and why can no individual prediction be made for IBNR claims?

> [!answer]- Answer
> - Goal: look at the **individual claims**, not on aggregate as we are used to
> - Advantages: aggregate methods neglect individual claims behaviour; features can be dynamic in the model (stochastic features)
> - For IBNR claims we use chain ladder to determine the future reported claims count
>   - this means that for these claims we cannot provide individual claim-specific predictions, because we do not have feature information
>   - instead we simulate the feature needed for the ML process so that we can predict how claims will evolve (this is implied by the use of a homogeneous marked Poisson process)

### B9. Why is it generally not possible to assess goodness of fit on a test set when validating a model on triangles, and what does the validation list require?

> [!answer]- Answer
> - Goodness of fit on the test set is not generally possible with triangles, since **all the data is used to create the triangles**
> - Analysis of distributional assumptions: review the link function and model choices
> - Analysis of goodness of fit: review residuals to get an idea of the error distribution
> - Validation list:
>   - appropriate link function
>   - reasonable selection of distribution
>   - fit the main effects in the model and obvious interactions
>   - check the residuals for any gross model assumption violation
>   - fit the model until satisfactory goodness of fit metrics are achieved
>   - review the distributional diagnostics in detail and make adjustments required to yield satisfactory results

## Part C — Application and Calculation

Source: [[Claim Layer]], [[Latent Claims]], [[Error in prediction]], [[Stochastic Loss Reserving]], [[Machine Learning]]

### C1. An insurer analyses claims subject to a policy limit. Assume the underlying claim size distribution $\Phi$ has $LEV(0;\Phi) = 0$, $LEV(200;\Phi) = 48$, $LEV(1000;\Phi) = 72$ and $LEV(\infty;\Phi) = 80$ (all in $000s). Compute the limit adjustment factor $S_{i,j}(L_a,L_b)$ for (a) $L_a = (0,200)$ and $L_b = (0,1000)$, and (b) $L_a = (0,200)$ and $L_b = (0,\infty)$. Interpret each.

> [!answer]- Answer
> - (a) $S_{i,j}((0,200),(0,1000)) = \dfrac{LEV(200;\Phi) - LEV(0;\Phi)}{LEV(1000;\Phi) - LEV(0;\Phi)} = \dfrac{48 - 0}{72 - 0} = 0.6667$
>   - Interpretation: the expected claims in the 0 to 200 layer are about two thirds of the expected claims in the 0 to 1000 layer
> - (b) $S_{i,j}((0,200),(0,\infty)) = \dfrac{48 - 0}{80 - 0} = 0.6000$
>   - Interpretation: the expected claims in the 0 to 200 layer are 60% of the expected ground-up, unlimited claims
> - The second figure is the "excess over" the layer $(0,200)$: $1 - 0.60 = 40\%$ of expected claims lie above 200

### C2. An insurer has cumulative incurred losses ($000s) at a policy limit of 500. It selects a basic limit $B = 100$, and $LEV(100;\Phi) = 24$, $LEV(500;\Phi) = 72$.

Observed at limit 500: AY1 = 1,500; 1,650; 1,716. AY2 = 1,440; 1,584. AY3 = 1,350.

(a) Restate the triangle to the basic limit. (b) Compute volume-weighted development factors, ultimates and total IBNR. (c) Explain why you cannot simply multiply the basic-limit IBNR by 3 to get back to the reported basis.

> [!answer]- Answer
> - (a) Restatement multiplier $= \dfrac{LEV(B;\Phi)}{LEV(L;\Phi)} = \dfrac{24}{72} = \dfrac{1}{3}$
>   - Restated triangle ($000s): AY1 = 500, 550, 572; AY2 = 480, 528; AY3 = 450
> - (b) $f_{1\to2} = \dfrac{550 + 528}{500 + 480} = \dfrac{1078}{980} = 1.10$; $f_{2\to3} = \dfrac{572}{550} = 1.04$
>   - AY1 ultimate $= 572 \times 1.04 = 594.88$
>   - AY2 ultimate $= 528 \times 1.04 = 549.12$
>   - AY3 ultimate $= 450 \times 1.10 \times 1.04 = 514.80$
>   - Latest diagonal $= 572 + 528 + 450 = 1,550$
>   - Total ultimate $= 594.88 + 549.12 + 514.80 = 1,658.8$
>   - Total IBNR $= 1,658.8 - 1,550 = 108.8$ ($000s), i.e. 22.88 + 21.12 + 64.80
> - (c) The restatement factor depends on the development age (via the maturity of the claim size distribution), so a single scalar multiplier applied in reverse will not reproduce the reported basis; relating development factors across cost levels and layers requires the claim size model and trend, and a triangle of trend indices is needed

### C3. An insurer has 40,000 policies in force. A policy review shows 6,200 of them are exposed to a newly recognised latent risk (bodily injury from a previously covered hazard). Management assesses the expected ultimate cost per exposed policy at $7,500. A market study puts market-wide latent losses at $400m and the insurer's estimated share of that market at 3.5%.

(a) Calculate a bottom-up reserve. (b) Calculate a top-down reserve. (c) Comment on the difference and on what happens once the latent claims have occurred.

> [!answer]- Answer
> - (a) Bottom up: review every policy to see whether it can be affected → 6,200 exposed policies
>   - Reserve $= 6,200 \times \$7,500 = \$46,500,000$
> - (b) Top down: consider market-wide losses → $400m \times 3.5\% = \$14,000,000$
> - (c) The two answers differ widely because the top-down approach ignores all the differences between the different insurers, whereas the bottom-up review reflects this insurer's actual policy mix
> - Once the latent claims have happened, the insurer will change pricing or change policy wording, so there should not be any further issue — the exposure is closed off rather than developing further

### C4. A GLM's prediction error has process variance of 2,500 and parameter variance of 1,500 ($000^2$). Model error is approximately 3/4 of total prediction error.

(a) Find total MSEP and the model error component. (b) Give the standard deviation of the forecast error. (c) Two candidate models produce MSEPs of 16,000 and 12,250, and AIC values of 340 and 318. Which do you select and why?

> [!answer]- Answer
> - (a) Process + parameter variance $= 2,500 + 1,500 = 4,000$, which is the remaining 1/4 of total prediction error
>   - Total MSEP $= 4,000 \times 4 = 16,000$; model error $= 16,000 - 4,000 = 12,000$ (i.e. 3/4)
> - (b) Standard deviation $= \sqrt{16,000} = 126.49$ ($000s)
> - (c) Select the second model on both counts: it has the smaller MSEP (MSEP estimates the tightness of a forecast around its target, so we want the smallest, and it takes into account the number of parameters), and AIC/BIC should be as low as possible
> - Model error is the component that is difficult to quantify, and can be partially mitigated by weighting the outputs of multiple models; structural changes and Black Swan (large or cat) event risk are further sources not captured by the arithmetic above

### C5. A chain-ladder run is fitted as an ODP GLM with log link and mean structure $\ln(\mu_{w,d}) = \alpha_w + \beta_d$, where $\alpha_1 = 8.00$, $\alpha_2 = 7.80$, $\alpha_3 = 7.60$, $\beta_1 = 0$, $\beta_2 = 0.15$, $\beta_3 = 0.29$.

(a) Compute fitted means for cells (1,1), (1,2), (1,3), (2,1), (2,2) and (3,1). (b) Compute the development factors implied and explain why they are identical across accident years. (c) Which data form and which distributional statement should accompany this fit?

> [!answer]- Answer
> - (a) $\mu_{w,d} = e^{\alpha_w + \beta_d}$
>   - $\mu_{1,1} = e^{8.00} = 2,981$; $\mu_{1,2} = e^{8.15} = 3,463$; $\mu_{1,3} = e^{8.29} = 3,984$
>   - $\mu_{2,1} = e^{7.80} = 2,441$; $\mu_{2,2} = e^{7.95} = 2,836$; $\mu_{3,1} = e^{7.60} = 1,998$
> - (b) $f_1 = e^{\beta_2 - \beta_1} = e^{0.15} = 1.1618$ (check: $3,463/2,981 = 1.1618$ and $2,836/2,441 = 1.1618$)
>   - $f_2 = e^{\beta_3 - \beta_2} = e^{0.14} = 1.1503$ (check: $3,984/3,463 = 1.1503$)
>   - The factors depend only on $\beta$, not on $\alpha_w$, which is exactly why the GLM reproduces the chain-ladder **mean** estimates
> - (c) The data are **incremental** loss triangles; the distribution is over-dispersed Poisson with a log link, and the variance is implied by the GLM distributional assumptions
> - Being parametric, this gives a likelihood, so bootstrap and Bayesian extensions are possible; dispersion parameter, residuals, deviance and diagnostics become available, and the model can be extended (trend, calendar effects, interactions)

### C6. There are 1,000 RBNS claims open at the end of period 0. Regression trees estimate the following transition probabilities for each open claim in each period: close with a payment 0.20, remain open and pay 0.55, remain open with no payment 0.25.

(a) Compute the expected number of payments in periods 1 to 5 and the expected total number of future payments. (b) What does this total represent, and why can the same approach not be applied claim by claim to IBNR claims?

> [!answer]- Answer
> - (a) Survival of a claim from one period to the next $= 0.20 + 0.25 = 0.45$
>   - Period 1: $1,000 \times 0.55 = 550$; open at end $= 450$
>   - Period 2: $450 \times 0.55 = 247.5$; open at end $= 202.5$
>   - Period 3: $202.5 \times 0.55 = 111.4$; open at end $= 91.1$
>   - Period 4: $91.1 \times 0.55 = 50.1$; open at end $= 41.0$
>   - Period 5: $41.0 \times 0.55 = 22.6$
>   - Total expected future payments $= 550 + 247.5 + 111.4 + 50.1 + 22.6 \approx 981.5$
>   - Equivalently $550 \times \dfrac{1 - 0.45^5}{1 - 0.45} = 550 \times 1.7846 \approx 981.5$
> - (b) This is the expected total number of future payments, i.e. the ultimate claim count implied by the RBNS population
> - For IBNR claims the future reported count is determined by chain ladder, so no individual claim-specific prediction is possible because there is no feature information; instead the required feature is simulated (implied by the use of a homogeneous marked Poisson process) so that claims can still be predicted as they evolve

### C7. Two stochastic models give central estimates and standard deviations for the same incremental cell: Model A mean $120,000 (sd $20,000); Model B mean $104,000 (sd $15,000). The combined estimate uses the same random variable for each model with weights 0.65 and 0.35.

(a) Compute the combined mean and standard deviation. (b) If the two models are instead run with independent random variables, describe how the combination would work. (c) State two practical obstacles to inducing correlation by location mapping.

> [!answer]- Answer
> - (a) Combined mean $= 0.65 \times 120,000 + 0.35 \times 104,000 = 78,000 + 36,400 = \$114,400$
>   - Combined variance $= (0.65 \times 20,000)^2 + (0.35 \times 15,000)^2 = 169,000,000 + 27,562,500 = 196,562,500$
>   - Combined sd $= \sqrt{196,562,500} \approx \$14,020$
> - (b) With independent random variables the weights are instead used to randomly select a model for each iteration by accident year; a calculated empirical correlation is almost always close to 0, which is not ideal, and contagion is not suited to the calculation (contagion between different lines of business)
> - (c) Location mapping drawbacks:
>   - it requires all business segments to use data triangles of precisely the same size, with no missing values or outliers, when comparing each location of the residuals
>   - the correlation of the original residuals is used in the model, so no other correlation assumptions can be used for stress testing the aggregate results
> - Resorting (copulas or the Iman-Conover algorithm) relaxes both: triangles may have different shapes and sizes, and different correlation assumptions may be employed

## Part D — Exam-Style Questions

Source: [[Stochastic Loss Reserving]], [[Claim Layer]], [[Latent Claims]], [[Machine Learning]], [[Model Validation]]

### D1. "Compare and contrast the Mack model, the ODP GLM chain-ladder model, the bootstrap and MCMC as methods for setting stochastic loss reserves, referring to the validation evidence."

> [!answer]- Answer
> - Common ground:
>   - Mack and the ODP GLM produce the same **mean** chain-ladder estimates
>   - both lead to a measure of prediction error for ultimate losses
> - Mack:
>   - distribution-free, no specified probability distribution, only mean and variance produced
>   - needs cumulative triangles; analytical formulas for process variance, parameter variance and MSEP
>   - strengths: minimal assumptions, closed-form MSEP, easy to implement
>   - weaknesses: cannot capture calendar effects, correlation, operational changes or skewness; on the CAS database it fails validation on incurred triangles because "the percentiles are not uniformly distributed"
> - ODP GLM:
>   - over-dispersed Poisson with log link, $\ln(\mu_{w,d}) = \alpha_w + \beta_d$; needs incremental triangles
>   - variance implied by the GLM distributional assumptions; supplies parameter estimates, dispersion parameter, residuals, deviance and diagnostics
>   - extensible to trend, calendar effects and interactions; a likelihood is available, enabling bootstrap and Bayesian extensions
> - Bootstrap (semi-parametric or parametric):
>   - resample residuals, refit on pseudo-triangles, then simulate future increments to capture parameter and process uncertainty
>   - semi-parametric uses empirical residuals and needs i.i.d. assumptions; parametric uses theoretical residuals and is easier to implement but needs more assumptions to be true
>   - estimates the entire distribution of the reserve, not just the MSEP
>   - weakness on CAS paid triangles: "both methods tend to overstate the range of expected outcomes", because the residual bootstrap assumes i.i.d. residuals and no calendar effects
> - MCMC:
>   - simulates from the posterior using priors and MCMC samplers such as Metropolis-Hastings or Gibbs (JAGS)
>   - four enhancements over bootstrap: accident-year correlation, skewed distributions allowing negative increments, payment-year trend, and changing settlement rates
>   - handles correlation, skewness, calendar trends and operational changes; produces the full posterior predictive distribution and validates better on CAS
>   - weaknesses: modeling choices, convergence diagnostics, computational cost

### D2. "Describe how you would build a stochastic reserving model for a set of loss triangles and take it through to a communicated result, including how you would combine it with other views."

> [!answer]- Answer
> - Data and fit:
>   - choose incremental loss triangles and enough data to compute residuals
>   - fit the ODP GLM (over-dispersed Poisson, log link, $\ln \mu_{w,d} = \alpha_w + \beta_d$); variance is implied by the distributional assumptions
> - Bootstrap for the predictive distribution:
>   - extract Pearson residuals; adjust using the hat matrix to equalize variance; resample with replacement; reconstruct pseudo-triangles; refit to give parameter uncertainty; simulate future increments using the ODP variance for process uncertainty; aggregate to a predictive distribution
> - Validation:
>   - review the link function, distribution choice, main effects and obvious interactions
>   - review residuals for gross assumption violations; review distributional diagnostics in detail and adjust
>   - test goodness of fit on a test set is generally not possible with triangles, because all the data is used to build them
> - Combining views:
>   - use the same random variable and weight the final incremental values, run models with independent random variables and select by accident year, or apply correlation
>   - correlation via location mapping preserves the original residual correlation and is easy, but needs identically shaped complete triangles and offers no alternative correlation assumptions; resorting with copulas or Iman-Conover allows different triangle shapes, sizes and correlation assumptions
> - Presentation: stochastic models give a full probability distribution and a standard deviation for the unpaid claims, allowing process risk to be separated from model risk — but recognise model risk and over-confidence, data and computational requirements, and communication difficulty
> - Complement with scenario testing (transparent, low data burden, but not probabilistic, subject to selection bias and incomplete coverage) and alternative assumption sets (simple, quick, useful for governance, but only a partial view of uncertainty and possibly a false sense of precision)

### D3. "Describe the claim layer (basic limit) approach to developing claims patterns on limited data, including the machinery required and the practical issues."

> [!answer]- Answer
> - Definition: $L(d,p)$ is a claims layer truncated from below at $d$ and censored from above at $p$
> - Claim size model:
>   - LEV = limited expected value; $\Phi_{i,j}$ = assumed distribution
>   - $S_{i,j}(L_a,L_b) = \dfrac{LEV(p_a;\Phi) - LEV(d_a;\Phi)}{LEV(p_b;\Phi) - LEV(d_b;\Phi)}$, equivalently $E[C_{i,j}L_a \mid C_{i,j}L_b]$ — a ratio of expectations
>   - $S(a,b)$ represents the ratio of expectations of claims between layer $L_a$ and $L_b$
> - Step 1: select a basic limit $B$, the threshold at which the data is believed sufficiently credible for developing claims development patterns
> - Step 2: restate the observed amounts onto the basic limit using $E[C_{i,j}B' \mid C_{i,j}L] = C_{i,j}L \times \dfrac{LEV(B;\Phi)}{LEV(L;\Phi)}$, adjusting for both cost level and limit differences
> - Step 3: link the layers — development factors at different cost levels and different layers are related through the claim size model and trend
> - Trend cautions: development- or calendar-period trend is often not considered; if trend is estimated from limited or deductible data it must first be put on a ground-up unlimited basis using the claim size model; in theory the trend factor differs for every triangle value
> - Issues (not too bad): requires selection of a basic limit (usually taken as credible enough), requires an ultimate claim size model, and requires the triangle to be adjusted to a basic limit and common cost level
> - Issues (bad): claim size models at maturities prior to ultimate are generally not available, and a triangle of trend indices must be calculated to implement a development method analysis

### D4. "What are latent claims, and how should an actuary assess them? Comment on where machine learning and model validation fit into reserving practice."

> [!answer]- Answer
> - Definition: a latent claim is a risk **not specifically considered when the policy was written**; types include bodily injury, pharmaceutical claims and environmental damage
> - Assessment routes:
>   - top down — consider market-wide losses; ignores all differences between the different insurers
>   - bottom up — review every policy to see whether it can be affected by the latent claims
>   - future — once the latent claims have happened the insurer will change pricing or policy wording, so there should not be any further issue
> - Machine learning in reserving:
>   - the goal is to look at individual claims rather than aggregate data, overcoming the neglect of individual claim behaviour by aggregate methods and allowing dynamic (stochastic) features
>   - regression trees (CART) estimate transition probabilities for staying open or closing and for generating a payment; iterating these forward gives the expected total number of future payments, i.e. the ultimate claim count
>   - RBNS claims are handled claim by claim; for IBNR claims the future reported count comes from chain ladder, so features must be simulated (implied by a homogeneous marked Poisson process) since no feature information exists yet
> - Model validation:
>   - analyse the distributional assumptions, the link function and model choices
>   - analyse goodness of fit by reviewing residuals to get an idea of the error distribution
>   - test-set goodness of fit is generally not possible with triangles because all data is used to build them
>   - checklist: appropriate link function; reasonable distribution selection; main effects and obvious interactions fitted; residuals checked for gross assumption violations; fit until satisfactory goodness of fit metrics are achieved; distributional diagnostics reviewed in detail with adjustments made