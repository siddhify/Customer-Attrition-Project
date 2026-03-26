# Bank Customer Churn Analysis & Retention Strategy

---

## 1. Background and Overview

Customer churn directly impacts a bank’s revenue, customer lifetime value, and growth strategy. Retaining customers is significantly more cost-effective than acquiring new ones.

This project analyzes customer data and builds a predictive model to:

* Identify key drivers of churn
* Segment high-risk customers
* Enable targeted retention strategies with measurable business impact

---

## 2. Data Structure Overview

* **Dataset Size:** 10,000 customers
* **Features:** 12 variables
* **Target Variable:** `churn` (1 = churned, 0 = retained)

### Key Features

* Demographics: Age, Gender, Country
* Financials: Balance, Credit Score, Estimated Salary
* Relationship: Tenure, Products Number
* Behavior: Active Member, Credit Card

### Key Statistics

* **Churn Rate:** ~20%
* **Average Age:** ~39
* **Average Credit Score:** ~650
* **Average Products:** ~1.5
* **Active Members:** ~51%

---

## 3. Executive Summary

### Key Findings

* Inactive customers have **~2x higher churn** than active customers
* Customers with **2 products show lowest churn (~7–8%)**
* Customers with **1 product show high churn (~27–29%)**
* **Germany has highest churn (~41% among inactive users)**
* Churn risk increases significantly **after age 45**

---

### Predictive Model Output

*  Model tuned at **0.3 threshold** achieves **~91.6% recall** and **~26% precision**, prioritizing maximum churn detection over false positives for effective targeting.  
* Model identified **1,380 high-risk customers for test data of 2000 customers.**
* Enables **targeted retention instead of mass outreach**

---

### Estimated Business Impact

Assumptions:

* Campaign Success Rate: 25%
* Value per retained customer: ₹5,000

**Impact Calculation:**

* Customers targeted: 1,380
* Expected saves ≈ 90 customers
* Estimated value saved = **4,50,000**

---

## 4. Insights

### 4.1 Customer Activity (Strongest Driver)

* Active churn rate: ~7%
* Inactive churn rate: ~13%

Inactive users are **~2x more likely to churn**

---

### 4.2 Product Ownership (Most Actionable Insight)

| Products | Churn Rate |
| -------- | ---------- |
| 1        | ~27–29%    |
| 2        | ~7–8%      |

Moving from **1 → 2 products reduces churn by ~70%**

Churn for 3+ products appears very high but is based on **small sample size**

---

### 4.3 Age Impact

* Churn increases significantly **after 45 years**
* Highest risk: **Older inactive customers**

---

### 4.4 Geographic Trends

* **Germany shows highest churn across all segments**
* France & Spain show relatively stable patterns

---

### 4.5 Financial Indicators

* Balance shows weak relationship with churn
* Credit score and salary show **minimal predictive power**

---

### 4.6 High-Risk Segment (Combined View)

Customers with:

* 1 product
* Inactive status
* Age > 45

Represent the **highest churn probability segment (~60–70%)**

---

## 5. Recommendations

### 1. Increase Customer Engagement

* App notifications, transaction nudges
* Loyalty & rewards programs

 Active customers show ~40% lower churn compared to inactive customers, indicating that improving customer engagement could reduce churn risk.  

   

---

### 2. Cross-Sell Second Product (High ROI)

* Target customers with 1 product
* Bundle offerings

 Customers with 2 products have significantly lower churn (~8%) compared to those with 1 product (~28%), representing ~72% lower churn.
 This suggests cross selling a second product may be a strong retention lever.  

---

### 3. Focus on Germany Market

* Investigate pricing, service gaps
* Launch localized retention campaigns

### 4. Retain Older Customers (45+)

* Personalized financial planning
* Dedicated relationship management

---

### 5. Use ML for Targeted Campaigns

* Focus on** predicted high-risk customers by scaling the model.**
* Avoid blanket campaigns → reduce cost

---

## Caveats and Assumptions

### Data Limitations

* Very small sample size for customers with 3–4 products
* No behavioral data (transactions, complaints, app usage)
* No time-series data (snapshot only)

---

### Modeling Assumptions

* Retention success rate assumed at 25%
* Customer value assumed at ₹5,000

---

### Analytical Limitations

* Correlation does not imply causation
* External factors (competition, macroeconomics) not included

---

## Final Takeaway

This project moves beyond descriptive analysis to actionable strategy:

* Identifies **who is likely to churn**
* Quantifies **why churn happens**
* Enables **targeted intervention with measurable ROI**

**Key Drivers:** Customer activity and product ownership
K**ey Strategy:** Increase engagement + cross-sell second product
**Key Outcome:** Focused targeting can deliver **₹22L+ potential value**

---
