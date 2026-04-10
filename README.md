# Bank Customer Churn Analysis & Retention Strategy

---

## 1. Background and Overview

A bank is currently losing approximately 20% of its customers annually due to churn, significantly impacting revenue and customer lifetime value.

As a business analyst, the goal is to identify high-risk customer segments and design targeted retention strategies.

If we can accurately identify even 75% of customers likely to churn, and successfully retain 50% of them, overall churn could be reduced by approximately 7–8%, resulting in meaningful business impact.
---

## 2. Data Structure Overview

* **Dataset Size:** 10,000 customers
* **Features:** 12 variables
* **Target Variable:** `churn` (1 = churned, 0 = retained)

### Key Features

* **Demographics:** Age, Gender, Country
* **Financials:** Balance, Credit Score, Estimated Salary
* **Relationship:** Tenure, Products Number
* **Behavior:** Active Member, Credit Card

### Key Statistics

* **Churn Rate:** ~20%
* **Average Age:** ~39
* **Average Products:** ~1.5
* **Active Members:** ~51%

---

## 3. Executive Summary

### Key Findings

* Inactive customers have **~2x higher churn** than active customers
* Customers with **2 products show lowest churn (~7–8%)**
* Customers with **1 product show high churn (~27–29%)**
* **Germany has highest churn across segments**
* Churn risk increases significantly **after age 45**

---

## 4. Key Drivers of Churn

Churn is primarily driven by **customer engagement, product usage, and demographics**.

---

### 4.1 Customer Activity (Strongest Driver)

![Engagement vs Churn](images/engagement_churn.png)

* Active churn rate: ~7%
* Inactive churn rate: ~13%

**Inactive users are ~2x more likely to churn**

Customer engagement is the most critical lever for retention. Even small improvements in activity levels can significantly reduce churn.

---

### 4.2 Product Ownership (Most Actionable Insight)

![Products vs Churn](images/products_churn.png)

| Products | Churn Rate |
| -------- | ---------- |
| 1        | ~27–29%    |
| 2        | ~7–8%      |

Moving from **1 → 2 products reduces churn by ~70%**

Product adoption directly improves retention, making cross-selling one of the highest ROI strategies.

---

### 4.3 Age Impact

![Age vs Churn](images/age_churn.png)

* Churn increases significantly **after age 45**

Older customers are at higher retention risk

Retention strategies should be personalized for older customers, who may have different expectations and needs.

---

### 4.4 Geographic Trends

![Country vs Churn](images/country_churn.png)

* **Germany shows highest churn across both active and inactive users**

Indicates potential regional issues

Churn is affected by customer location. Regional factors such as service quality or competition may be influencing customer behavior.

---

### 4.5 Combined Risk Analysis (Most Important)

![Combined Drivers](images/combined_churn.png)

Customers with:

* 1 product
* Inactive status
* Age > 45

Show **highest churn probability (~60–70%)**

Churn is driven by a combination of factors, not individual variables. Targeting this segment provides the highest impact.

---

## 5. Customer Segments

| Segment            | Characteristics      | Risk Level |
| ------------------ | -------------------- | ---------- |
| At-risk            | Inactive + 1 product | High       |
| Loyal              | Active + 2 products  | Low        |
| High-risk          | Older + inactive     | High       |
| Growth Opportunity | Active + 1 product   | Medium     |

---

## 6. Business Recommendations

### 1. Increase Customer Engagement

- Use app notifications and transaction-based nudges  
- Introduce loyalty and rewards programs  
- Improve onboarding experience to drive early engagement 

Expected impact: Reduce churn by improving activity levels

---

### 2. Cross-Sell Second Product (High ROI)

- Target customers with only 1 product  
- Offer bundled products and personalized recommendations  
- Use in-app prompts to encourage product discovery 

Expected impact: ~70% lower churn for converted users

---

### 3. Focus on Germany Market

* Investigate pricing, service gaps
* Launch localized retention campaigns

Expected impact: Address region-specific churn drivers

---

### 4. Retain Older Customers (45+)

* Offer personalized financial solutions
* Provide dedicated relationship management
* Ensure easy access to human support when needed 

Expected impact: Reduce churn in high-risk demographic

---

### 5. Enable Targeted Campaigns

* Focus on high-risk customers instead of mass outreach
* Prioritize segments with highest churn probability

Expected impact: Higher ROI with lower campaign cost

---

## 7. Caveats and Assumptions

### Data Limitations

* Small sample size for customers with 3–4 products
* No behavioral data (transactions, complaints, app usage)
* No time-series data

### Analytical Limitations

* Correlation does not imply causation
* External factors not included

---

## 8. Final Takeaway

This project demonstrates how data can be used to:

* Identify **who is likely to churn**
* Understand **why churn happens**
* Enable **targeted retention strategies**

**Key Drivers:** Engagement + Product Usage
**Key Strategy:** Increase activity + cross-sell second product
**Key Outcome:** Focused targeting improves retention and business impact
