### Mathematics Behind the Chi-Square Test of Independence

The **Chi-Square Test of Independence** is a statistical test used to determine whether two categorical variables are **independent** or **associated**. The mathematical process involves comparing the observed frequencies of different combinations of categories with the expected frequencies that would occur if the two variables were independent.

Here’s a step-by-step breakdown of the mathematical formulation:

### 1. **Contingency Table (Cross-Tabulation)**

The first step is to construct a **contingency table** (cross-tabulation) that displays the observed frequencies of the combinations of the two variables. 

Suppose we have two categorical variables, \( X \) (e.g., **admission**) and \( Y \) (e.g., **insurance situation**). Let’s define:

- $X_1, X_2, \dots, X_m$ as the categories of variable $X$,
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





Let’s go through a full example of the **Chi-Square Test of Independence** using mathematical steps with some data, but without Python code.

### Example: Testing the Independence between Admission Status and Insurance Situation

Suppose you are analyzing data from a hospital, and you want to test if there's an association between two categorical variables:
1. **Admission status** (whether a patient is admitted to the hospital or not)
2. **Insurance situation** (whether a patient has private insurance, public insurance, or no insurance)

Here’s a small dataset that shows the observed frequencies of patients' admission status and their insurance situation:

| Insurance Status  | Admitted (Yes) | Not Admitted (No) | Total |
|-------------------|----------------|-------------------|-------|
| Private Insurance | 30             | 20                | 50    |
| Public Insurance  | 40             | 30                | 70    |
| No Insurance      | 10             | 20                | 30    |
| **Total**         | **80**         | **70**            | **150** |

### Step 1: Construct the Contingency Table

The contingency table is already provided, where the rows represent the different insurance statuses, and the columns represent whether the patient was admitted or not.

\[
\begin{array}{|c|c|c|c|}
\hline
\text{Insurance Status} & \text{Admitted (Yes)} & \text{Not Admitted (No)} & \text{Total} \\
\hline
\text{Private Insurance} & 30 & 20 & 50 \\
\text{Public Insurance} & 40 & 30 & 70 \\
\text{No Insurance} & 10 & 20 & 30 \\
\hline
\text{Total} & 80 & 70 & 150 \\
\hline
\end{array}
\]

### Step 2: Calculate the Expected Frequencies

Now we calculate the expected frequencies for each cell, assuming that the two variables (admission and insurance status) are **independent**.

The formula for the expected frequency in any cell \( E_{ij} \) is:

\[
E_{ij} = \frac{R_i \times C_j}{N}
\]

Where:
- \( R_i \) is the total of row \( i \) (total number of patients in each insurance category),
- \( C_j \) is the total of column \( j \) (total number of admitted vs not admitted),
- \( N \) is the grand total of all observations (total number of patients).

#### Calculate the expected frequency for "Private Insurance" and "Admitted (Yes)":

\[
E_{11} = \frac{50 \times 80}{150} = 26.67
\]

#### Calculate the expected frequency for "Private Insurance" and "Not Admitted (No)":

\[
E_{12} = \frac{50 \times 70}{150} = 23.33
\]

#### Calculate the expected frequency for "Public Insurance" and "Admitted (Yes)":

\[
E_{21} = \frac{70 \times 80}{150} = 37.33
\]

#### Calculate the expected frequency for "Public Insurance" and "Not Admitted (No)":

\[
E_{22} = \frac{70 \times 70}{150} = 32.67
\]

#### Calculate the expected frequency for "No Insurance" and "Admitted (Yes)":

\[
E_{31} = \frac{30 \times 80}{150} = 16
\]

#### Calculate the expected frequency for "No Insurance" and "Not Admitted (No)":

\[
E_{32} = \frac{30 \times 70}{150} = 14
\]

### Step 3: Chi-Square Statistic Calculation

Now we can calculate the **Chi-Square statistic** \( \chi^2 \). The formula is:

\[
\chi^2 = \sum_{i=1}^{m} \sum_{j=1}^{n} \frac{(O_{ij} - E_{ij})^2}{E_{ij}}
\]

Where:
- \( O_{ij} \) is the observed frequency in cell \( (i,j) \),
- \( E_{ij} \) is the expected frequency in cell \( (i,j) \).

We will now calculate the sum for each cell.

#### For "Private Insurance" and "Admitted (Yes)":

\[
\frac{(30 - 26.67)^2}{26.67} = \frac{(3.33)^2}{26.67} = \frac{11.09}{26.67} = 0.416
\]

#### For "Private Insurance" and "Not Admitted (No)":

\[
\frac{(20 - 23.33)^2}{23.33} = \frac{(-3.33)^2}{23.33} = \frac{11.09}{23.33} = 0.475
\]

#### For "Public Insurance" and "Admitted (Yes)":

\[
\frac{(40 - 37.33)^2}{37.33} = \frac{(2.67)^2}{37.33} = \frac{7.13}{37.33} = 0.191
\]

#### For "Public Insurance" and "Not Admitted (No)":

\[
\frac{(30 - 32.67)^2}{32.67} = \frac{(-2.67)^2}{32.67} = \frac{7.13}{32.67} = 0.218
\]

#### For "No Insurance" and "Admitted (Yes)":

\[
\frac{(10 - 16)^2}{16} = \frac{(-6)^2}{16} = \frac{36}{16} = 2.25
\]

#### For "No Insurance" and "Not Admitted (No)":

\[
\frac{(20 - 14)^2}{14} = \frac{(6)^2}{14} = \frac{36}{14} = 2.57
\]

Now sum all the values:

\[
\chi^2 = 0.416 + 0.475 + 0.191 + 0.218 + 2.25 + 2.57 = 6.12
\]

### Step 4: Degrees of Freedom (df)

The degrees of freedom (df) for a contingency table are given by:

\[
df = (m - 1) \times (n - 1)
\]

Where:
- \( m \) is the number of rows (3 categories of insurance),
- \( n \) is the number of columns (2 categories of admission: Yes and No).

Thus, the degrees of freedom are:

\[
df = (3 - 1) \times (2 - 1) = 2 \times 1 = 2
\]

### Step 5: Find the p-value

To determine the significance of the test, we compare the calculated \( \chi^2 \) value to a **Chi-Square distribution** with 2 degrees of freedom.

Using a Chi-square distribution table, or a calculator, we find that for \( \chi^2 = 6.12 \) with \( df = 2 \), the p-value is approximately **0.047**.

### Step 6: Conclusion

If we choose a significance level \( \alpha = 0.05 \), we compare the p-value to \( \alpha \):

- **p-value = 0.047** is **less than** 0.05.

Since the p-value is less than 0.05, we reject the null hypothesis and conclude that there is a **significant association** between admission status and insurance situation. In other words, the likelihood of being admitted to the hospital **depends on** the type of insurance the patient has.
