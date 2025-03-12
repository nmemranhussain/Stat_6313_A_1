# Advanced Logistic Regression Analysis of Age-Based Participation Using R

The GitHub repository "flixit-data-analysis" houses the R code for performing logistic regression analysis on a dataset named "FlixIt_2025". This repository includes scripts for loading necessary libraries like dplyr, pscl, pROC, and ResourceSelection, and for processing the dataset for statistical analysis. The primary focus of the analysis is to explore the relationship between 'Age' and 'Participation' using logistic regression, generating insights such as coefficients, odds ratios, sensitivity, specificity, and predictive values. Additional calculations in the analysis cover McFadden's R², area under the ROC curve, and model goodness-of-fit via the Hosmer and Lemeshow test. This codebase is useful for researchers or analysts interested in understanding the application of logistic regression in R, particularly in the context of binary outcome data related to age demographics. The README provides a comprehensive overview of how to set up the environment, execute the scripts, and interpret the results.

## Basic Information
**Names:** N M Emran Hussain  
**Email:** nmemranhussain2023@gmail.com  
**Date:** January 2025  
**Model Version:** 1.0.0  
**License:** [MIT License](LICENSE)

## Intended Use
**Purpose:** The model is the application of logistic regression in R, particularly in the context of binary outcome data related to age demographics.  
**Intended Users:** Data Analysts, Data scientists, machine learning enthusiasts, educators.  
**Out-of-scope Uses:** The model is not intended for production use in any critical applications or real-time decision-making systems.

## Data Description

| **Variable Name**       | **Model Role** | **Measurement Level**  | **Description**                                       |
|-------------------------|----------------|------------------------|-------------------------------------------------------|
| Age                     | Independent    | Ratio                  | Age score on a scale from 20 to 64.                   | 
| Region                  | Independent    | Discreet               | Region score on 'North', 'South', 'East' & 'West'     |
| Participation (Partic)  | Dependent      | Discreet               | For 'Participation' = 1, for 'Non-participation' = 0  |

**Dataset Name:** FlixIt_2025.dat  
**Number of Samples:** 200  
**Features Used:** 'Age', 'region'  
**Target Variable used:** 'Participation' (Partic)

## Model Details
### Architecture  
- This model card utilizes linear model such as **'Logistic Regression'**.

### Evaluation Metrics  
- **McFadden R^2** - Indicates the strength of relationships for logisitic regression model. 
- **Odds-ratio** - A statistic that quantifies the strength of the association between two events, representing the odds that one event will occur given the occurrence of another event.
- **Specificity** - The proportion of true negatives correctly identified by the model, indicating its accuracy in identifying non-events.
- **Sensitivity** - The proportion of true positives correctly identified by the model, reflecting its ability to detect actual events.
- **Positive Predictive Value (PPV)** - The proportion of positive test results that are true positives, indicating the likelihood that subjects with a positive test truly have the condition.
- **Negitive Predictive Value (NPV)** - The proportion of negative test results that are true negatives, showing the probability that subjects with a negative test truly don't have the condition.
- **Accuracy** - The proportion of true results (both true positives and true negatives) in the population, measuring the overall correctness of the model.
- **ROC curve** - A graphical plot that illustrates the diagnostic ability of a binary classifier system as its discrimination threshold is varied, used to select possibly optimal models.
- **Hoslem Good fit test** -  A statistical test for goodness of fit for logistic regression models, assessing whether the observed event rates match expected event rates in subgroups of the model population.
  
### Version of the Modeling Software: 
- **R:** 4.3.2
- **dplyr:** 1.1.4
- **pscl:** 1.5.9
- **pROC:** 1.18.5
- **ResourceSelection:** 0.3.6

## Quantitative Analysis

### Interpretation 

- **In the population, we can be reasonably certain that Age predicts Participation** because Using the logistic regression model, the p-value is significantly low (9.47e-11), indicating that 'Age' can reliably predict 'Participation'.
- **The relationship (McFadden’s R²) is 0.3336**, suggesting that the model has limited predictive power as the value is below 0.40.
- **The odds ratio is associated with Age** is 1.3191. It means the exponential of slope value of 'Age' in logistic regression. This value indicates that for each additional year of 'age', the odds of participating increase by approximately 31.91%.
- **If we applied this model to 100 people, 82 of them would you expect to be correctly classified** because our Accuracy result of the model is 0.8150 or 81.50%.
- **If we had 100 people known to be **Participants**, 43 of them would be expected to be incorrectly classified as non-participants by your logistic model** because it is based on the **sensitivity** of the model, which is 56.86%.
- **If we had 100 people known to be **non-Participants**, 10 of them would you expect to be incorrectly classified as participants by your logistic model** because it is derived from the **specificity** of the model, which is 89.93%.
- **If the model classifies 100 people as **Participants**, 34 of those people would you expect to be incorrectly classified** because the **positive predictive value (PPV) is 0.6591**, implying 34.09% might be incorrectly classified.
- **If the model classifies 100 people as **non-Participants**, 14 of those people would you expect to be incorrectly classified** because the **negative predictive value (NPV) is 0.859**, indicating 14.1% might be incorrectly.
- **The odds that a 30-year-old participates is 0.0095.**
- **The odds that a 40-year-old participates is 0.1510.**
- A 40-year-old is approximately **15.95 times more likely** to participate than a 30-year-old.
- The **probability** that **a 30-year-old participates** is **0.0094.*** using the formula: probability = odds / (1 + odds).
- **The Area is there under the ROC curve is 0.8772.** This indicates that the model does a good job of discriminating between participants and non-participants.
- **The Hosmer-Lemeshow goodness of fit test, which has a p-value of 0.1441** means a good fit to the data. This p-value, being above the typical alpha level of 0.05, suggests that there is no significant evidence to reject the model, implying that the logistic regression model is appropriate for these data.
