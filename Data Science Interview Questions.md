# Statistics: 
In statistical hypothesis testing, Type I and Type II errors are potential mistakes that can occur when making decisions based on sample data.

# Type I and Type II Error: 

### Type I Error (False Positive)
- **Definition:** A Type I error occurs when the null hypothesis \( H_0 \) is true, but it is incorrectly rejected.
- **Significance Level (α):** The probability of committing a Type I error is denoted by α. This is the level of significance set by the researcher (e.g., 0.05), which represents a 5% risk of rejecting the null hypothesis when it is actually true.
- **Example:** If you are testing a new drug to determine if it has a significant effect, a Type I error would occur if you conclude that the drug works (reject the null hypothesis) when in fact it does not.

### Type II Error (False Negative)
- **Definition:** A Type II error occurs when the null hypothesis \( H_0 \) is false, but it is incorrectly accepted (failed to be rejected).
- **Beta (β):** The probability of committing a Type II error is denoted by β. This probability depends on the power of the test, which is the likelihood that the test correctly rejects a false null hypothesis.
- **Power (1 - β):** The power of a test is the probability that it correctly rejects the null hypothesis when it is false. Higher power means a lower probability of Type II error.
- **Example:** Continuing with the drug example, a Type II error would occur if you conclude that the drug does not work (fail to reject the null hypothesis) when in fact it does.

### Summary of Differences
- **Type I Error (α):** Rejecting a true null hypothesis (false positive).
- **Type II Error (β):** Failing to reject a false null hypothesis (false negative).
- **Control:** Type I error is controlled by setting a significance level (α), while Type II error is controlled by increasing the sample size, effect size, or power of the test.
- **Consequences:** The consequences of these errors depend on the context. Type I errors can lead to believing there is an effect when there isn't, while Type II errors can lead to missing out on a real effect.

In practical terms, researchers must balance the risks of both errors depending on the situation and the consequences of making incorrect decisions.


# Linear regression, coefficinet, p-value, and $R^2$

### Linear Regression

**Linear regression** is a statistical method used to model the relationship between a dependent variable (also called the response variable or target) and one or more independent variables (also called predictors or features). The goal is to fit a linear equation to observed data.

The general form of a simple linear regression model is:
\[ y = \beta_0 + \beta_1 x + \epsilon \]
where:
- \( y \) is the dependent variable.
- \( x \) is the independent variable.
- \( \beta_0 \) is the intercept of the regression line.
- \( \beta_1 \) is the slope (coefficient) of the regression line.
- \( \epsilon \) is the error term (the difference between the observed and predicted values).

### Terms and Their Significance

#### 1. Coefficient (\(\beta\))

- **Definition:** The coefficient (\(\beta\)) in linear regression represents the change in the dependent variable (\(y\)) for a one-unit change in the independent variable (\(x\)).
- **Significance:** It indicates the strength and direction of the relationship between the dependent and independent variables. A positive coefficient means that as the independent variable increases, the dependent variable also increases. A negative coefficient means that as the independent variable increases, the dependent variable decreases.

#### 2. p-Value

- **Definition:** The p-value is a measure of the probability that an observed difference could have occurred just by random chance.
- **Significance in Regression:** In the context of linear regression, the p-value tests the null hypothesis that the coefficient of a predictor is zero (no effect). A low p-value (< 0.05) indicates that you can reject the null hypothesis, suggesting that the predictor is statistically significant and likely to have a real impact on the dependent variable.
  - **Low p-value (< 0.05):** Suggests strong evidence against the null hypothesis, indicating that the predictor variable is significant.
  - **High p-value (> 0.05):** Suggests weak evidence against the null hypothesis, indicating that the predictor variable is not significant.

#### 3. R-Squared Value (\(R^2\))

- **Definition:** The R-squared value is a statistical measure that represents the proportion of the variance for the dependent variable that's explained by the independent variables in the model.
- **Significance:** It provides an indication of the goodness of fit of the model.
  - **\(R^2 = 0\):** Indicates that the model does not explain any of the variability of the response data around its mean.
  - **\(R^2 = 1\):** Indicates that the model explains all the variability of the response data around its mean.
  - **Interpreting \(R^2\):** Higher values of \(R^2\) indicate a better fit of the model to the data. However, it is important to note that a high \(R^2\) does not necessarily mean the model is appropriate, as it doesn't account for the complexity of the model or potential overfitting.

### Summary of Significance

- **Coefficient:** Indicates the impact of each predictor on the dependent variable. Helps in understanding the direction and magnitude of the relationship.
- **p-Value:** Determines the statistical significance of each predictor. Helps in identifying which predictors are meaningful contributors to the model.
- **R-Squared Value:** Measures the overall fit of the model. Provides an understanding of how well the model explains the variability in the dependent variable.

These components are crucial in assessing the performance, reliability, and usefulness of the linear regression model in making predictions or understanding relationships within the data.

### The mathematics behind it 

Certainly! The R-squared value (\( R^2 \)) is a measure used in statistical modeling to determine the proportion of variance in the dependent variable that can be explained by the independent variables in the model. Here’s the mathematical breakdown of how \( R^2 \) is calculated:

### Mathematical Definition of \( R^2 \)

\[ R^2 = 1 - \frac{SS_{\text{res}}}{SS_{\text{tot}}} \]

where:
- \( SS_{\text{res}} \) is the residual sum of squares.
- \( SS_{\text{tot}} \) is the total sum of squares.

### Steps to Calculate \( R^2 \)

