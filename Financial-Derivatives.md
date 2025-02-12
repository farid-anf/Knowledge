The **Black-Scholes model** relies on several assumptions to derive the pricing formulas for European call and put options. These assumptions are:

---

### 1. **Efficient Market**
   - The market is frictionless: no transaction costs, taxes, or bid-ask spreads.
   - All investors have access to the same information and act rationally.

---

### 2. **Underlying Asset Dynamics**
   - The price of the underlying asset follows a **geometric Brownian motion** with constant drift ($\mu$) and constant volatility ($\sigma$):
    
     $$\frac{dS}{S} = \mu dt + \sigma dW$$
     
     where:
     - $dW$: A Wiener process (random walk)
     - $\mu$: The expected return of the asset (not directly used in the model)
     - $\sigma$: The volatility (constant)

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

These terms—**at-the-money (ATM)**, **in-the-money (ITM)**, and **out-of-the-money (OTM)**—describe the relationship between the **strike price** of an option and the **current price** of the underlying asset.

---

### 1. **At-the-Money (ATM)**
- An option is **at-the-money** when the **strike price** is **approximately equal to the current price** of the underlying asset.

#### Example:
- **Call Option**: If the strike price = $100 and the stock price = $100, the option is **ATM**.
- **Put Option**: If the strike price = $100 and the stock price = $100, the option is **ATM**.

---

### 2. **In-the-Money (ITM)**
- An option is **in-the-money** when it has **intrinsic value**, meaning exercising the option would result in a positive payoff.

#### **Call Option:**
- ITM if the **current price of the underlying asset** is **greater than the strike price** (\( S_0 > K \)).
  
#### **Put Option:**
- ITM if the **current price of the underlying asset** is **less than the strike price** (\( S_0 < K \)).

#### Example:
- **Call Option**: Strike price = $100, stock price = $120 → ITM by $20.
- **Put Option**: Strike price = $100, stock price = $80 → ITM by $20.

---

### 3. **Out-of-the-Money (OTM)**
- An option is **out-of-the-money** when it has **no intrinsic value**, meaning exercising the option would not result in a positive payoff.

#### **Call Option:**
- OTM if the **current price of the underlying asset** is **less than the strike price** (\( S_0 < K \)).

#### **Put Option:**
- OTM if the **current price of the underlying asset** is **greater than the strike price** (\( S_0 > K \)).

#### Example:
- **Call Option**: Strike price = $100, stock price = $80 → OTM.
- **Put Option**: Strike price = $100, stock price = $120 → OTM.

---

### **Summary of Terms**:

| **Option Type** | **ITM**                              | **ATM**                              | **OTM**                              |
|------------------|--------------------------------------|--------------------------------------|--------------------------------------|
| **Call Option**  | \( S_0 > K \)                       | \( S_0 = K \) (approximately)        | \( S_0 < K \)                       |
| **Put Option**   | \( S_0 < K \)                       | \( S_0 = K \) (approximately)        | \( S_0 > K \)                       |

---

### **Importance in Options Trading:**
1. **Intrinsic Value**: Only ITM options have intrinsic value; OTM options are purely speculative.
2. **Premiums**: ATM options tend to have the highest **time value**, making them more expensive than OTM options.
3. **Profitability**: ITM options are closer to profitability, while OTM options require a significant price move to become profitable.

---

These assumptions are idealized and often do not hold perfectly in real markets, which can lead to deviations between theoretical and actual option prices. Extensions to the Black-Scholes model, like the **Black-Scholes-Merton with Dividends** or **Stochastic Volatility models**, address some of these limitations.


The **Black-Scholes formula** for the price of a European **call option** is given by:

$$C_K(T) = K e^{-rT} N(d_2) + S_0 N(d_1)$$

The **Black-Scholes formula** for the price of a European **put option** is given by:

$$
P_K(T) = K e^{-rT} N(-d_2) - S_0 N(-d_1)
$$

The **Black-Scholes-Merton formula** for the price of a European **call option with dividends** is given by:

