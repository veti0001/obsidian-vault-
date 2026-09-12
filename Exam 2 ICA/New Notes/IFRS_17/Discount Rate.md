## Definition

- **Discount rate**: Rate used to discount the estimates of future cash flows, which is consistent with the timing, liquidity and currency of the insurance contract cash flows. A discount rate may be a single rate, or a curve of rates varying by duration.
- **Illiquidity premium**: Adjustment made to a liquid risk-free yield curve to reflect differences between the liquidity characteristics of the financial instruments that underlie the (risk-free) rates observed in the market and the liquidity characteristics of the insurance contracts.
- **Reference portfolio**: A portfolio of assets used to derive discount rates based on current market rates of return, adjusted to remove returns related to risk characteristics embedded in the portfolio that are not inherent in insurance contracts.

## Discount Rate

- Characteristics:
	- reflect the time value of money, the characteristics of the cash flows and the liquidity characteristics of the insurance contracts;
	- be consistent with observable current market prices (if any) for financial instruments with cash flows whose characteristics are consistent with those of the insurance contracts, in terms of, for example, timing, currency and liquidity; and
	- exclude the effect of factors that influence such observable market prices but do not affect the future cash flows of the insurance contracts
- Determination:
	- Bottom-up
		- liquid risk-free yield curve is adjusted to reflect the differences between the liquidity characteristics of the market and the portfolio
		- Bottom-Up Discount Rate = Risk-Free Rate + Illiquidity premium
		- risk free rate: look at Canadian bond
		- how to estimate Illiquidity premium: 
			- Using a reference portfolio and determining its illiquidity premium using top-down techniques; and
			- Comparing yields on illiquid and liquid assets, both with same or similar degree of credit risk.
		- #### Advantages
			- availability of risk-free yield curves
		- #### Disadvantage
			- need to derive an illiquidity premium
	- Top-down
		- yield to maturity of a reference portfolio of assets is adjusted to eliminate any factors that are not relevant to insurance contracts.
		- Remove the following risks:
			- liquidity
			- investment risk (e.g., credit risk, market risk)
				- Credit risk: includes default risk and downgrade risk.
			- amount, timing and uncertainty of cash flows
				- assess the consistency of the timing of payments between the assets in the reference portfolio and the insurance contract liabilities
			- currency risk
				- select a reference portfolio made up of investments denominated in the same currency as the insurance contracts
		- Top-Down Discount Rate = Reference Portfolio Rate – Credit Risk, Market Risk & Other Adjustments
		- Selection of reference portfolio: We should aim to have portfolio with similar assets to have the least possible adjustment needed
		- #### Advantages
			- does not require the explicit derivation of an illiquidity premium
		- #### Disadvantage
			- potential complexity of the derivation of a reference portfolio rate and applicable adjustments
	- Hybrid:
		- IFRS 17 Discount Rate = Risk-Free Rate + Reference Portfolio Illiquidity premium
		- Reference Portfolio Illiquidity premium = Top-Down Discount Rate – Risk-Free Rate
		- #### Advantages
			- blend robust illiquidity premium models with readily available Canadian risk-free yield curve
- No need to estimate discount rate curve

## Liquidity of P&C contracts liabilities

- Discount rate should reflect the liquidity characteristics of the insurance contracts
- Liquidity arise from:
	- call or put options in the instruments 
	- marketability of the instruments
- Contract attribute that may affect the liquidity:
	- Exit value
	- Exit cost
	- Inherent value / value build-up:
- LRC is generally liquid : Ability of policyholder to cancel policy before expiry date and to receive value without significant exit costs.
	- Reinsurance contract held : the liquidity of the LRC is evaluated on the basis of the ability of the purchaser of the reinsurance to cancel the reinsurance contract before its expiry date and to receive value./Treaty-specific cancellation provisions are considered for the purposes of assessing liquidity

- LIC is generally illiquid: Ability for the policyholder to obtain the exit value in advance of “normal” payment dates.
	
## Reference Curve

- 2 different yield curve could be used ( 1 for liquid assets and one for illiquid assets)
- 1 yield curve could also be used
	- Fewer yield curves to manage
	- Single view of the profitability of portfolios
- Up to 30 years from now use the following
	- liquid curve: risk-free rate + 90% of provincial bonds spread;
	- illiquid curve: risk-free rate + 0.50% + X% of Canadian investment grade bonds spread, where X% = 80% in years 1-3, 75% in year 4, and 70% in years 5+.
	- illiquid curve uses uses A and BBB bonds