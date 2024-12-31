### Mathematics Behind the Chi-Square Test of Independence

The **Chi-Square Test of Independence** is a statistical test used to determine whether two categorical variables are **independent** or **associated**. The mathematical process involves comparing the observed frequencies of different combinations of categories with the expected frequencies that would occur if the two variables were independent.

Here’s a step-by-step breakdown of the mathematical formulation:

### 1. **Contingency Table (Cross-Tabulation)**

The first step is to construct a **contingency table** (cross-tabulation) that displays the observed frequencies of the combinations of the two variables. 

Suppose we have two categorical variables, \( X \) (e.g., **admission**) and \( Y \) (e.g., **insurance situation**). Let’s define:

- $X_1, X_2, \dots, X_m$ as the categories of variable $X$,
- $Y_1, Y_2, \dots, Y_n$ as the categories of variable $Y$.

The contingency table would have the following structure:

$$
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
$$

Where $O_{ij}$ represents the **observed frequency** in the cell corresponding to the combination of $X_i$ and $Y_j$.

### 2. **Expected Frequencies**

If the two variables $X$ and $Y$ are **independent**, the observed frequencies should follow a certain expected distribution. The expected frequency $E_{ij}$ for each cell of the contingency table is calculated under the assumption that the variables are independent. The expected frequency is given by:

$$
E_{ij} = \frac{( \text{Row total for } X_i ) \times ( \text{Column total for } Y_j )}{\text{Grand total of all observations}}
$$

Mathematically:

$$
E_{ij} = \frac{R_i \cdot C_j}{N}
$$

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


The **Chi-Square Test of Independence** works because it compares the **observed frequencies** in each category of a contingency table to the **expected frequencies** under the assumption that the two categorical variables are independent. The test evaluates whether the difference between observed and expected frequencies is large enough to suggest that the variables are not independent.

Here’s why the Chi-Square test works:

### 1. **The Assumption of Independence**
   The Chi-Square test is based on the **null hypothesis**, which assumes that there is no relationship (or association) between the two categorical variables. If the two variables are truly independent, the distribution of observations across the cells in the contingency table will align with the expected frequencies calculated based on the marginal totals of the rows and columns.

   - **Independence** means that knowing the value of one variable provides no information about the value of the other. For example, if admission status and insurance type are independent, the probability of a patient being admitted should not depend on whether they have private, public, or no insurance.
   
### 2. **Expected Frequencies Calculation**
   The expected frequency for each cell in the contingency table assumes that the two variables are independent. It is calculated based on the product of the marginal probabilities of the two variables:

   \[
   E_{ij} = \frac{(Row \, Total \, i) \times (Column \, Total \, j)}{Grand \, Total}
   \]

   The idea is that if the variables are independent, the observed distribution of data across the table should closely match these expected values. If it doesn’t, that suggests some form of association between the variables.

### 3. **Chi-Square Statistic**
   The **Chi-Square statistic** measures the difference between the observed frequencies (\( O_{ij} \)) and the expected frequencies (\( E_{ij} \)) for each cell in the contingency table:

   \[
   \chi^2 = \sum_{i=1}^{m} \sum_{j=1}^{n} \frac{(O_{ij} - E_{ij})^2}{E_{ij}}
   \]

   - A large \( \chi^2 \) value indicates that the difference between observed and expected frequencies is large, suggesting a possible association between the variables.
   - A small \( \chi^2 \) value indicates that the observed frequencies are close to the expected frequencies, supporting the idea that the variables are independent.

### 4. **Degrees of Freedom and p-value**
   The degrees of freedom (\( df \)) in a contingency table are determined by the number of rows and columns (minus 1 for each). This helps define the distribution of the Chi-Square statistic.

   - **Degrees of freedom** are calculated as \( df = (m - 1) \times (n - 1) \), where \( m \) and \( n \) are the number of rows and columns, respectively.
   
   After calculating the \( \chi^2 \) statistic, we compare it to a Chi-Square distribution with the appropriate degrees of freedom. This comparison results in a **p-value**, which tells us whether the observed difference is statistically significant.

   - **p-value**: If the p-value is low (typically below 0.05), it suggests that the difference between observed and expected frequencies is large enough to reject the null hypothesis and conclude that there is an association between the two variables.
   - **High p-value**: If the p-value is large, we fail to reject the null hypothesis, meaning the evidence does not support an association between the variables, and they may be independent.