$$C_K(T) = K e^{-rT} N(d_2) + S_0 e^{-qT} N(d_1)$$

The **Black-Scholes formula** for the price of a European **put optionwith dividends** is given by:

$$P_K(T) = K e^{-rT} N(-d_2) - S_0 e^{-qT} N(-d_1)$$


Where:

- \( P \): The price of the put option
- \( S_0 \): The current price of the underlying asset
- \( K \): The strike price of the option
- \( r \): The risk-free interest rate (annualized and continuously compounded)
- \( T \): Time to maturity (in years)
- q: Continuous dividend yield (annualized, continuously compounded).
- \( \sigma \): The volatility of the underlying asset (standard deviation of its returns)
- \( N(x) \): The cumulative distribution function (CDF) of the standard normal distribution
- \( d_1 \) and \( d_2 \) are intermediate terms, defined as:


$$d_1 = \frac{\ln(S_0 / K) + (r + \sigma^2 / 2)T}{\sigma \sqrt{T}}$$



$$d_2 = d_1 - \sigma \sqrt{T}
$$

---

### **Enhanced Table with Greeks in Terms of Derivatives**

| **Greek** | **Measures Sensitivity To**           | **Call Option Impact**                           | **Put Option Impact**                            | **Mathematical Formula** (Derivatives)                                                |
|-----------|---------------------------------------|------------------------------------------------|-------------------------------------------------|---------------------------------------------------------------------------------------|
| **Delta (Δ)** | Underlying price (\( S_0 \))        | Positive (\( 0 \leq \Delta \leq 1 \))           | Negative (\( -1 \leq \Delta \leq 0 \))          | \( $\Delta = \frac{\partial C}{\partial S_0}$ \) (Call), \( $\Delta = \frac{\partial P}{\partial S_0}$ \) (Put) |
| **Gamma (Γ)** | Delta                               | Positive for both                               | Positive for both                               | \( $\Gamma = \frac{\partial^2 C}{\partial S_0^2} = \frac{\partial^2 P}{\partial S_0^2}$ \)                |
| **Theta (Θ)** | Time decay                          | Negative (value decreases over time)            | Negative (value decreases over time)            | \( $\Theta = \frac{\partial C}{\partial T}$ \) (Call), \( $\Theta = \frac{\partial P}{\partial T}$ \) (Put) |
| **Vega (ν)**  | Volatility (\( \sigma \))           | Positive (higher volatility increases value)    | Positive (higher volatility increases value)    | \( $\nu = \frac{\partial C}{\partial \sigma} = \frac{\partial P}{\partial \sigma}$ \)                     |
| **Rho (ρ)**   | Risk-free interest rate (\( r \))  | Positive                                        | Negative                                        | \( $\rho = \frac{\partial C}{\partial r} \) (Call), \( \rho = \frac{\partial P}{\partial r}$ \) (Put)     |

---

### **Explicit Formulas for Each Greek**

Using the Black-Scholes formula, the Greeks can also be expressed explicitly as follows:

---

#### **1. Delta (Δ):**

$$\Delta_{\text{call}} = N(d_1), \quad \Delta_{\text{put}} = N(d_1) - 1$$

Where:
$$d_1 = \frac{\ln(S_0 / K) + (r + \sigma^2 / 2)T}{\sigma \sqrt{T}}$$

---

#### **2. Gamma (Γ):**

