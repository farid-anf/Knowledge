The **Black-Scholes formula** for the price of a European **call option** is given by:
$$
C_K(T) = K e^{-rT} N(d_2) + S_0 N(d_1)
$$

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


