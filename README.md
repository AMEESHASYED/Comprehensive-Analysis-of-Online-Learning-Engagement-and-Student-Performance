# Online Learning Engagement and Student Performance Analysis

An interactive Power BI dashboard, backed by SQL-based analysis, that identifies the factors behind student engagement, academic performance, and dropout on an online learning platform.

## 🎯 Problem

Instructors and coordinators have no consolidated, real-time view of student engagement and performance — so at-risk students are only noticed after they've already disengaged or dropped out.

## 📊 The Data

- **online_education_dataset** — ~32,593 student records: demographics, engagement (clicks), performance (scores), and outcomes (pass/dropout/final result)

## 🛠️ Tech Stack

- **SQL** (MySQL) — exploratory data analysis (`ameesha.sql`)
- **Power BI Desktop** — data modeling, DAX measures, dashboard & report
- **Power Query / DAX** — data cleaning and 5 core measures

## 📈 Key Insights

- Engagement is the strongest predictor of outcomes: **78.10 avg score / 11.9% dropout** for High-engagement students vs. **66.05 avg score / 43.6% dropout** for Low-engagement students
- **31.16%** overall dropout rate; **47.20%** pass rate across 28,785 unique students
- Dropout risk concentrates in specific regions (North Western, West Midlands) and in students with no formal prior qualifications

## 📁 Repository Structure

| Folder | Contents |
|---|---|
| `01_Project_Initialization` | Problem statements, proposal, sprint planning |
| `02_Data_Collection_Preprocessing` | Raw data sources, data quality report, preprocessing notes |
| `03_Data_Visualization` | Business questions & visualization report |
| `04_Dashboard` | Dashboard design doc & screenshots |
| `05_Report` | Report pages (KPI trends + dropout decomposition tree) |
| `06_Executables` | `online_education_dataset.csv`, `online_education.pbix`, `ameesha.sql` |
| `07_Documentation` | Final project report (PDF), demo video |

## 🚀 Getting Started

1. Clone the repo
2. Import `online_education_dataset.csv` into MySQL and run `ameesha.sql` for the exploratory analysis
3. Open `online_education.pbix` in Power BI Desktop to explore the dashboard and report

## 👤 Author

**Ameesha Syed** — MCA, Data Analyst Track