$$\Gamma = \frac{N'(d_1)}{S_0 \sigma \sqrt{T}}$$

Where \( N'(d_1) \) is the probability density function (PDF) of the standard normal distribution:

$$N'(d_1) = \frac{1}{\sqrt{2\pi}} e^{-d_1^2 / 2}$$

---

#### **3. Theta (Θ):**
For a **call option**:

$$\Theta_{\text{call}} = -\frac{S_0 N'(d_1) \sigma}{2\sqrt{T}} - r K e^{-rT} N(d_2)$$
For a **put option**:

$$\Theta_{\text{put}} = -\frac{S_0 N'(d_1) \sigma}{2\sqrt{T}} + r K e^{-rT} N(-d_2)$$
Where:

$$d_2 = d_1 - \sigma \sqrt{T}$$

---

#### **4. Vega (ν):**

$$\nu = S_0 N'(d_1) \sqrt{T}$$

---

#### **5. Rho (ρ):**
For a **call option**:

$$\rho_{\text{call}} = K T e^{-rT} N(d_2)$$

For a **put option**:

$$\rho_{\text{put}} = -K T e^{-rT} N(-d_2)$$

---

### **European Digital Option (Binary Option):**

A **European digital option**, also called a **binary option**, is a type of option that pays a fixed amount if a certain condition is met at expiration. Unlike standard options, the payout of a digital option does not depend on the difference between the strike price and the underlying price; instead, it is a fixed value or zero.

---

### **Key Characteristics:**
1. **Payout Structure:**
   - If the condition is met (e.g., the underlying price is above the strike price for a call option), the buyer receives a fixed payout.
   - If the condition is not met, the buyer receives nothing.
   - The payoff is **all-or-nothing**.

2. **European-style:**
   - These options can only be exercised at maturity (not before).

3. **Payoff Formula:**
   - For a **digital call option**, the payoff is:
     
     $$\text{Payoff} = \begin{cases} 
     Q & \text{if } S_T > K \\
     0 & \text{if } S_T \leq K 
     \end{cases}$$
     
   - For a **digital put option**, the payoff is:
     
     $$\text{Payoff} = \begin{cases} 
     Q & \text{if } S_T < K \\
     0 & \text{if } S_T \geq K 
     \end{cases}$$
     
     Where:
     - \( Q \): Fixed payout.
     - \( S_T \): Price of the underlying at expiration.
     - \( K \): Strike price.

---

### **Valuation of a Digital Option:**

The Black-Scholes framework can be adapted to value European digital options. The price of a digital option is essentially the discounted probability of the condition being met.

#### **Digital Call Option Price:**

$$C_{\text{digital}} = e^{-rT} N(d_2)$$

#### **Digital Put Option Price:**

$$P_{\text{digital}} = e^{-rT} N(-d_2)$$


Where:
- \( N(d_2) \): The cumulative probability of \( d_2 \) under a standard normal distribution.
- \( d_2 \) is defined as:
  
  $$d_2 = \frac{\ln(S_0 / K) + (r - \sigma^2 / 2)T}{\sigma \sqrt{T}}$$

---

### **Greek Sensitivities:**
- **Delta:** Measures the change in the digital option price with respect to changes in the underlying price. It is a **spike-like function** near the strike price.
- **Gamma:** Even sharper spike than Delta, as digital options have a discontinuous payoff.
- **Theta:** Measures the impact of time decay. For digital options, Theta can be quite erratic near expiration.
- **Vega:** Measures sensitivity to volatility. Vega is high near the strike price because a slight increase in volatility can significantly affect the likelihood of crossing the strike.

---

### **Use Cases:**
1. **Speculation:**
   - Investors use digital options to speculate on whether an asset will be above or below a certain price at expiration.
   
2. **Risk Management:**
   - Digital options can serve as a hedge for specific payout structures, such as insurance against specific price movements.

3. **Exotic Trading:**
   - Popular in exotic options markets due to their simplicity and all-or-nothing payoff.

---

### **Example:**
Suppose you buy a **European digital call option** on a stock with:
- Strike price (\( K \)): $100
- Fixed payout (\( Q \)): $1,000
- Current stock price (\( S_0 \)): $95
- Volatility (\( \sigma \)): 20% per year
- Time to expiration (\( T \)): 1 year
- Risk-free rate (\( r \)): 5%.

At maturity:
- If the stock price \( S_T > 100 \), you receive $1,000.
- Otherwise, you receive $0.

Using the formula, you can calculate the price of this option today.

---

Digital options are widely used in structured products and speculative trading due to their straightforward payoff structure and pricing simplicity.