1. **Calculate the Total Sum of Squares (\( SS_{\text{tot}} \))**:
   \[ SS_{\text{tot}} = \sum_{i=1}^n (y_i - \bar{y})^2 \]
   where:
   - \( y_i \) are the observed values of the dependent variable.
   - \( \bar{y} \) is the mean of the observed values.
   - \( n \) is the number of observations.

   \( SS_{\text{tot}} \) measures the total variation in the dependent variable.

2. **Calculate the Residual Sum of Squares (\( SS_{\text{res}} \))**:
   \[ SS_{\text{res}} = \sum_{i=1}^n (y_i - \hat{y}_i)^2 \]
   where:
   - \( \hat{y}_i \) are the predicted values from the regression model.

   \( SS_{\text{res}} \) measures the variation in the dependent variable that is not explained by the model.

3. **Calculate the Regression Sum of Squares (\( SS_{\text{reg}} \))** (optional for understanding):
   \[ SS_{\text{reg}} = \sum_{i=1}^n (\hat{y}_i - \bar{y})^2 \]

   \( SS_{\text{reg}} \) measures the variation in the dependent variable that is explained by the model.

4. **Calculate \( R^2 \)**:
   \[ R^2 = \frac{SS_{\text{reg}}}{SS_{\text{tot}}} \]

   Alternatively, using the relationship between the sums of squares:
   \[ R^2 = 1 - \frac{SS_{\text{res}}}{SS_{\text{tot}}} \]

### Interpretation of \( R^2 \)

- **\( R^2 = 0 \)**: Indicates that the model does not explain any of the variability in the dependent variable. The model predictions are no better than the mean of the observed data.
- **\( R^2 = 1 \)**: Indicates that the model explains all the variability in the dependent variable. The model predictions perfectly fit the observed data.
- **\( 0 < R^2 < 1 \)**: Indicates the proportion of the variance in the dependent variable that is predictable from the independent variables. For example, \( R^2 = 0.75 \) means that 75% of the variability in the dependent variable can be explained by the model.

### Example Calculation

Suppose you have the following observed values and predicted values from a linear regression model:

- Observed values (\( y \)): [3, 5, 7, 9]
- Predicted values (\( \hat{y} \)): [2.8, 4.9, 7.1, 9.2]

1. **Calculate the mean of observed values (\( \bar{y} \))**:
   \[ \bar{y} = \frac{3 + 5 + 7 + 9}{4} = 6 \]

2. **Calculate \( SS_{\text{tot}} \)**:
   \[ SS_{\text{tot}} = (3 - 6)^2 + (5 - 6)^2 + (7 - 6)^2 + (9 - 6)^2 \]
   \[ SS_{\text{tot}} = 9 + 1 + 1 + 9 = 20 \]

3. **Calculate \( SS_{\text{res}} \)**:
   \[ SS_{\text{res}} = (3 - 2.8)^2 + (5 - 4.9)^2 + (7 - 7.1)^2 + (9 - 9.2)^2 \]
   \[ SS_{\text{res}} = 0.04 + 0.01 + 0.01 + 0.04 = 0.10 \]

4. **Calculate \( R^2 \)**:
   \[ R^2 = 1 - \frac{SS_{\text{res}}}{SS_{\text{tot}}} \]
   \[ R^2 = 1 - \frac{0.10}{20} \]
   \[ R^2 = 1 - 0.005 \]
   \[ R^2 = 0.995 \]

This high \( R^2 \) value indicates that the model explains 99.5% of the variability in the dependent variable, suggesting an excellent fit to the data.


# Conditions for Linear regression to be reliable?

 Linear regression relies on several key assumptions to ensure the validity and reliability of the model’s results. Here are the main assumptions:

### 1. Linearity
The relationship between the independent variables and the dependent variable should be linear. This means that the change in the dependent variable is proportional to the change in the independent variable(s).

- **Check:** Plotting the residuals vs. the predicted values. Residuals should have no obvious pattern.

### 2. Independence
Observations should be independent of each other. The residuals (errors) should not be correlated with each other.

- **Check:** Durbin-Watson test for autocorrelation.

### 3. Homoscedasticity
The residuals should have constant variance at every level of the independent variables. This is known as homoscedasticity. If the variance of the residuals changes at different levels of the independent variables, it indicates heteroscedasticity.

- **Check:** Plotting the residuals vs. the predicted values. The spread of the residuals should be roughly constant.

### 4. Normality of Residuals
The residuals (errors) of the model should be approximately normally distributed. This is particularly important for hypothesis testing and constructing confidence intervals.

- **Check:** Q-Q plot (quantile-quantile plot) of the residuals. The points should lie approximately along a straight line. Alternatively, a histogram of residuals can be used.

### 5. No Multicollinearity
In multiple linear regression, the independent variables should not be too highly correlated with each other. Multicollinearity can make it difficult to determine the individual effect of each independent variable.

- **Check:** Variance Inflation Factor (VIF). VIF values above 10 indicate high multicollinearity.

### Summary of Assumptions
1. **Linearity**: The relationship between the independent and dependent variables is linear.
2. **Independence**: Observations are independent of each other.
3. **Homoscedasticity**: Constant variance of the residuals.
4. **Normality**: Residuals are normally distributed.
5. **No Multicollinearity**: Independent variables are not highly correlated with each other.

### Importance of Assumptions
- **Linearity**: Ensures the model is a good fit for the data.
- **Independence**: Prevents the results from being biased due to correlation between observations.
- **Homoscedasticity**: Ensures that the model’s predictions are equally reliable across all values of the independent variables.
- **Normality**: Allows for accurate hypothesis testing and confidence intervals.
- **No Multicollinearity**: Ensures the stability of coefficient estimates and interpretability of the model.

Violations of these assumptions can lead to biased, inefficient, or misleading results, which is why it's crucial to validate these assumptions when performing linear regression analysis.
