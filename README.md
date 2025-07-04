# Cohort-Opportunity-Insights
Final capstone project for the Excelerate Data Analyst Associate Internship. Built a complete PostgreSQL data pipeline and an interactive Power BI dashboard to deliver cohort-based insights on learner engagement, enrollment trends, and campaign efficiency.

---

# 📊 End-to-End Data Integration & Power BI Dashboard for Cohort Analytics
**Capstone Project | Excelerate Data Analyst Associate Internship**

This repository showcases a comprehensive analytics solution built as the final capstone for the Excelerate Data Analyst Associate Internship. I led the design and execution of a complete **data engineering and visualization pipeline**, transforming disjointed raw CSV files into a relational data warehouse and delivering an **interactive Power BI dashboard** for strategic decision-making.

---

## 💼 Project Objective

The core challenge addressed in this project was the **fragmentation of learner and program data across multiple flat files**, which hindered real-time insights into enrollment patterns, opportunity distribution, and campaign performance.

### ✔️ Solution Overview:
- Built an **ETL pipeline using PostgreSQL** to integrate six independent datasets into a normalized schema.
- Created a **production-ready `master_enrollments` table** using stored procedures, key constraints, and optimized queries.
- Delivered a **business-ready Power BI dashboard** with DAX measures, dynamic filters, drill-down logic, and executive-level KPIs.

---

## 🧠 Business Goals

- Enable **cohort-wise tracking** of learner progress and opportunity engagement.
- Provide **spending insights per cohort** for better budget allocation.
- Surface **year-over-year enrollment trends** to evaluate program scaling.
- Deliver **real-time, decision-support dashboards** to stakeholders via Power BI.

---

## 🔍 Data Architecture & Engineering Pipeline

### 🔹 1. Data Sources & Domains
| Dataset | Domain |
|--------|--------|
| `user_data.csv` | Learner profiles |
| `cohort_data.csv` | Program timelines |
| `opportunity_data.csv` | Application & opportunity metadata |
| `learner_opportunity_data.csv` | Learner engagement & status |
| `cognito_data.csv` | Demographics |
| `marketing_campaign_data.csv` | Campaign performance & spending |

### 🔹 2. PostgreSQL Setup
- Developed a fully normalized schema with referential integrity.
- Defined constraints and indexes for performance optimization.
- Implemented `COPY` command for CSV ingestion:
  - `ENCODING = 'LATIN1'` to handle special characters
  - NULL strings converted to SQL NULLs
  - Header alignment verified per schema

### 🔹 3. Transformation Logic
- Created `load_master_enrollments()` stored procedure to:
  - Join six tables via `learner_id`, `opportunity_id`, `cohort_code`
  - De-duplicate using `ROW_NUMBER()` window function
  - Normalize inconsistent formats using `LOWER()`, `TRIM()`, `INITCAP()`
  - Convert UNIX timestamps to SQL `TIMESTAMP`
  - Fuzzy-match campaign data using `ILIKE` operator
- Final destination: `master_enrollments` → clean, enriched, query-optimized table

---

## 📊 Dashboard Design – Power BI

Here is a glimpse of the dashboard:

<img width="616" alt="image" src="https://github.com/user-attachments/assets/2e298cf9-7e20-46db-83e3-9c8a3d18017d" />


### 🔸 Core Visuals
- 📈 **Total Enrollment by Year**  
- 🧑‍🎓 **Opportunities by Cohort Code**
- 💸 **Campaign Spend by Cohort**
- ⏱️ **Application Status Over Time**
- 📍 **Dynamic Filtering by Cohort, Year, Status**

---

### 🔸 Technical Stack
- **Power BI Desktop**
- **DAX for calculated measures**
- **Power Query (M) for backend shaping**
- Hierarchies & drill-throughs to enable multi-level insight
- Focus on performance: minimized visuals, optimized refresh paths

---

## 📈 Key Strategic Insights

- **Scalability Evidence:** Enrollment grew significantly across years, validating program expansion.
- **Engagement Trends:** Certain cohorts showed higher opportunity conversion rates—ideal for deeper targeting.
- **Budget Efficiency:** Identified mismatches in campaign spend vs. actual enrollment output.
- **Demographic Representation:** Segmented cohort analysis helped address gaps in inclusion and outreach.

---

## ✅ Outcome & Impact

- Reduced analytics workload by centralizing previously scattered data.
- Created a single source of truth (`master_enrollments`) for reporting and future automation.
- Delivered a **clean, fast, interactive Power BI dashboard** tailored for leadership review and cohort planning.
- Reinforced data governance and quality practices (type enforcement, timestamp normalization, fuzzy joins).

---

## 🗂️ Repository Contents

| File | Description |
|------|-------------|
| `Dashboard.docx` | Final Power BI interactive dashboard |
| `Presentation.pptx` | Slide deck summarizing business problem, solution, and process |

---

## 🧰 Tech Stack

- **Languages/Tools:** SQL (PostgreSQL), DAX, M (Power Query), Power BI Desktop
- **ETL Focus:** Data cleansing, transformation, deduplication, enrichment
- **Visualization:** KPI cards, column charts, donut charts, time-series, filters
- **Workflow Tools:** Excel, OneDrive (sharing), Looker Studio (prototype stage)

---

# Connect With Me

If you enjoyed this project or have feedback, feel free to connect with me!

[LinkedIn](https://www.linkedin.com/in/akshitha-thatla/) 

[Github](https://github.com/Akshitha-git06)

---

## Thank you for checking out my project!