### 5. **Why the Chi-Square Test Works**
   - **Central Limit Theorem**: The Chi-Square test works because, under the null hypothesis of independence, the distribution of the test statistic \( \chi^2 \) approximates a **Chi-Square distribution** as the sample size increases. This approximation is due to the **central limit theorem**, which states that with large enough sample sizes, the distribution of the test statistic will converge to a known distribution (Chi-Square in this case), making it possible to calculate a p-value.
   
   - **Large Sample Size**: For smaller datasets, the Chi-Square test can be less reliable, especially if the expected frequencies are small (typically less than 5). In such cases, the results might not be as accurate. For small sample sizes, other tests like **Fisher’s Exact Test** may be more appropriate.

### 6. **Assumptions of the Chi-Square Test**
   For the Chi-Square test to be valid, certain conditions should be met:
   - The data should be categorical (nominal or ordinal).
   - The categories should be mutually exclusive.
   - The observations should be independent.
   - The expected frequency in each cell should generally be at least 5. If not, the Chi-Square approximation may not hold.

In summary, the **Chi-Square Test of Independence** works because it measures how much the observed frequencies deviate from what we would expect if the two variables were independent. By quantifying this deviation and comparing it to a theoretical distribution, it allows us to determine whether the variables are related or independent. The test is grounded in solid mathematical theory, including the concept of expected frequencies and the Chi-Square distribution, making it a robust method for testing relationships between categorical variables.


Besides the **Chi-Square Test of Independence**, several other methods can be used to test the independence between two categorical variables. Some of these methods include:

### 1. **Fisher's Exact Test**
   - **When to Use**: Fisher’s Exact Test is used primarily when the sample size is small or when the expected frequency in some cells of the contingency table is less than 5. 
   - **How It Works**: Unlike the Chi-Square test, which is based on approximations of large sample sizes, Fisher's Exact Test calculates the exact probability of observing the given data (or something more extreme) assuming the null hypothesis of independence. It uses the hypergeometric distribution to determine the probability of the observed configuration of counts.
   - **Assumptions**: It’s valid for 2x2 contingency tables and can be extended for larger tables using the Fisher-Freeman-Halton extension.

### 2. **Likelihood Ratio Test (G-test)**
   - **When to Use**: This is another alternative to the Chi-Square test. It is often used when the Chi-Square test assumptions are violated (e.g., expected frequencies too low).
   - **How It Works**: The Likelihood Ratio Test compares the likelihood of the data under the null hypothesis of independence to the likelihood of the data under the alternative hypothesis. The test statistic follows a Chi-Square distribution under the null hypothesis.
   - **Mathematics**: The likelihood ratio statistic is calculated as:
     \[
     G^2 = 2 \sum_{i,j} O_{ij} \ln \left(\frac{O_{ij}}{E_{ij}}\right)
     \]
     where \( O_{ij} \) and \( E_{ij} \) are the observed and expected frequencies, respectively.

### 3. **Cramér's V Statistic**
   - **When to Use**: This method is typically used to measure the strength of association between two categorical variables (not necessarily for testing independence). Cramér's V ranges from 0 (no association) to 1 (complete association).
   - **How It Works**: Cramér's V is based on the Chi-Square statistic but provides a standardized measure of association. It is often used alongside the Chi-Square test to measure the strength of the association when the Chi-Square test suggests that there is a significant association.
   - **Formula**:
     \[
     V = \sqrt{\frac{\chi^2}{n \times (k - 1)}}
     \]
     where \( n \) is the total number of observations and \( k \) is the smaller of the number of rows or columns in the contingency table.

### 4. **Theodosiou's Test**
   - **When to Use**: This test is used in cases where the number of categories is large, and the variables are ordinal. It is an alternative to the Chi-Square test when the variables are ordered.
   - **How It Works**: Theodosiou's test uses a non-parametric approach for calculating the association between ordered categorical variables.

