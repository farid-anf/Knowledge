The **Black-Scholes model** relies on several assumptions to derive the pricing formulas for European call and put options. These assumptions are:

---

### 1. **Efficient Market**
   - The market is frictionless: no transaction costs, taxes, or bid-ask spreads.
   - All investors have access to the same information and act rationally.

---

### 2. **Underlying Asset Dynamics**
   - The price of the underlying asset follows a **geometric Brownian motion** with constant drift (\( \mu \)) and constant volatility (\( \sigma \)):
     $$
     dS = \mu S dt + \sigma S dW
     $$
     where:
     - \( dW \): A Wiener process (random walk)
     - \( \mu \): The expected return of the asset (not directly used in the model)
     - \( \sigma \): The volatility (constant)

---

### 3. **Risk-Free Rate**
   - The risk-free interest rate (\( r \)) is constant over the option's life.
   - Investors can borrow and lend at this risk-free rate.

---

### 4. **No Dividends**
   - The underlying asset pays no dividends or other cash flows during the life of the option.
   - Extensions of the Black-Scholes model address dividend-paying assets.

---

### 5. **Option Type**
   - The option is a **European option**, meaning it can only be exercised at expiration.

---

### 6. **No Arbitrage**
   - Arbitrage opportunities do not exist; the market enforces the law of one price (two identical assets have the same price).

---

### 7. **Continuous Trading**
   - Trading of the underlying asset occurs continuously, allowing for perfect hedging.

---

### 8. **Lognormal Price Distribution**
   - The underlying asset price is lognormally distributed because its returns are normally distributed.

---

### 9. **Perfect Liquidity**
   - The underlying asset can be bought or sold in any quantity without affecting its price.

---

These assumptions are idealized and often do not hold perfectly in real markets, which can lead to deviations between theoretical and actual option prices. Extensions to the Black-Scholes model, like the **Black-Scholes-Merton with Dividends** or **Stochastic Volatility models**, address some of these limitations.


The **Black-Scholes formula** for the price of a European **call option** is given by:

$$C_K(T) = K e^{-rT} N(d_2) + S_0 N(d_1)$$

The **Black-Scholes formula** for the price of a European **put option** is given by:

$$
P_K(T) = K e^{-rT} N(-d_2) - S_0 N(-d_1)
$$

Where:

- \( P \): The price of the put option
- \( S_0 \): The current price of the underlying asset
- \( K \): The strike price of the option
- \( r \): The risk-free interest rate (annualized and continuously compounded)
- \( T \): Time to maturity (in years)
- \( \sigma \): The volatility of the underlying asset (standard deviation of its returns)
- \( N(x) \): The cumulative distribution function (CDF) of the standard normal distribution
- \( d_1 \) and \( d_2 \) are intermediate terms, defined as:


$$d_1 = \frac{\ln(S_0 / K) + (r + \sigma^2 / 2)T}{\sigma \sqrt{T}}$$



$$d_2 = d_1 - \sigma \sqrt{T}
$$


