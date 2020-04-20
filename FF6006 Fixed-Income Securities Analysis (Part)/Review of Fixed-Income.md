# Review of Fixed-Income

## Session 1: Bonds and Mone-Market Instruments

- Types of fixed-income securities:
  - Bonds
  - Money-market instruments

### Bonds

- Termiology
  - The day-count type: Actual/Actual, Actual/365, Actual/360, 30/360
  - Quoted price: usually **clean price**, that is, its **gross price** minus **accrued interest**.
  - Bond quote spread: spread over a given benchmark bond. Corporate bond are usually quoted in spread.
  - Mid price: average of bid price and ask price. So as mid yield.

- Floater and Inverse-Floater
  
- To hedge: $V_F k_F = V_{IF} k_{IF}$
  
- Inflation-Indexed Bonds

  $Coupon_t = Face\ value \times Real\ coupon \times \frac{CPI_t}{CPI_{initial}}$

  $Redemption\ value = Face\ value \times \frac{CPI_t}{CPI_{initial}}$

### Money-Market Instruments

- T-bills
  - yield on a discount basis (US, UK, Euro zone): $y_d = \frac{F - P}{F} \times \frac{B}{n}$, $P = F \times (1 - \frac{n \times y_d}{B})$
  - yield on a money-market basis (Japan):$y_m = \frac{F - P}{P} \times \frac{B}{n}$, $y_m = \frac{B \times y_d}{B - n \times y_d}$, $P = \frac{F}{1 + \frac{n \times y_m}{B}}$
- Certificates of deposit: debt instruments issued by banks
- Bankers' accpetances
- Commercial papers
- Repo: lend bonds in exchange for a loan of money, based on Actual/360 basis

## Session 2: Bond Prices and Yields

- Bond pricing: $P^T = B^T \times CF$

- Different rates and yields

  - Bond equivalent yield: nominal rate compounding semiannually

  - Current yield: $y_d = \frac{cN}{P}$

  - Total return rate: similar to MIRR

  - Bond par yield:
    $$
    c(n) = \frac{1 - \frac{1}{(1 + R(0, n))^n}}{\sum_{i=1}^{n}{\frac{1}{(1 + R(0, i))^i}}}
    $$

  - Instantaneous forward rate: $f(t, s) = \lim_{T - s \rightarrow 0}{F^c(t, s, T - s)}$ where $F^c(t, s, T - s) = \ln{(1 + F(t, s, T - s))}$

## Session 3: Empirical Properties and Classical Theories of the Term Structure

- Properties of the term structure
  - Interest rates are rarely negative
  - Mean-reversion model: $dr(t) = a[b - r(t)]dt + \sigma dW(t)$
  - Changes of interest rates are positively correlated
  - Short-term rates are more volatile than long-term rates
  - PCA model: 3 main factors
- Classical theories of the term structure
  - Pure expectation theory
  - Pure risk premium theory
    - Liquidity premium theory
    - Preferred habitat theory
  - Market segmentation theory
  - Biased expectations theory

## Session 4: Deriving the Zero-Coupon Yield Curve

### Deriving Treasury Zero-Coupon Rates

- Direct method

  - Theoretical method: $B = F^{-1}P$

  - Bootstrapping method: extending 1-year zero yield curve by using interpolation

    - Linear interpolation: $R(0, y) = \frac{(z - y)R(0, x) + (y - x)R(0, z)}{z - x}$

    - Cubic interpolation
      $$
      \left(\begin{matrix} 
      	a \\ b \\ c \\ d 
      \end{matrix}\right)
      =
      \left(\begin{matrix} 
      	t_1^3 & t_1^2 & t_1 & 1 \\ 
      	t_2^3 & t_2^2 & t_2 & 1 \\ 
      	t_3^3 & t_3^2 & t_3 & 1 \\
      	t_4^3 & t_4^2 & t_4 & 1
      \end{matrix}\right)
      \left(\begin{matrix} 
      	R(0, t_1) \\ R(0, t_2) \\ R(0, t_3) \\ R(0, t_4)
      \end{matrix}\right)
      $$

  - Regression approach