### 5. **Spearman's Rank Correlation Coefficient**
   - **When to Use**: This method is used to test for monotonic relationships between two ordinal variables. Unlike Pearson’s correlation (which measures linear relationships), Spearman’s rank correlation measures the strength and direction of the relationship between ranked variables.
   - **How It Works**: It calculates the correlation between the ranks of the values of the variables, not their raw values.
   - **Mathematics**: The formula for Spearman’s rank correlation coefficient is:
     \[
     \rho = 1 - \frac{6 \sum d_i^2}{n(n^2 - 1)}
     \]
     where \( d_i \) is the difference in ranks for each pair of values, and \( n \) is the number of data points.

### 6. **Mutual Information**
   - **When to Use**: Mutual Information is a method from information theory that quantifies the amount of information gained about one variable by knowing the other variable. It is particularly useful when the relationship between variables is non-linear.
   - **How It Works**: It measures the reduction in uncertainty of one variable given knowledge of the other variable. If two variables are independent, their mutual information will be zero.
   - **Formula**:
     \[
     I(X;Y) = \sum_{x \in X} \sum_{y \in Y} P(x, y) \log \frac{P(x, y)}{P(x)P(y)}
     \]
     where \( P(x, y) \) is the joint probability distribution of \( X \) and \( Y \), and \( P(x) \) and \( P(y) \) are their marginal distributions.

---

### Can We Use **Bootstrapping** for Testing Independence?

Yes, **bootstrapping** can be used to test the independence of two variables. Bootstrapping is a non-parametric method that involves repeatedly sampling from the data with replacement to create a large number of simulated datasets. For testing independence, bootstrapping can be used as follows:

1. **Resampling**: Generate many resampled datasets by drawing samples with replacement from the observed data.
   
2. **Test Statistic**: For each resampled dataset, compute a test statistic (such as the Chi-Square statistic, or a measure like mutual information).

3. **Comparison**: Compare the observed test statistic (calculated from the original data) to the distribution of the test statistic from the resampled datasets. If the observed statistic is significantly different from what is expected under the null hypothesis of independence, this suggests that the variables are not independent.

#### Advantages of Bootstrapping for Independence Testing:
- **Non-parametric**: Bootstrapping doesn't rely on the assumptions of normality or other parametric constraints, making it useful when the data do not meet the assumptions of traditional tests like Chi-Square or Fisher’s Exact Test.
- **Flexibility**: It can be applied to a variety of test statistics, including those that are not easily derived under theoretical distributions.

#### Disadvantages:
- **Computational Intensity**: Bootstrapping requires a large number of resamples to provide accurate p-values, which can be computationally expensive, especially with large datasets.
- **Assumption of IID**: Bootstrapping assumes that the data points are independent and identically distributed (IID), which may not hold in all scenarios.

---

### Conclusion

In summary, while the **Chi-Square Test of Independence** is one of the most commonly used tests for independence, there are several other methods available, including **Fisher's Exact Test**, **Likelihood Ratio Test (G-test)**, **Cramér's V**, and others, depending on the data type and size. **Bootstrapping** can be a useful, flexible alternative for testing independence, especially in cases where the assumptions of parametric tests do not hold or when the sample size is small.


Let's go through an example of testing the independence of two categorical variables using **bootstrapping**. We will simulate a small dataset with two categorical variables and then use bootstrapping to test their independence.

### Example

Suppose we have a dataset where we want to test the independence between **admission type** (whether a patient was admitted through the emergency department or not) and **insurance status** (whether the patient has insurance or not). Let's use a contingency table for this purpose.

#### Step 1: Simulated Data

Let’s assume the following data (simplified):

| Admission Type | Insurance Status: Insured | Insurance Status: Not Insured |
|----------------|----------------------------|-------------------------------|
| Emergency      | 40                         | 20                            |
| Non-Emergency  | 30                         | 10                            |

From this, we create a contingency table as:

