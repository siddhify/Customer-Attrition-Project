# Bank Customer Churn: Analysis & Predictive Retention Model

Exploratory analysis and a predictive classification model to identify which bank customers are likely to churn, and a set of prioritized, ROI-ranked retention recommendations built from the findings.

[![Python](https://img.shields.io/badge/Python-3.10-blue)](https://www.python.org/)
[![scikit--learn](https://img.shields.io/badge/scikit--learn-ML-orange)](https://scikit-learn.org/)
[![pandas](https://img.shields.io/badge/pandas-data%20analysis-150458)](https://pandas.pydata.org/)

---

## Table of Contents

- [Background](#background)
- [Dataset](#dataset)
- [Executive Summary](#executive-summary)
- [Key Drivers of Churn](#key-drivers-of-churn)
- [Customer Segments](#customer-segments)
- [Predictive Model](#predictive-model)
- [Business Recommendations](#business-recommendations)
- [Caveats & Limitations](#caveats--limitations)
- [Final Takeaway](#final-takeaway)

---

## Background

A bank is currently losing approximately **20% of its customers annually** due to churn, materially impacting revenue and customer lifetime value.

This project takes the perspective of a business analyst: identify high-risk customer segments, quantify what actually drives churn, and design targeted retention strategies grounded in the data rather than guesswork.

> If we can accurately identify even 75% of customers likely to churn, and successfully retain 50% of them, overall churn could be reduced by approximately **7–8%** , a meaningful business impact at this customer base size.

---

## Dataset

| | |
|---|---|
| **Size** | 10,000 customers |
| **Features** | 12 variables |
| **Target** | `churn` (1 = churned, 0 = retained) |

**Feature groups**

- **Demographics:** age, gender, country
- **Financials:** balance, credit score, estimated salary
- **Relationship:** tenure, number of products
- **Behavior:** active member status, credit card ownership

**Headline stats**

- Churn rate: **~20%**
- Average age: **~39**
- Average products held: **~1.5**
- Active members: **~51%**

---

## Executive Summary

- Inactive customers churn at **~2x the rate** of active customers
- Customers with **2 products** show the lowest churn (**~7–8%**)
- Customers with **1 product** show high churn (**~27–29%**)
- **Germany** has the highest churn across every segment
- Churn risk rises sharply **after age 45**

---

## Key Drivers of Churn

Churn is primarily driven by a combination of **engagement, product usage, and demographics** , not any single variable in isolation.

### 1. Customer activity , the strongest single driver

| Status | Churn rate |
|---|---|
| Active | ~7% |
| Inactive | ~13–14% |

Inactive users are roughly **2x** more likely to churn. Engagement is the single most actionable lever available for retention , even small improvements in activity level move churn meaningfully.

### 2. Product ownership: the most actionable insight

| Products held | Churn rate |
|---|---|
| 1 | ~27–29% |
| 2 | ~7–8% |

Moving a customer from **1 → 2 products reduces churn by roughly 70%**. This makes cross-selling one of the highest-ROI retention plays available.

### 3. Age

Churn increases significantly **after age 45**. Older customers represent a distinct, higher-risk group whose expectations and service needs likely differ from younger customers.

### 4. Geography

**Germany** shows the highest churn rate across both active and inactive segments, pointing to a regional issue , pricing, service quality, or competitive pressure specific to that market.

### 5. Combined risk (most important cut of the data)

The highest-risk customers are those who are simultaneously:

- Holding **1 product**
- **Inactive**
- **Over age 45**

This combination shows a churn probability of **~60–70%**, several times the base rate. Because churn is driven by the *intersection* of factors rather than any one variable, this segment is the highest-value target for intervention.

---

## Customer Segments

| Segment | Characteristics | Risk Level |
|---|---|---|
| At-risk | Inactive + 1 product | High |
| Loyal | Active + 2 products | Low |
| High-risk | Older + inactive | High |
| Growth opportunity | Active + 1 product | Medium |

---

## Predictive Model

Beyond descriptive analysis, a classification model was built to score each customer's individual churn probability, enabling proactive, risk-ranked targeting rather than static segment rules.

**Approach:**

1. Data quality checks (missing values, duplicates, dtypes)
2. Feature engineering: one-hot encoding for categorical variables, standardization for scale-sensitive models
3. Two models trained and compared:
   - **Logistic Regression** , interpretable baseline; coefficients show direction and relative strength of each driver
   - **Random Forest** , captures non-linear interactions (e.g. the age × activity × product-count pattern found in the EDA)

**Results (held-out test set):**

| Metric | Logistic Regression | Random Forest |
|---|---|---|
| Accuracy | 0.714 | 0.829 |
| Precision | 0.387 | 0.561 |
| Recall | 0.700 | 0.720 |
| F1 score | 0.499 | 0.631 |
| ROC-AUC | 0.777 | **0.866** |

**Top predictive features (both models agree):** age, active member status, number of products, country (Germany), balance.

The Random Forest model was used to generate a churn-risk score for every customer, which concentrates a large share of actual churners into a small, actionable top-risk decile , the basis for the targeted-campaign recommendation below.

---

## Business Recommendations

### 1. Increase customer engagement
- App notifications and transaction-based nudges
- Loyalty and rewards programs
- Improved onboarding to drive early engagement

**Expected impact:** reduced churn via improved activity levels

### 2. Cross-sell a second product (highest ROI)
- Target customers holding only 1 product
- Bundled offers and personalized recommendations
- In-app prompts to encourage product discovery

**Expected impact:** ~70% lower churn among converted customers

### 3. Focus on the Germany market
- Investigate pricing and service gaps
- Launch localized retention campaigns

**Expected impact:** addresses a region-specific churn driver rather than treating it as noise

### 4. Retain older customers (45+)
- Personalized financial solutions
- Dedicated relationship management
- Easy access to human support when needed

**Expected impact:** reduced churn in the highest-risk demographic

### 5. Enable targeted, risk-ranked campaigns
- Use the model's churn-probability scores instead of mass outreach
- Prioritize the highest-risk segments identified above

**Expected impact:** higher ROI at lower campaign cost, by concentrating spend where it is most likely to work

---

## Caveats & Limitations

**Data limitations**
- Small sample size for customers holding 3–4 products (as few as 8–31 customers in some cuts) , churn rates here should not be treated as reliable
- No behavioral data available (transactions, complaints, app usage logs)
- No time-series data , this is a single snapshot, not a rolling "will churn in next N days" view

**Analytical limitations**
- Correlation does not imply causation recommendations should be validated with controlled retention pilots before full rollout
- External factors (competitor activity, macroeconomic conditions) are not included
- A fairness/model-risk review is recommended before deployment, given the observed country and demographic effects, to confirm the model doesn't produce disparate outcomes across groups

---

## Final Takeaway

This project shows how data can be used to:

- Identify **who** is likely to churn
- Understand **why** churn happens
- Enable **targeted**, cost-effective retention strategies

**Key drivers:** engagement + product usage
**Key strategy:** increase activity + cross-sell a second product
**Key outcome:** focused, risk-ranked targeting improves retention and ROI over mass-outreach campaigns