- Indirect method: $\hat{\beta^*} = \arg{\min_{\beta}{\sum_{j=1}^n{(P_t^j - \hat{P_t^j})^2}}}$ where $\hat{P_t^j} = \sum_s{F_s^{(j)}B(t,  s)}$

  - Spline function

    - Condition: $B(0) = 1$, 0th, 1st and 2nd derivative.
    - Two-phase polinomial spline: $B(s) = 1 + c_0 s + b_0 s^2 + a_0 s^3 + (a_1 - a_0) [\max{(s - break\ point, 0)}]^3$

  - Nelson-Siegel model
    $$
    R^c(0, \theta) = \beta_0 + \beta_1 \left[ \frac{1 - \exp{(-\frac{\theta}{\tau_1})}}{\frac{\theta}{\tau_1}} \right] + \beta_2 \left[ \frac{1 - \exp{(-\frac{\theta}{\tau_1})}}{\frac{\theta}{\tau_1}} - \exp{(-\frac{\theta}{\tau_1})} \right] \\+ \beta_3 \left[ \frac{1 - \exp{(-\frac{\theta}{\tau_2})}}{\frac{\theta}{\tau_2}} - \exp{(-\frac{\theta}{\tau_2})} \right]
    $$

  - Pros: save parameters, robust and stable

  - Cons: lack flexibility, can't explain some shapes.

### Deriving Interbank Zero-Coupon Rates

- Choose the base

  - Money-market rates: convert Libor (Actual/360) to zero-coupon rates (usually Actual/365)

    1-month Libor: $R(0, 1/12) = (1 + \frac{31}{360} \times 2.5\%)^{365/31} - 1$

  - Future contracts: convert Libor with Libor contract to zero-coupon rates

    3-month Libor & Libor contract: $R(0, 6/12) = [(1 + \frac{92}{360} \times 3\%)(1 + \frac{92}{360})]^{365/184} - 1$

  - Swaps: $1 = \frac{SR(2)}{1 + R(0, 1)} + \frac{1 + SR(2)}{(1 + R(0, 2))^2}$

### Term Structure of Credit Spreads

- Logic: spread = risky zero yield - risk free zero yield
- Method: disjoint method, joint method

## Session 5: Hedging Interest-Rate Risk with Duration

- Basics of interest-rate risk
  - Reinvestment risk: positively related to longer maturity and higher coupon rate
  - Capital gain risk
- Duration
  - Implication: deal with one single risk variable, i.e., the YTM.
  - Macaulay duration: weighted average maturity, the elasticity of bond price
  - Duration, $Duration and Modified Duration
    - $D = -(1 + y)\frac{P'(y)}{P(y)}$, $MD(P(y)) = - \frac{P'(y)}{P(y)}$, $\$Dur = P'(y)$
    - $MD = \frac{D}{1 + y}$, $\$Dur = -\frac{D}{1 + y} \times P = -MD \times P$
    - $Absolute\ P\&L \approx \$Dur \times \Delta y$, $Relative\ P\&L \approx -MD \times \Delta y$
    - Basis point value (BPV): set $\Delta y = 0.01\%$
    - If compounding is not annual, replace $1 + y$ by $1 + y/k$.
    - Time to maturity increase, $duration decrease.
    - $D_p = \sum_{i=1}^n{w_i D_i}$ only true when yield curve is flat.
- Hedging with duration
  - $\phi = -\frac{\$Dur(P(y))}{\$Dur(H(y_1))} = - \frac{P(y) MD(P(y))}{H(y_1) MD(H(y_1))}$
- Immunization
  - Goal: ensure to have an amount of Q dollars in the future
  - $\Delta V_O = \frac{dV_O}{dy} \Delta y = - \frac{D}{1 + y} V_O \Delta y = -\frac{T}{1 + y} \frac{Q}{(1 + y)^T} \Delta y$, $\Delta V_B = - \frac{D}{1 + y} V_B \Delta y = -\frac{T}{1 + y}$
  - $T = D$

- Assumptions
  - Small changes in yield
  - The yield curve is flat at the origin
  - The yield curve is flat at each point in time

## Session 6: Beyond Duration

