# Intermediate SQL - Sales Analysis

## Overview
This project uses SQL (PostgreSQL) to analyze customer behavior, revenue patterns, and retention for an e-commerce business.
The goal is to identify high-value customers, understand revenue trends across cohorts, and detect churn risks to support data-driven retention and revenue optimization strategies.

## Business Questions

1. Who are our most valuable customers?
2. How does customer revenue evolve across acquisition cohorts?
3. Which customers are at risk of churning?
4. Where should the business focus retention and re-engagement efforts?

## Tools & Technologies

- Database: PostgreSQL
- CTEs & Views
- Aggregations & GROUP BY
- Window Functions (ROW_NUMBER, LAG, cumulative metrics)
- Cohort Analysis (First purchase date logic)
- Customer Lifetime Value (LTV)
- Retention & churn identification

## Clean Up Data

**🖥️ Query**: [0_create_view.sql](0_create_view.sql)

- Aggregated sales and customer data into revenue metrics
- Calculated first purchase dates for cohort analysis
- Created a unified analytical view combining transactions and customer attributes

## Analysis

### 1. Customer Segmentation

**🖥️ Query**: [1_customer_segmentation.sql](1_customer_segmentation.sql)

Customers were segmented into High, Mid, and Low-value groups based on lifetime revenue contribution.

**📈 Visualization:**

<img src="images\6.3_customer_segementation.png" alt="Customer Segmentation" width="50%">

📊 **Key Findings:**

- High-value customers (25%) generate 66% of total revenue ($135.4M)
- Mid-value customers (50%) contribute 32% of revenue ($66.6M)
- Low-value customers (25%) account for only 2% of revenue ($4.3M)

💡 **Business Impact**

- Revenue is highly concentrated among a small customer segment
- Retaining high-value customers has a disproportionate impact on profitability

### 2. Customer Revenue by Cohort
**🖥️ Query**: [2_cohort_analysis.sql](2_cohort_analysis.sql)

Customers were grouped by year of first purchase to evaluate long-term revenue behavior.

**📈 Visualization:**

> ⚠️ Note: This only includes 2 charts. 

Customer Revenue by Cohort (Adjusted for time in market) - First Purchase Date 

<img src="images\5.2_customer_revenue_normalized.png" width="50%">

Investigate Monthly Revenue & Customer Trends (3 Month Rolling Average)

<img src="images\5.2_monthly_revenue_customers_3mo.png" width="50%">  

📊 **Key Findings:**  
- Older cohorts (2016–2018) show significantly higher lifetime revenue (~$2,800+)
- Newer cohorts (2024) show reduced spending (~$1,970)
- Revenue and customer counts peaked in 2022–2023 and declined in 2024
- High volatility suggests retention instability 

💡 **Business Impact:**  
- Declining cohort performance indicates weakening customer loyalty
- Revenue sustainability depends on improving early cohort engagement

### 3. Customer Retention
🖥️ Query: [3_retention_analysis.sql](3_retention_analysis.sql)

Customer activity was analyzed to identify churn risk and long-term retention patterns.

**📈 Visualization:**

<img src="images\7.3_customer_churn_cohort_year.png" alt="Customer Churn by Cohort Year" style="width: 50%; height: auto;">

📊 **Key Findings:**  
- Churn stabilizes at ~90% after 2–3 years across cohorts
- Retention rates remain low (8–10%) regardless of cohort year
- Newer cohorts follow the same churn trajectory as older ones

💡 **Business Impact:**  
- Retention issues are systemic, not cohort-specific
- Early lifecycle engagement is critical to long-term customer value

## Strategic Recommendations


### Customer Value Optimization
- Launch VIP program for 12,372 high-value customers
- Develop personalized upgrade paths for mid-value customers
- Use price-sensitive promotions for low-value customers to increase frequency
### Cohort Performance Improvement
- Target 2022–2024 cohorts with personalized re-engagement campaigns
- Introduce loyalty or subscription models to stabilize revenue
- Apply strategies from high-performing cohorts (2016–2018) to newer users
### Retention & Churn Prevention
- Strengthen first 1–2 year engagement with onboarding and loyalty incentives
- Focus win-back campaigns on churned high-value customers
- Implement churn risk indicators for proactive intervention

## Conclusion

- This project demonstrates how SQL can be used beyond reporting—serving as a foundation for customer analytics, retention strategy, and revenue optimization.
- The analysis highlights how structured queries and business logic can directly inform strategic decision-making in an e-commerce environment.
