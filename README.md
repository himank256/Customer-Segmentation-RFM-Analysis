# Customer-Segmentation-RFM-Analysis
The marketing team was running one-size-fits-all campaigns for 3,000+ customers — no segmentation, no prioritization, no personalization.

📊 Raw Data Challenges

Before modeling, the dataset had critical inconsistencies:

150 duplicate customer IDs with conflicting attributes
is_active stored in 6+ inconsistent formats (Y/N/1/0/True/False)
14,000 transactions across GBP, USD, EUR (no FX standardization)
Negative transaction values due to data errors
Invalid foreign keys (transactions without matching customers)
Campaign responses stored in mixed binary formats
City names inconsistent (typos, casing, whitespace issues)

⚙️ ETL + RFM Pipeline Overview
Step 1  → Load & profile raw datasets
Step 2  → Clean customer master (dedup, standardization, tenure calc)
Step 3  → Clean transactions (dates, FX conversion, invalid filtering)
Step 4  → Filter completed transactions
Step 5  → Build RFM features (Recency, Frequency, Monetary)
Step 6  → Score customers (1–5 using quintiles)
Step 7  → Clean campaign response data (binary standardization)
Step 8  → Merge all datasets into unified customer view
Step 9  → Segment customers into 10 actionable groups

📊 RFM Scoring Framework

| **Dimension**       | **Definition**               | **Logic**               | **Weight** |
| ------------------- | ---------------------------- | ----------------------- | ---------- |
| **Recency (R)**     | Days since last transaction  | Lower = better          | 40%        |
| **Frequency (F)**   | Number of transactions       | Higher = better         | 35%        |
| **Monetary (M)**    | Total spend (GBP normalized) | Higher = better         | 25%        |
| **Composite Score** | Weighted score (1–5 scale)   | R×0.4 + F×0.35 + M×0.25 | —          |

🗂️ Customer Segments & Strategy
| **Segment**            | **Count** | **% Base** | **Strategy**          | **Priority** |
| ---------------------- | --------- | ---------- | --------------------- | ------------ |
| Champions              | 377       | 14.0%      | Reward & Upsell       | 🔴 Critical  |
| Loyal Customers        | 475       | 17.7%      | Relationship Building | 🔴 High      |
| At-Risk                | 316       | 11.7%      | Win-Back Campaigns    | 🔴 High      |
| Cannot Lose Them       | 32        | 1.2%       | Immediate RM Outreach | ⚠️ Critical  |
| New Customers          | 277       | 10.3%      | Onboarding Campaigns  | 🟡 Medium    |
| Potential Loyalists    | 155       | 5.8%       | Nurturing             | 🟡 Medium    |
| Hibernating High Value | 212       | 7.9%       | Reactivation          | 🟡 High      |
| Promising              | 85        | 3.2%       | Engagement Boost      | 🟢 Medium    |
| Need Attention         | 481       | 17.9%      | Automated Nurture     | 🟢 Low       |
| Lost                   | 280       | 10.4%      | Churn Analysis        | ⚫ Low        |


📈 Key Business Insights
1. Identified £97M at-risk revenue pool (At-Risk + Cannot Lose Them segments)
2. Champions & Loyal Customers contribute disproportionate revenue share
3. Significant opportunity in reactivating dormant high-value users
4. Email targeting can be optimized using segment-specific personalization

📦 Deliverables
📁 Cleaned RFM master dataset (2,690 customers, 30 features)
📊 4-tab Excel segmentation dashboard
🐍 Python ETL + segmentation pipeline
🧾 Data audit log
📄 Case study report

🧠 Skills Demonstrated

RFM Modeling · Customer Segmentation · ETL Pipelines · Data Cleaning · FX Conversion · pandas · CRM Analytics · Marketing Strategy
