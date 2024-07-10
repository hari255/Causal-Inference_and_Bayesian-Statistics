# Estimating the Impact of an Online Marketing Campaign Using Bayesian Statistics and Causal Inference


## Project Overview

Analyzing the impact of an online marketing campaign on user engagement metrics, such as `click-through` rate (CTR) or `conversion` rate. The goal is to quantify the casual effect of the campaign and estimate the impact using Bayesian statistics and Causal Inference.


### Data Collection

Simulating data on user interactions before and after the marketing campaign.

| Variables | Description | Datatype |
|-----------|-------------|----------|

|User ID   | A unique identifier for each user in the dataset. | Integer |
|Exposed | Indicates whether a user was exposed to the marketing campaign. 1 means the user was exposed, and 0 means the user was not exposed.| Integer 0/1 | 
|Clicks before | The number of clicks a user made before being exposed to the marketing campaign. | Integer |
|clicks after | The number of clicks a user made after being exposed to the marketing campaign. | Integer |
| conversions before | Indicates whether a user converted (e.g., made a purchase) before being exposed to the marketing campaign. 1 means the user converted, and 0 means the user did not convert.| Integer 0/1|
| Conversions After |  Indicates whether a user converted after being exposed to the marketing campaign. 1 means the user converted, and 0 means the user did not convert. | Integer 0/1 | 
| Clicks Difference | The difference in the number of clicks before and after the campaign exposure (clicks_after - clicks_before). This variable is used to measure the change in user behavior due to the campaign. | Integer|
| Conversions Difference|  The difference in the number of conversions before and after the campaign exposure (conversions_after - conversions_before). This variable is used to measure the change in user behavior due to the campaign. | Integer|
|Propensity Score | The probability of a user being exposed to the campaign based on their characteristics (e.g., clicks_before and conversions_before). This score is used in propensity score matching to create comparable treatment and control groups. | Float|
