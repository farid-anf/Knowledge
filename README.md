### Mathematics Behind the Chi-Square Test of Independence

The **Chi-Square Test of Independence** is a statistical test used to determine whether two categorical variables are **independent** or **associated**. The mathematical process involves comparing the observed frequencies of different combinations of categories with the expected frequencies that would occur if the two variables were independent.

Here’s a step-by-step breakdown of the mathematical formulation:

### 1. **Contingency Table (Cross-Tabulation)**

The first step is to construct a **contingency table** (cross-tabulation) that displays the observed frequencies of the combinations of the two variables. 

Suppose we have two categorical variables, \( X \) (e.g., **admission**) and \( Y \) (e.g., **insurance situation**). Let’s define:

- \( X_1, X_2, \dots, X_m \) as the categories of variable \( X \),
- \( Y_1, Y_2, \dots, Y_n \) as the categories of variable \( Y \).

The contingency table would have the following structure:

\[
\begin{array}{|c|c|c|c|c|}
\hline
& Y_1 & Y_2 & \dots & Y_n \\
\hline
X_1 & O_{11} & O_{12} & \dots & O_{1n} \\
X_2 & O_{21} & O_{22} & \dots & O_{2n} \\
\vdots & \vdots & \vdots & \ddots & \vdots \\
X_m & O_{m1} & O_{m2} & \dots & O_{mn} \\
\hline
\end{array}
\]

Where \( O_{ij} \) represents the **observed frequency** in the cell corresponding to the combination of \( X_i \) and \( Y_j \).

### 2. **Expected Frequencies**

If the two variables \( X \) and \( Y \) are **independent**, the observed frequencies should follow a certain expected distribution. The expected frequency \( E_{ij} \) for each cell of the contingency table is calculated under the assumption that the variables are independent. The expected frequency is given by:

\[
E_{ij} = \frac{( \text{Row total for } X_i ) \times ( \text{Column total for } Y_j )}{\text{Grand total of all observations}}
\]

Mathematically:

\[
E_{ij} = \frac{R_i \cdot C_j}{N}
\]

Where:
- \( R_i \) is the total of the \( i \)-th row (the total count of occurrences for category \( X_i \)),
- \( C_j \) is the total of the \( j \)-th column (the total count of occurrences for category \( Y_j \)),
- \( N \) is the grand total of all observations (the total number of data points).

### 3. **Chi-Square Statistic**

The **Chi-Square statistic** (\( \chi^2 \)) is calculated by summing the squared difference between the observed and expected frequencies, divided by the expected frequencies. This can be expressed as:

\[
\chi^2 = \sum_{i=1}^{m} \sum_{j=1}^{n} \frac{(O_{ij} - E_{ij})^2}{E_{ij}}
\]

Where:
- \( O_{ij} \) is the observed frequency in cell \( (i, j) \),
- \( E_{ij} \) is the expected frequency in cell \( (i, j) \).

The Chi-square statistic measures how far the observed data are from the expected data if the two variables are independent. A larger \( \chi^2 \) value indicates a greater discrepancy between the observed and expected values, suggesting that the variables may not be independent.

### 4. **Degrees of Freedom (df)**

The **degrees of freedom** for the Chi-square test are determined by the number of categories in each variable. For a contingency table with \( m \) rows and \( n \) columns, the degrees of freedom are given by:

\[
df = (m - 1)(n - 1)
\]

Where:
- \( m \) is the number of categories for variable \( X \),
- \( n \) is the number of categories for variable \( Y \).

### 5. **P-value and Conclusion**

The calculated Chi-square statistic is compared against a **Chi-square distribution** with \( (m - 1)(n - 1) \) degrees of freedom to determine the **p-value**. The p-value indicates the probability of obtaining a Chi-square statistic as extreme as the one observed, assuming the null hypothesis (independence) is true.

- If the **p-value** is less than the chosen significance level \( \alpha \) (commonly 0.05), you **reject the null hypothesis** and conclude that the variables are **dependent** (i.e., there is a significant association between them).
- If the **p-value** is greater than \( \alpha \), you **fail to reject the null hypothesis** and conclude that the variables are likely **independent**.

### Summary of the Chi-Square Test of Independence:

1. **Construct the contingency table** based on the observed data.
2. **Calculate the expected frequencies** assuming independence of the variables.
3. **Compute the Chi-square statistic** to measure the difference between observed and expected frequencies.
4. **Calculate the degrees of freedom**.
5. **Determine the p-value** from the Chi-square distribution with the calculated statistic and degrees of freedom.
6. **Interpret the results**: If the p-value is less than the significance level, reject the null hypothesis and conclude that the variables are dependent.

In the case of your example with **admission** and **insurance situation**, this test helps you determine whether the likelihood of being admitted to the hospital is associated with the type of insurance a patient has.
