The **Black-Scholes formula** for the price of a European **put option** is given by:

$$
P = K e^{-rT} N(-d_2) - S_0 N(-d_1)
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

\[
d_1 = \frac{\ln(S_0 / K) + (r + \sigma^2 / 2)T}{\sigma \sqrt{T}}
\]

\[
d_2 = d_1 - \sigma \sqrt{T}
\]

### Explanation:
- \( S_0 N(-d_1) \): Represents the present value of the asset price when the put option is exercised.
- \( K e^{-rT} N(-d_2) \): Represents the present value of the strike price discounted at the risk-free rate, adjusted by the probability of exercise.

The formula assumes no dividends, European-style exercise (only at maturity), and constant volatility and interest rates.
