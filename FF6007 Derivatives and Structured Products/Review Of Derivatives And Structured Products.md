# Review Of Derivatives And Structured Products

## Introduction

- Risk management (hedging & insurance), speculation, value creation

## Futures and Forward

- Contract
  - OTC vs Exchange
  - Margin: net basis vs gross basis
  - Convergence of futures to spot (not forward)
- Pricing
  - Rely on no arbitrage assumption
  - If short sales are not possible, still holds
  - Value of forward contract: $f = S_t - Ke^{-rt}$
  - A strong positive correlation between interest rates and the asset price implies the futures price is slightly higher than the forward price
- Forward Rate Agreement
  - Buyer receives floating rate (settlement rate) and pays fixed rate (contract rate)
  - Settlement sum = (settlement rate - contract rate) * amount * (day / day per year) / (1 + settlement rate * (day / day per year))
- Hedging strategies using futures
  - Problem: mismatch
  - Hedge: $V_T = S_T + (F_0 - F_T) = S_0 + (F_0 - S_0) - (F_T - S_T) = S_0 + (B_0 - B_T)$
    - Convert price change of underlying asset to price change of basis risk
  - Minimum variance hedging ratio: $\Delta V = \Delta S + h \Delta F$, $h = \rho \frac{\sigma_{\Delta S}}{\sigma_{\Delta F}}$
  - Hedge an equity portfolio
    - Reason: Desire to be out of the market for a short period of time, Desire to hedge systematic risk
    - $h = \beta$

## Swaps

- Interest rate swap
  - Applications: risk management, trading, creating synthetic instruments, others

## Options Markets

- Properties of stock option prices
  - Value: intrinsic value $\max{0, S_0 - K}$; time value (extrinsic value)
- Option pricing
  - $Se^{-\delta t} \ge C_a \ge Se^{-\delta t} - Ke^{-rt}$, $S \ge C_e \ge S - K$, $K \ge P_a \ge K - S$, $Ke^{-rt} \ge P_e \ge Ke^{-rt} - Se^{-\delta t}$
  - Early exercise of American options
    - American call = European call
    - American put, early exercise when dividend yield > interest cost
- Option trading
  - Naked: Bull call, bear put, straddle (strap: buy more call than put, strip: buy more put than call), strangle

## Option Pricing

## Volatility

- Volatility is not a constant: volatility smile
- Stock return
  - The left tail is heavier than the normal distribution, The right tail is less heavy than the normal distribution
  - Negative correlation between stock price and implied volatility
  - Volatility on volatility: 1m is higher, need compensation

## Option Greeks

## Exotics Options & Structured Products

- Exotics option
  - Barrier option
  - Binary option
  - Basket option: option on a portfolio
  - Worst-of and best-of option
- Structured products
  - Major risks: Issuer Risk, Market Risk, Liquidity Risk, Other risks

