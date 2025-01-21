### **Bond Basics**
A bond is a debt security with periodic interest payments (coupons) and a final repayment of the principal (face value).

- **Cash Flows**: A bond generates periodic cash flows:

$$\text{Cash Flow at time } t =\begin{cases} 
      \text{Coupon Payment} & \text{for } t = 1, 2, \dots, T-1 \\
      \text{Coupon Payment} + \text{Face Value} & \text{for } t = T 
  \end{cases}$$
  
The lecture notes from MIT's course 18.S096 provide detailed mathematical formulations related to bonds. Here's a summary of the key formulas presented:

###  **Bond Price**

The fair price $P$ of a bond is calculated as the sum of the present values of its future cash flows, which include periodic coupon payments and the face value at maturity:


$$P = \sum_{i=1}^{N} \left( cF \times \Lambda_i \right) + F \times \Lambda_N$$


Where:
- $c$ is the coupon rate.
- $F$ is the face value of the bond.
- $\Lambda_i$ is the discount factor for payment date $i$.
- $N$ is the total number of coupon periods.

### 2. **Yield to Maturity (YTM)**

Assuming continuous compounding, the bond price can also be expressed using the yield to maturity \( y \):


$$P = \sum_{i=1}^{N} \left( C_i \times e^{-y t_i} \right)$$


Where:
- $C_i$ represents the $i$-th cash flow.
- $t_i$ is the time in years until the $i$-th payment.
- $y$ is the yield to maturity.

### 3. **Bond Duration**

Duration measures the sensitivity of the bond's price to changes in yield. It's calculated as:


$$d = \frac{1}{P} \sum_{i=1}^{N} \left( t_i \times C_i \times e^{-y t_i} \right)$$

Where:
- $t_i$ is the time in years until the \( i \)-th payment.
- $C_i$ is the $i$-th cash flow.
- $y$ is the yield to maturity.
- $P$ is the current bond price.

### 4. **Bond Convexity**

Convexity accounts for the curvature in the relationship between bond prices and yields, providing a more accurate measure for larger yield changes:

\[
c = \frac{1}{P} \sum_{i=1}^{N} \left( t_i^2 \times C_i \times e^{-y t_i} \right)
\]

Where:
- \( t_i \) is the time in years until the \( i \)-th payment.
- \( C_i \) is the \( i \)-th cash flow.
- \( y \) is the yield to maturity.
- \( P \) is the current bond price.

These formulas provide a comprehensive framework for evaluating bond prices, yields, and their sensitivities to interest rate changes. 