\[
\text{Observed Contingency Table:}
\begin{array}{|c|c|c|}
\hline
\text{Admission Type} & \text{Insured} & \text{Not Insured} \\
\hline
\text{Emergency} & 40 & 20 \\
\hline
\text{Non-Emergency} & 30 & 10 \\
\hline
\end{array}
\]

#### Step 2: Calculating the Chi-Square Statistic (Observed)

The Chi-Square statistic for testing independence is given by:

\[
\chi^2 = \sum \frac{(O_{ij} - E_{ij})^2}{E_{ij}}
\]

Where:
- \(O_{ij}\) is the observed frequency in cell \((i, j)\),
- \(E_{ij}\) is the expected frequency in cell \((i, j)\), which is calculated as:
  
\[
E_{ij} = \frac{\text{row total} \times \text{column total}}{\text{grand total}}
\]

First, calculate the expected values for each cell in the table:

\[
E_{\text{Emergency, Insured}} = \frac{(40 + 30) \times (40 + 20)}{(40 + 20 + 30 + 10)} = \frac{70 \times 60}{100} = 42
\]
\[
E_{\text{Emergency, Not Insured}} = \frac{(40 + 30) \times (20 + 10)}{100} = \frac{70 \times 30}{100} = 21
\]
\[
E_{\text{Non-Emergency, Insured}} = \frac{(40 + 30) \times (40 + 20)}{100} = \frac{70 \times 60}{100} = 42
\]
\[
E_{\text{Non-Emergency, Not Insured}} = \frac{(40 + 30) \times (20 + 10)}{100} = \frac{70 \times 30}{100} = 21
\]

Now, compute the Chi-Square statistic:

\[
\chi^2 = \frac{(40 - 42)^2}{42} + \frac{(20 - 21)^2}{21} + \frac{(30 - 42)^2}{42} + \frac{(10 - 21)^2}{21}
\]

\[
\chi^2 = \frac{4}{42} + \frac{1}{21} + \frac{144}{42} + \frac{121}{21}
\]

\[
\chi^2 = 0.0952 + 0.0476 + 3.4286 + 5.76 = 9.3314
\]

#### Step 3: Bootstrap Resampling

To use bootstrapping, we will create new datasets by sampling with replacement from the original dataset and then compute the Chi-Square statistic for each resampled dataset.

1. **Resample the data with replacement**:
   - This means randomly selecting observations with replacement (i.e., a patient could appear more than once in the resampled dataset).

2. **Calculate the Chi-Square statistic for each resampled dataset**:
   - For each resampled dataset, construct the contingency table and calculate the Chi-Square statistic.

3. **Repeat the resampling process** a large number of times (e.g., 1000 iterations).

4. **Compare the observed Chi-Square statistic** to the distribution of Chi-Square statistics from the resampled datasets.

#### Step 4: Bootstrap Implementation (Conceptually)

- Let's say we resample the dataset 1000 times, and for each resample, we calculate a Chi-Square statistic.

- Suppose the bootstrapped Chi-Square statistics for 1000 resamples are stored in a list. We can compute the p-value by finding the proportion of resampled statistics that are greater than or equal to the observed statistic.

\[
p\text{-value} = \frac{\text{Number of bootstrapped statistics} \geq \chi^2_{\text{observed}}}{\text{Total number of bootstraps}}
\]

If the p-value is below a significance level (say, 0.05), we reject the null hypothesis and conclude that the two variables (Admission Type and Insurance Status) are not independent.

#### Step 5: Interpretation of Results

- If the p-value obtained from the bootstrap resampling is low (e.g., \( p < 0.05 \)), this suggests that the observed relationship between **Admission Type** and **Insurance Status** is unlikely to be due to random chance, indicating that the two variables are **dependent**.
- If the p-value is high (e.g., \( p \geq 0.05 \)), it suggests that the observed relationship could be due to random chance, and thus the two variables are **independent**.

---

### Conclusion

In this example, we used bootstrapping to assess the independence between two categorical variables by generating new samples and comparing the Chi-Square statistic to a distribution of bootstrapped statistics. This allows us to assess the significance of the observed independence test without relying on large-sample approximations, which can be especially useful in small datasets.
