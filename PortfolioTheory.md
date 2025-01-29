## **Markowitz Mean Variance Analysis**

Markowitz Mean Variance Analysis, also known as Modern Portfolio Theory (MPT), is a framework for constructing a portfolio of assets that maximizes expected return for a given level of risk. It was introduced by Harry Markowitz in his 1952 paper "Portfolio Selection." Here’s a crash course on the key concepts:

### Two assets 

The daily return of an asset at time $t$ is computed by $\frac{r_{t}-r_{t-1}}{r_{t-1}}$. Now if we look at the daily returns we have a list of returns that we can compute volatility (variance) and expected return for it. Now consider two assets:

$$R_1: E(R_1)= 0.15 = \alpha_1, \sqrt{Var(R_1)}=0.25 = \sigma_1$$

$$R_1: E(R_2)= 0.20 = \alpha_2, \sqrt{Var(R_2)}=0.30 = \sigma_2$$

Let have a portfolio with $(1-w)$ share of $R_1$ and $w$ share of $R_2$. 

Then 



$$ R_w = 
\left(\begin{array}{cc} 
1-w \\ 
w 
\end{array}\right)^T
\left(\begin{array}{cc} 
R_1  \\
R_2  
\end{array}\right)= (1-w)R_1+wR_2, 0\leq w\leq 1
$$ 

$$\alpha_w=E[R_w]=(1-\alpha_1)+w\alpha_2$$

$$\sigma_w^2=Var(R_w)= 
\left(\begin{array}{cc} 
1-w \\ 
w 
\end{array}\right)^T \Sigma(R_1,R_2)$$
$$
=\left(\begin{array}{cc} 
1-w \\ 
w 
\end{array}\right)^T 
\left(\begin{array}{cc} 
Cov(R_1,R_1) & Cov(R_1,R_2) \\ 
Cov(R_2,R_1) & Cov(R_2,R_2)
\end{array}\right)
\left(\begin{array}{cc} 
1-w \\ 
w 
\end{array}\right)=
=\left(\begin{array}{cc} 
\sigma_1^2 &  \\ 
w 
\end{array}\right)^T 
$$



### Key Concepts

1. **Expected Return**:
   - The average return that an asset or portfolio is expected to generate. It’s often calculated as the weighted average of the possible returns, with the weights being the probabilities of those returns occurring.

2. **Risk (Variance/Standard Deviation)**:
   - Risk is quantified by the variance or standard deviation of returns. Variance measures the dispersion of returns around the expected return, while standard deviation is the square root of variance, providing a more intuitive measure of risk.

3. **Covariance and Correlation**:
   - Covariance measures how two assets move together. A positive covariance means they tend to move in the same direction, while a negative covariance means they move in opposite directions.
   - Correlation is the standardized version of covariance, ranging from -1 to 1. It provides a scale for the relationship between assets.

4. **Portfolio Expected Return**:
   - The expected return of a portfolio is the weighted sum of the expected returns of the individual assets in the portfolio.
   \[
   E(R_p) = \sum_{i=1}^{n} w_i E(R_i)
   \]
   where \(E(R_p)\) is the expected return of the portfolio, \(w_i\) is the weight of asset \(i\) in the portfolio, and \(E(R_i)\) is the expected return of asset \(i\).

5. **Portfolio Variance**:
   - The variance of a portfolio takes into account the variances of individual assets and the covariances between them.
   \[
   \sigma_p^2 = \sum_{i=1}^{n} \sum_{j=1}^{n} w_i w_j \sigma_{ij}
   \]
   where \(\sigma_p^2\) is the portfolio variance, \(w_i\) and \(w_j\) are the weights of assets \(i\) and \(j\), and \(\sigma_{ij}\) is the covariance between assets \(i\) and \(j\).

6. **Efficient Frontier**:
   - The efficient frontier is the set of optimal portfolios that offer the highest expected return for a defined level of risk or the lowest risk for a given level of expected return. These portfolios are considered efficient.

7. **Sharpe Ratio**:
   - The Sharpe Ratio measures the performance of an investment compared to a risk-free asset, after adjusting for its risk. It is calculated as:
   \[
   Sharpe Ratio = \frac{E(R_p) - R_f}{\sigma_p}
   \]
   where \(E(R_p)\) is the expected return of the portfolio, \(R_f\) is the risk-free rate, and \(\sigma_p\) is the standard deviation of the portfolio's excess return.

### Steps in Markowitz Mean Variance Analysis

1. **Estimate Expected Returns and Risks**:
   - Collect historical data to estimate the expected returns, variances, and covariances of the assets.

2. **Construct the Covariance Matrix**:
   - Calculate the covariance matrix of the asset returns, which will be used to compute portfolio variance.

3. **Determine Portfolio Weights**:
   - Use optimization techniques to find the weights of the assets that minimize portfolio risk for a given level of expected return, or maximize expected return for a given level of risk.

4. **Plot the Efficient Frontier**:
   - Plot the efficient frontier by solving the optimization problem for various levels of expected return.

5. **Select the Optimal Portfolio**:
   - Depending on the investor's risk tolerance, select the optimal portfolio from the efficient frontier. The optimal portfolio is typically the one that maximizes the Sharpe Ratio.

### Example Calculation

1. **Expected Returns**:
   Suppose you have two assets, A and B, with expected returns \(E(R_A) = 8\%\) and \(E(R_B) = 12\%\).

2. **Standard Deviations and Covariance**:
   Asset A has a standard deviation \(\sigma_A = 10\%\) and asset B has \(\sigma_B = 15\%\). The covariance between A and B is \(\sigma_{AB} = 0.0015\).

3. **Portfolio Expected Return**:
   If the weights of assets A and B in the portfolio are \(w_A = 0.6\) and \(w_B = 0.4\), the expected return of the portfolio is:
   \[
   E(R_p) = 0.6 \cdot 0.08 + 0.4 \cdot 0.12 = 0.096 = 9.6\%
   \]

4. **Portfolio Variance**:
   The portfolio variance is:
   \[
   \sigma_p^2 = (0.6^2 \cdot 0.01) + (0.4^2 \cdot 0.0225) + (2 \cdot 0.6 \cdot 0.4 \cdot 0.0015) = 0.0081
   \]
   The portfolio standard deviation is \(\sigma_p = \sqrt{0.0081} \approx 9\%\).

5. **Sharpe Ratio**:
   If the risk-free rate is 3%, the Sharpe Ratio is:
   \[
   Sharpe Ratio = \frac{0.096 - 0.03}{0.09} = 0.733
   \]

### Conclusion
Markowitz Mean Variance Analysis helps in creating an optimal portfolio by balancing the trade-off between risk and return. By diversifying across assets with different risk-return profiles and correlations, investors can achieve a portfolio that maximizes returns for a given level of risk, or minimizes risk for a given level of return.
