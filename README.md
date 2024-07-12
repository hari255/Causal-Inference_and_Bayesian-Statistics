# Estimating the Impact of an Online Marketing Campaign Using Bayesian Statistics and Causal Inference


## Project Overview

Analyzing the impact of an online marketing campaign on user engagement metrics, such as `click-through` rate (CTR) or `conversion` rate. The goal is to quantify the causal effect of the campaign and estimate the impact using Bayesian statistics and Causal Inference.


### Data 
-----------


| Variables | Description | Data type | 
|-----------|-------------|-----------|
| User ID   | A unique identifier for each user in the dataset. | Int | 
| Exposed | Indicates whether a user was exposed to the marketing campaign. 1 means the user was exposed, and 0 means the user was not exposed.| Int(0/1) | 
| Clicks before | The number of clicks a user made before being exposed to the marketing campaign. | Int |
| clicks after | The number of clicks a user made after being exposed to the marketing campaign. | Int |
| conversions before | Indicates whether a user converted (e.g., made a purchase) before being exposed to the marketing campaign. 1 means the user converted, and 0 means the user did not convert. | Int (0/1) |
| Conversions After |  Indicates whether a user converted after being exposed to the marketing campaign. 1 means the user converted, and 0 means the user did not convert. | Int (0/1) |
| Clicks Difference | The difference in the number of clicks before and after the campaign exposure (clicks_after - clicks_before). This variable is used to measure the change in user behavior due to the campaign. | Int | 
| Conversions Difference|  The difference in the number of conversions before and after the campaign exposure (conversions_after - conversions_before). This variable is used to measure the change in user behavior due to the campaign. | Int |
| Propensity Score | The probability of a user being exposed to the campaign based on their characteristics (e.g., clicks_before and conversions_before). This score is used in propensity score matching to create comparable treatment and control groups. | Float | 


## Concepts and Methods

### Propensity Score

**Propensity Score** is the probability of a unit (e.g., a user) being assigned to the treatment group given a set of observed covariates. It helps to balance the treatment and control groups on these covariates, making the groups comparable for causal inference.

#### Formula

Given a set of covariates \(X\), the propensity score \(e(X)\) is defined as:

\[ e(X) = P(T = 1 \mid X) \]

where:
- \(T\) is the treatment indicator (1 if treated, 0 if control).
- \(X\) is the vector of observed covariates.

### Logistic Regression

Logistic regression is used to estimate the propensity scores. The model predicts the probability of a user being exposed to the campaign based on their pre-treatment characteristics.

#### Formula

The logistic regression model estimates the probability \(P(T = 1 \mid X)\) as:

\[ P(T = 1 \mid X) = \frac{1}{1 + \exp^{-(\alpha + \beta_1 \cdot X_1 + \beta_2 \cdot X_2 + \ldots + \beta_n \cdot X_n)}} \]

where:
- \(\alpha\) is the intercept.
- \(\beta_1, \beta_2, \ldots, \beta_n\) are the coefficients for the covariates \(X_1, X_2, \ldots, X_n\).

### Nearest Neighbors Matching

Nearest Neighbors Matching is used to match each treated user with a control user who has a similar propensity score. This helps to create a balanced dataset where the treatment and control groups are comparable.

### Difference-in-Differences (DiD)

The Difference-in-Differences method estimates the treatment effect by comparing the changes in outcomes over time between the treatment and control groups. This method helps to account for time-invariant unobserved confounders.

## Steps

1. **Data Simulation**: Simulate user data with engagement metrics and campaign exposure.
2. **Propensity Score Calculation**: Use logistic regression to calculate propensity scores based on pre-treatment variables.
3. **Matching**: Use Nearest Neighbors Matching to match treated users with control users based on propensity scores.
4. **Visualization**: Create scatter plots to visualize the distribution of propensity scores before and after matching.
