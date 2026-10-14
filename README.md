# 📊 Customer Churn Analysis & Customer Intelligence

An end-to-end **Data Analytics Project** focused on understanding customer churn, subscription behaviour, revenue impact, and customer-support patterns in an OTT-style subscription business.

This project combines **SQL and Python** to transform raw customer data into meaningful insights and actionable business recommendations. 💡

> 🎯 **Project Type:** Data Analytics | Exploratory Data Analysis (EDA)  
> 🛠️ **Tools:** Python, SQL, SQLite, Pandas, NumPy, Matplotlib, Seaborn, Jupyter Notebook

---

## 📌 Table of Contents

- [🔍 Project Overview](#-project-overview)
- [💼 Business Problem](#-business-problem)
- [🎯 Project Objectives](#-project-objectives)
- [🗂️ Dataset and Database Structure](#️-dataset-and-database-structure)
- [🛠️ Tools and Technologies](#️-tools-and-technologies)
- [🔄 Project Workflow](#-project-workflow)
- [📈 Key Performance Indicators](#-key-performance-indicators)
- [🔎 Key Findings](#-key-findings)
- [💡 Business Recommendations](#-business-recommendations)
- [📁 Repository Structure](#-repository-structure)
- [⚙️ Getting Started](#️-getting-started)
- [📊 Expected Outputs](#-expected-outputs)
- [⚠️ Limitations](#️-limitations)

---

## 🔍 Project Overview

Customer churn occurs when customers stop using a product or service. Understanding why customers leave, when they cancel subscriptions, and which customer segments are most affected can help businesses improve retention and protect recurring revenue.

This project analyses customer demographics, subscription details, cancellation records, churn-risk scores, and customer-support information to identify churn patterns and potential areas for improvement.

The project demonstrates practical data analytics skills, including **SQL-based data extraction, data cleaning, feature engineering, exploratory data analysis, KPI calculation, and data visualisation**.

## 💼 Business Problem

Subscription-based businesses operate in a competitive environment where retaining existing customers is essential for sustainable growth.

High customer churn can result in:

- 📉 Reduced recurring revenue
- 💸 Revenue loss and declining customer lifetime value (CLTV)
- ⚠️ Increased customer acquisition costs
- 📊 Poor customer-retention performance

This project investigates three key business questions:

- 👥 **Who is leaving?** Identify churned customers and high-risk customer segments.
- 🔍 **Why are customers leaving?** Explore patterns related to subscription plans, contract types, locations, and support interactions.
- ⏳ **When are customers leaving?** Identify cancellation trends and periods that may require further investigation.

## 🎯 Project Objectives

- 🔗 Connect Python to a relational SQLite database and retrieve data using SQL.
- 🧹 Clean and prepare customer, subscription, and support datasets.
- 🏗️ Perform feature engineering to create churn flags, customer tenure, and churn-risk categories.
- 📈 Calculate important business KPIs, including churn rate, retention rate, ARPU, and revenue impact.
- 🔎 Explore churn patterns across subscription plans, contract types, geographical regions, and support interactions.
- 📊 Create visualisations to communicate analytical findings.
- 💡 Translate data-driven insights into actionable customer-retention recommendations.

## 🗂️ Dataset and Database Structure

The project uses a relational database named `customer_churn`, containing three main tables connected through `customerid`.

| Database Table | Description | Example Fields |
|---|---|---|
| `db_customer` | Customer demographic information | `customerid`, `name`, `country`, `state`, `gender`, `dob` |
| `db_subscription` | Subscription and billing information | `subscription_start_date`, `plan_type`, `contract_type`, `cancellation_date`, `monthly_charges`, `cltv`, `churn_score` |
| `db_support` | Customer complaints and support information | `customerid`, `complaint_date`, `Escalations`, `csat_score`, `comment` |

📌 The notebook also includes an optional database-creation step using an Excel workbook named `customer_churn_data_raw.xlsx`.

**Note:** The original dataset must be available separately to execute the analysis from the beginning.

## 🛠️ Tools and Technologies

| Technology | Purpose |
|---|---|
| 🐍 Python | Data analysis and processing |
| 🗃️ SQL | Data extraction and relational queries |
| 🪶 SQLite | Database management |
| 🐼 Pandas | Data cleaning, manipulation, and aggregation |
| 🔢 NumPy | Numerical operations and feature engineering |
| 📊 Matplotlib | Data visualisation |
| 🎨 Seaborn | Statistical visualisation and heatmaps |
| 📓 Jupyter Notebook | Interactive analysis and documentation |

## 🔄 Project Workflow

### 1️⃣ Database Connection and Data Extraction
- Connected Python to SQLite using `sqlite3`.
- Inspected database tables and columns.
- Retrieved data using SQL queries and Pandas.

### 2️⃣ Data Cleaning and Preparation 🧹
- Renamed columns for clarity.
- Removed unnecessary customer attributes.
- Converted date columns to appropriate datetime formats.
- Standardised category values.
- Handled missing country values using available state-to-country mappings.
- Calculated complaint counts and handled duplicate customer records in the support data.

### 3️⃣ Feature Engineering 🏗️
- Created a `churn_flag` based on the presence of a cancellation date.
- Calculated customer tenure in days.
- Categorised customers into Low, Medium, and High churn-risk groups using `churn_score`.
- Combined customer, subscription, and support information using `customerid`.
- Exported the integrated dataset to `exported_churn_data.csv`.

### 4️⃣ Exploratory Data Analysis (EDA) 🔎
- Calculated overall churn and retention rates.
- Compared churn across subscription plans and contract types.
- Analysed cancellation trends over time.
- Investigated regional churn patterns.
- Examined revenue and customer-support metrics.
- Used aggregations, grouping, and pivot tables to summarise the data.

### 5️⃣ Data Visualisation 📊
- 📅 Monthly customer-cancellation trends
- 📦 Churn rate by subscription plan
- 🌍 Churn rate by state
- 🔥 Correlation heatmaps
- 📈 Pair plots and category comparisons
- 👥 Analysis by plan, gender, and churn-risk segment

## 📈 Key Performance Indicators

| KPI | Description |
|---|---|
| 📉 Churn Rate | Percentage of customers who have churned |
| 🔄 Retention Rate | Percentage of customers retained |
| 📦 Churn by Plan | Churn rate across Basic, Standard, and Premium plans |
| 📃 Churn by Contract | Comparison of monthly and annual contract churn |
| 💰 ARPU | Average revenue per user, based on the notebook's calculation |
| ⏳ Average Tenure | Average customer subscription duration in days |
| ⚠️ Revenue at Risk | Revenue metric calculated using the notebook's churn definition |
| 🎧 Escalation Rate | Percentage of support records with an escalation indicator of `Y` |
| 💬 Average Complaints per Customer | Average number of complaints per customer |
| 🔗 Escalation–Churn Correlation | Association between support escalations and customer churn |

## 🔎 Key Findings

The accompanying project report presents the following results:

| Metric | Reported Result |
|---|---:|
| 📉 Overall Churn Rate | 28.6% |
| 🔄 Retention Rate | 71.4% |
| 📃 Monthly Contract Churn | 55.6% |
| 📃 Annual Contract Churn | 8.3% |
| ⏳ Average Customer Tenure | 1,451 days |
| 💰 ARPU | Rs 18.8 |
| 💸 Total Revenue | 395 |
| ⚠️ Revenue Loss Attributed to Churn | Approximately 74 |
| 📉 Reported CLTV Lost | 2,047 |
| 💹 Reported Revenue Loss | 18% |

### 🧠 Important Observations

- 📌 Monthly-contract customers showed a substantially higher reported churn rate than annual-contract customers.
- 📦 The report identified the Basic subscription plan as having a large share of churned customers.
- 📅 September 2024 was reported as the month with the highest customer churn.
- 🌍 Karnataka was identified as the most affected state.
- 💸 The reported monthly recurring revenue (MRR) leakage was approximately 73.94, with CLTV erosion of 2,047 attributed to six at-risk customers.

*Note: These are findings reported in the supplied project materials. They should be validated against the underlying dataset before being used for business decisions.*

## 💡 Business Recommendations

Based on the patterns highlighted in the analysis, the following actions are recommended for further investigation:

1. 📃 **Investigate monthly-contract churn:** Examine renewal behaviour and evaluate whether suitable annual-plan options could improve retention.
2. 📅 **Investigate the September 2024 churn spike:** Review pricing changes, technical issues, customer complaints, and content-related changes during that period.
3. 🌍 **Analyse regional churn differences:** Investigate customer experiences and support records in Karnataka before determining the underlying causes.
4. 🎯 **Prioritise high-risk customers:** Use churn-risk scores, customer lifetime value, and support history to prioritise retention outreach.
5. 🎧 **Improve customer-support experiences:** Investigate whether escalated complaints are associated with higher churn.
6. 📊 **Monitor retention KPIs:** Track churn rates, revenue impact, and customer-support trends over time to evaluate future retention initiatives.

These recommendations represent potential business actions to investigate. The analysis does not establish that any single factor caused customer churn.

## 📁 Repository Structure

```text
customer-churn-analysis/
│
├── churn_analysis.ipynb
├── Data Analytics Project - Churn Analysis Report.pdf
├── customer_churn.db
├── exported_churn_data.csv
└── README.md
```

📌 The database, Excel source workbook, and exported CSV should be included only when available and appropriate to share. Avoid uploading confidential customer information.

## ⚙️ Getting Started

### 1. Clone the Repository

```bash
git clone <your-repository-url>
cd customer-churn-analysis
```

Replace `<your-repository-url>` with your actual GitHub repository URL.

### 2. Install Dependencies

Create and activate a virtual environment:

```bash
python -m venv .venv
```

**Windows:**
```bash
.venv\Scripts\activate
```

**macOS / Linux:**
```bash
source .venv/bin/activate
```

Install the required Python libraries:

```bash
pip install numpy pandas matplotlib seaborn jupyter openpyxl
```

`sqlite3` is included in Python's standard library and normally does not require separate installation.

### 3. Prepare the Dataset 📂

Place `customer_churn.db` in the working directory, or provide `customer_churn_data_raw.xlsx` if using the notebook's optional database-creation section.

Ensure that the source data contains the tables and columns expected by the notebook.

### 4. Run the Jupyter Notebook ▶️

```bash
jupyter notebook churn_analysis.ipynb
```

Run the cells in order, beginning with database setup and data extraction.

### 5. Explore the Results 📊

Review the generated dataset, KPI summaries, analysis tables, and visualisations displayed throughout the notebook.

## 📊 Expected Outputs

- ✅ Cleaned customer, subscription, and support datasets
- 🔗 Integrated churn-analysis dataset
- 📄 `exported_churn_data.csv`
- 📈 Churn and retention KPI summaries
- 📦 Contract and plan-level comparisons
- 📅 Monthly churn trend visualisations
- 🔥 Correlation heatmaps and exploratory charts
- 💡 Data-driven customer-retention recommendations

## ⚠️ Limitations and Notes

- 📌 This project focuses on descriptive analytics and exploratory data analysis rather than a trained predictive machine-learning model.
- 📊 Results depend on the source dataset and the churn definition used.
- 🧮 The notebook defines churn using a non-null `cancellation_date`.
- 🔗 Correlation between customer-support escalations and churn does not prove causation.
- 🗂️ Support data is reduced to customer-level records for merging after complaint counts are calculated, which may limit interaction-level analysis.
- 💰 Revenue figures and units should be verified against the source data and calculation formulas before being used in external reporting.
- 🔍 Some notebook sections contain exploratory SQL examples in addition to the main analysis workflow.

---

⭐ If you find this project useful, feel free to explore the notebook and adapt the analytical workflow to other subscription-based business scenarios.

🚀 *Keep learning, keep analysing, and keep growing!*