- Larger changes in yield

  - $dP(y) \approx \$Dur(P(y)) dy + \frac{1}{2} \$Conv(P(y)) (dy)^2 = -MD(P(y)) \cdot P(y) dy + \frac{1}{2}RC(P(y)) \cdot P(y) (dy)^2$

  - $RC = \frac{1}{(1 + y)^2} \sum_{i=1}^{t}{i(i+1)\frac{F_i}{(1 + y)^i} \frac{1}{P}}$

  - Properties of convexity

    - The lower the coupon rate, the higher its convexity and the lower its $convexity
    - The longer the maturity, the higher its convexity and $convexity
    - The lower the YTM, the higher the convexity and $convexity
    - $RC_p = \sum_{i=1}^n{w_i RC_i}$

  - Hedging method (immunization needs 2, self financing needs 3)
    $$
    \left[ \begin{matrix}
    	H_1(y_1) & H_2(y_2) & H_3(y_3) \\
    	H_1(y_1) \cdot MD(y_1) & H_2(y_2) \cdot MD(y_2) & H_3(y_3) \cdot MD(y_3) \\
    	H_1(y_1) \cdot RC(y_1) & H_2(y_2) \cdot RC(y_2) & H_3(y_3) \cdot RC(y_3)
    \end{matrix} \right]
    \left[ \begin{matrix}
    	\phi_1 \\ \phi_2 \\ \phi_3
    \end{matrix} \right]
    =
    \left[ \begin{matrix}
    	-P(y) \\ -P(y) \cdot MD(y) \\ -P(y) \cdot RC(y)
    \end{matrix} \right]
    $$

- Non flat yield curve

  - Duration and convexity hedging is only approximate

