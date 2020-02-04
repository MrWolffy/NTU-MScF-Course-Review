# Review of Corporate Finance

## Structure

- How to determine value?
	- TVM (L2 & L3)
	- Risk and return (L4)
	- Models for valuing bonds and stocks (L5 - L7)
- How do companies conduct their business?
	- Investing (L8 & L9)
	- Raising capital (L10 & L11)

## Lecture 1

### Chapter 1

- forms of business organization
	- proprietorship
	- partnership
	- corporation
- the main financial goal: creating value for investors
	- long-run stock price maximization
	- intrinsic value maximization
	- shareholder wealth maximization
	- take long-run view of operations
	- why managers will have short-run focus
		- bonus for engaging in risky transactions
		- bonus tied solely to this year's earnings
		- stock options
- determinants of value
	- cash flow
	- risk 
- stockholder-manager conflicts
	- compensation packages
	- direct stockholder intervention
	- managers' response
- stockholder-debtholder conflicts
	- risk bearing
	- use of additional debt

### Chapter 2

- capital allocation process
	- direct transfers: securities (stocks or bonds)
	- through investment bankers
	- through a financial intermediary
- types of financial markets
	- money market: short-term, high liquid debt securities
	- capital market: intermediate- or long-term debt and corporate stocks

## Lecture 2

Nothing new

## Lecture 3

Nothing new

## Lecture 4

### Chapter 7

- factors affecting the cost of money
	- production opportunities
	- time preferences for consumption
	- risk
	- inflation

$$r = r^* + IP + DRP + LP + MRP$$

- for $$r^*$$
	- can be measured by short-term US Treasury securities
	- affected by (1) expected earnings and (2) time preferences
- for $$r_{RF} = r^* + IP$$
	- no observable risk free rate, except short-term Treasury Inflation Protected Security (TIPS)
- for $$IP$$
	- expectation of future, not in the past
- for $$MRP$$
	- reflects interest rate risk
	- reinvestment risk: the risk that principal can't be invested at the same IR

### Chapter 8

- measure stand-alone risk
	- standard deviation
	- the coefficient of variation: measures the risk per unit of return
- measure risk in a portfolio
	- most investors are faced with market risk, as they can buy mutual funds
	- what appears to be a risky investment when viewed on a stand-alone basis may not be very risky when viewed within the context of the company as a hole

## Lecture 5

- features of bond
	- Sinking fund: provision to pay off the loan over its life rather than all at maturity 
	- warrants: option to exchange bonds for stock at a stated price
- YTM = expected rate of return, only when
	- no default risk
	- the bond cannot be called

## Lecture 6

- PEG method: $$\frac{P/E}{g}$$

## Lecture 7

$$r_{WACC} = w_d r_d(1-T) + w_p r_p + w_c r_s$$

- for weights
	- use target capital structure
- for $$r_d$$
	- $$r_d$$ is the interest rate of **new** debt
	- can use the YTM of outstanding debt, or ask the banker
		- YTM of long-term debt is often used because new capital is used to fund long-term projects
- for $$r_p$$
	- the rate of return investors require on preferred stock
	- often $$D_p / P_p$$
- for $$r_s$$
	- $$r_s$$ is the cost of retained earnings
		- not free, because the opportunity cost of using retained earnings is investing in other projects
		- how to calculate
			- CAPM
			- bond yield + risk premium
			- DCF, i.e., $$\frac{D_1}{P_0} + g$$
			- use 1 if confident, or use a weighted average of 3
	- $$r_e$$ is the cost of new common stock, higher because of flotation cost
		- by DCF: $$\frac{D_0}{P_0(1-F)} + g$$
		- calculate the gap between $$r_s$$ and $$r_e$$ by DCF
		- $$r_e = r_s + gap$$ where $$r_s$$ is the final one
		- when must external equity be used?
			- max capital raised before new stock = retained earnings / propotion of equity
- factors that affect the WACC
	- cannot control: interest rates, stock price, tax rates
	- can control: capital structure, dividend payout ratio (affects the amount of retained earnings), capital budget decision rule (affects risk)
- each project should have own hurdle rate, not WACC

## Lecture 8

- criterion
	- NPV: calculated with project's risk-adjusted WACC
	- IRR: compare with project's WACC
- reinvestment rate assumptions
	- NPV: at project's risk-adjusted WACC
	- IRR: at IRR
	- if firm has good access to external capital, can use WACC, or should use IRR
- when NPV and IRR conflict
	- timing differences
	- size differences
	- should use NPV
- why payback and discounted payback are useful
	- provide information of liquidity and risk

## Lecture 9

- how to identify free cash flow

```
EBIT = sales - variable costs - fixed costs - depreciation
free cash flow = EBIT(1-T) + depreciation - capex - change in NOWC
```

- three types of risk
	- stand-alone risk
	- corporate risk
	- market risk: most important, but hard to quantify
- evaluating projects with unequal lives
	- calculate NPV
	- amortize NPV into project's life
	- compare annual payment

## Lecture 10

- two new dimensions of risk
	- business risk: risk if no debt is used
		- measure: sd of return on invested capital (ROIC)
		- ROIC = EBIT(1-T) / total invested capital
		- operating leverage: how much fixed cost is
			- (sales - VC) / (sales - (VC + WC))
	- financial risk: risk brought by using debt
		- financial leverage: how much debt is used
		- when debt ratio increases, EPS will increase first, then decrease
- the optimal capital structure is not the one that max EPS, but lower to max stock price
- capital structure max stock price = capital structure min WACC
- Hamada equation: $$\beta_L = \beta_U[1 + (1 - T)(D/E)]$$
	- use CAPM to get $$\beta_U$$, which is beta of asset
	- get $$\beta_L$$, which is beta of equity
	- use CAPM to get cost of equity
- MM proposition
	- assumptions
		- no brokerage costs
		- no taxes
		- no bankruptcy costs
		- investors can borrow at the same rate as corporations
		- pertect information
		- EBIT is not affected by using debt
	- conclusion: no matter how a firm finances its operations

## Lecture 11

- high or low dividend?
	- MM dividend irrelevance theory: doesn't matter
	- bird-in-the-hand theory: high dividend
	- tax preference theory: low dividend
- residual dividend model

```
dividend = net income - (target equity ratio * total capital budegt)
```

- setting dividend policy
- dividend reinvestment plan
- open market purchase plan
- new stock plan
