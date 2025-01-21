The lecture notes discuss **bonds** with a focus on their **cash flows, pricing, and yield to maturity (YTM)**. Here's a mathematical breakdown of the content:

---

### 1. **Bond Basics**
A bond is a debt security with periodic interest payments (coupons) and a final repayment of the principal (face value).

- **Cash Flows**: A bond generates periodic cash flows:
  \[
  \text{Cash Flow at time } t = 
  \begin{cases} 
      \text{Coupon Payment} & \text{for } t = 1, 2, \dots, T-1 \\
      \text{Coupon Payment} + \text{Face Value} & \text{for } t = T 
  \end{cases}
  \]

---

### 2. **Bond Pricing**
The price of a bond is the **present value (PV)** of its future cash flows, discounted using the **discount rate \( r \)** (often related to market interest rates):
\[
P = \sum_{t=1}^{T} \frac{C}{(1 + r)^t} + \frac{F}{(1 + r)^T}
\]
Where:
- \( P \): Price of the bond
- \( C \): Periodic coupon payment (\( C = \text{Coupon Rate} \times F \))
- \( F \): Face value of the bond
- \( T \): Time to maturity (in periods)
- \( r \): Discount rate or yield

---

### 3. **Yield to Maturity (YTM)**
The **YTM** is the interest rate \( r \) that equates the bond's price to the present value of its cash flows:
\[
P = \sum_{t=1}^{T} \frac{C}{(1 + \text{YTM})^t} + \frac{F}{(1 + \text{YTM})^T}
\]
This equation is typically solved numerically since it is nonlinear in \( \text{YTM} \).

---

### 4. **Duration**
**Duration** measures the sensitivity of a bond's price to changes in interest rates. The **Macaulay Duration** \( D_M \) is:
\[
D_M = \frac{\sum_{t=1}^{T} t \cdot \frac{C}{(1 + r)^t} + T \cdot \frac{F}{(1 + r)^T}}{P}
\]
- It gives the weighted average time until cash flows are received.

---

### 5. **Convexity**
**Convexity** measures the curvature of the price-yield relationship, improving the accuracy of duration estimates:
\[
\text{Convexity} = \frac{\sum_{t=1}^{T} t \cdot (t + 1) \cdot \frac{C}{(1 + r)^{t+2}} + T \cdot (T + 1) \cdot \frac{F}{(1 + r)^{T+2}}}{P}
\]

Convexity is used to refine bond price approximations when interest rates change significantly.

---

### 6. **Applications**
- Understanding **sensitivity** of bond prices to interest rate movements.
- Valuing bonds in changing interest rate environments using \( r \) derived from yield curves.
- Regularizing bond models for stability, especially in volatile markets.

---

Would you like me to explain any of these in greater detail or apply them to an example?