- Non parallel shifts

  - Implication: $P_t$ is determined by $m$ risk factors, i.e., $P_t = P(R_t^1, \cdots, R_t^m)$
  - $P_t^* = P_t + \sum_{j=1}^{m}{\phi_t^j H_t^j}$, let $dP_t^* = 0$ we have $\sum_{i=1}^{m}{\left( \frac{\partial P_t}{\partial R_t^i} + \sum_{j=1}^{m}{\phi_j \frac{\partial H_t^j}{\partial R_t^j}} \right) dR_t^i} = 0$.
  - $\Phi_t = (H_t')^{-1} \cdot P_t'$
  - For cross-hedge risk:
    - If $P_t = P(R_t)$ and $H_t = H(R_t')$,$dP_t^* \approx \frac{\partial P_t}{\partial R_t} dR_t + \phi \frac{\partial H_t}{\partial R_t} dR_t'$, so $dR_t$ and $dR_t'$ may not be the same.
    - Set $R_t' = f(R_t)$, we can get $\phi_t = - (\frac{\partial P_t}{\partial R_t}) / (\frac{\partial H_t}{\partial R_t'}f'(R_t))$
  - Application
    - PCA model
    - Nelson-Siegel model
      - $D_0 = \frac{\partial P_0}{\partial \beta_0} = -\sum_{i}{\theta_i F_i e^{-\theta_i R^c(0, \theta_i)}}$
      - $D_1 = \frac{\partial P_0}{\partial \beta_1} = -\sum_{i}{\theta_i \left[ \frac{1 - \exp{(-\frac{\theta_i}{\tau_1})}}{\frac{\theta_i}{\tau_1}} \right] F_i e^{-\theta_i R^c(0, \theta_i)}}$
      - $D_2 = \frac{\partial P_0}{\partial \beta_2} = -\sum_{i}{\theta_i \left[ \frac{1 - \exp{(-\frac{\theta_i}{\tau_1})}}{\frac{\theta_i}{\tau_1}} - \exp{(-\frac{\theta_i}{\tau_1})} \right] F_i e^{-\theta_i R^c(0, \theta_i)}}$
    - Vasicek 1 model: $R^c(0, \theta_i) = G(0, \theta_i; u) = L_0 - S_0 \frac{1 - e^{-a\theta_i}}{a\theta_i} + \gamma_0 \frac{(1 - e^{-a\theta_i})^2}{4 \cdot a\theta_i}$
      - $D_L = \frac{\partial P_t}{\partial L_t} = -\sum_{i}{\theta_i F_i e^{-\theta_i R^c(t, \theta_i)}}$
      - $D_S = \frac{\partial P_t}{\partial S_t} = -\sum_{i}{\theta_i \frac{1 - e^{-a\theta_i}}{a\theta_i} F_i e^{-\theta_i R^c(t, \theta_i)}}$
      - $D_\gamma = \frac{\partial P_t}{\partial \gamma_t} = -\sum_{i}{\theta_i \frac{(1 - e^{-a\theta_i})^2}{4 \cdot a\theta_i} F_i e^{-\theta_i R^c(t, \theta_i)}}$

## Session 7: Passive Fixed-Income Portfolio Management

- Ideal replication method: duplicate the target index by holding all its securities in exact proportions

  - Disadvantages: costly, many bonds are thinly traded, the index changes regularly

- Stratified sampling method: represent every important component of index with several securities

- Tracking error minimization method: create minimum tracking error portfolios

  - Goal: find $R_P = \sum_{i=1}^{N}{w_i R_i}$ that $\min_{w_1, \cdots, w_N}{Var(R_P - R_B)} = w_p'Vw_p - w_p' \sigma_{iB} + \sigma_B^2$, s.t. $w_p'i = 1$

  - Can't use regression, as lack of the constraint

  - Closed form solution: $w_p' = \sigma_{iB}'V^{-1} + \frac{1 - i'V^{-1}\sigma_{iB}}{i'V^{-1}i}i'V^{-1}$

  - $TE = \sqrt{Var(R_P - R_B)}$

  - Bond return covariance matrix estimation

    - Sample covariance matrix: $V = \frac{X'X - T \cdot X'X}{T - 1} = \frac{x'x}{T - 1}$

    - Equal correlation structure:
      $$
      V = 
      \left[ \begin{matrix}
      	1 & \rho & \rho \\
      	\rho & \ddots & \rho \\
      	\rho & \rho & 1
      \end{matrix} \right]
      \otimes
      \left[ \begin{matrix}
      	\sigma_1^2 & \sigma_i \sigma_j & \cdots \\
      	\sigma_i \sigma_j & \ddots & \vdots \\
      	\vdots & \cdots & \sigma_N^2
      \end{matrix} \right]
      $$
      where $\rho = \bar{\rho} = \frac{1}{N(N - 1)} \sum_{i=1}^N{\sum_{j=1 \\i \ne j}^N{\rho_{ij}}}$

    - With decay: $V = \frac{1}{T - 1}x'(x \otimes p)$ where $p_t = \frac{\lambda^{T - t + 1}}{\sum_{t=1}^T{\lambda^t}}$

    - Factor-based covariance matrix

      - Set $h_t = \alpha + \beta m_t + \varepsilon_t$, then 
        $$
        V = \sigma_m^2 \vec{\beta} \vec{\beta}' + 
        \left[ \begin{matrix}
        	\sigma_{\varepsilon_1}^2 & 0 & \cdots & 0 \\
        	0 & \sigma_{\varepsilon_2}^2 & \cdots & 0 \\
        	\vdots & \vdots & \ddots & \vdots \\
        	0 & 0 & \cdots & \sigma_{\varepsilon_N}^2
        \end{matrix} \right]
        $$
        where $\sigma_m^2 = N + \sum_{i \ne j}{\rho_{ij}}$, also $\sigma_m^2 = N + \bar{\rho} \cdot N(N-1)$

- Factor-based replication method

## Session 8&9: Active Fixed-Income Portfolio Management

### Market Timing

- Idea: bet on interest-rate predictions
- Type
  - bet on no changes in the yield curve (riding the yield curve)
  - bet on interest rate level (naive or roll-over strategies)
  - bet on both slope and curvature movements of the yield curve (butterfiles)
- Tool: scenario analysis
  - Evaluation of break-even point from which the stragety will start making or losing money
  - Assessment of the risk that the expectations are not realized
- Riding the yield curve
  - Strategy: buy longer maturity bonds, then sell
- Naive or roll-over stratigies
  - Strategy: when rates are expected to decrease, lengthen the \$duration or modified duration; when rates are expected to increase, shorten the \$duration or modified duration.
- Specific changes in the yield curve
  - Bullet: 1 maturity
  - Barbell: 1 long maturity and 1 short maturity
    - A barbell is nore convex than a bullet with the same duration
  - Ladder: equal amounts with different maturities
  - Butterfly: combination of a barbell (wing) and a bullet (body)
    - Idea: cash neutral, \$dur = 0, positive convexity, can benefit from parallel shift
    - Types
      - Cash- and \$duration-neutral weighting: cash = 0, ​\$dur = 0
      - Fifty-fifty weighting: cash = 0, $q_s D_s = q_l D_l = \frac{-q_m D_m}{2}$, deal with small steepening and flattening movements
      - Regression weighting: cash = 0, $q_s D_s = \beta q_l D_l$ where $y_l - y_m = \alpha + \beta(y_m - y_s)$, considering short-term rates are more volatile
      - Maturity weighting: cash = 0, $q_s D_s = -q_m (\frac{M_m - M_s}{M_l - M_s})D_m$, $q_l D_l = -q_m (\frac{M_l - M_m}{M_l - M_s})D_m$,weight on maturities
    - Measure the performance and risk
      - Total return measure

### Bond Picking

- Idea: bet on market inefficiency







## Excel

Delta of days (actual basis): `days(start_date, end_date)`

Delta of days (360 basis): `days360(start_date, end_date)`

Fraction of a year: `yearfrac(start_date, end_date, [basis])`

