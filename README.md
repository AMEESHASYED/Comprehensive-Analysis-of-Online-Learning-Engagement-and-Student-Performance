# 📊 Online Learning Engagement and Student Performance Analysis

A data analytics project that explores student engagement and academic performance on an online learning platform, using **SQL** for exploratory analysis and **Power BI** for interactive dashboarding and visualization.

---

## 📌 Project Overview

Online learning platforms often struggle to identify students at risk of dropping out or underperforming. This project analyzes student-level data — engagement (clicks), academic performance (scores), and outcomes (pass/dropout) — to uncover patterns and build an interactive Power BI dashboard that helps stakeholders monitor and act on these insights.

**Objectives:**
- Evaluate overall student engagement and academic performance using KPIs
- Identify key factors contributing to student dropout
- Compare performance across region, gender, education level, and risk level
- Build an interactive Power BI dashboard for exploration and decision-making

---

## 🗂️ Repository Contents

| File | Description |
|---|---|
| `dataset.pbix` | Power BI Desktop file containing data model, DAX measures, dashboard, and report pages |
| `online_education_dataset.csv` | Raw dataset used for analysis (student-level records) |
| `ameesha.sql` | SQL script used for exploratory data analysis prior to building the dashboard |

---

## 🧾 Dataset Description

The dataset (`online_education_dataset.csv`) contains **32,593 student records** with the following columns:

| Column | Description |
|---|---|
| `id_student` | Unique student identifier |
| `gender` | Student gender (M/F) |
| `region` | Geographic region of the student |
| `highest_education` | Highest prior education qualification |
| `studied_credits` | Number of credits studied |
| `imd_band` | Index of Multiple Deprivation band (socio-economic indicator) |
| `total_clicks` | Total number of clicks/interactions on the platform |
| `avg_score` | Average academic score of the student |
| `engagement_level` | Categorized engagement (Low / Medium / High) |
| `performance_level` | Categorized academic performance (Low / Medium / High) |
| `risk_level` | Categorized dropout risk (Low / Medium / High / Very High Risk) |
| `pass_flag` | 1 = Passed, 0 = Did not pass |
| `dropout_flag` | 1 = Dropped out, 0 = Did not drop out |
| `final_result` | Final outcome (Pass / Fail / Withdrawn / Distinction) |

---

## 🛢️ SQL Analysis (`ameesha.sql`)

Before building the dashboard, exploratory analysis was performed in SQL to understand key trends. Highlights include:

- **Core KPIs:** total students, average score, average clicks
- **Engagement analysis:** student distribution and average score by engagement level
- **Performance analysis:** student count and average score by performance level
- **Risk analysis:** student distribution by risk level
- **Dropout analysis:** dropout rate by engagement level and performance level
- **Click-band analysis:** average score across click ranges (0–500, 500–1000, 1000–2000, 2000–3000, 3000+)
- **Regional analysis:** average score and clicks by region
- **Educational background analysis:** average score and clicks by prior education level

Run the script in MySQL (or any compatible RDBMS) after creating the `online_education_db` database and importing `online_education_dataset.csv` into a table named `online_education_dataset`.

```sql
create database online_education_db;
use online_education_db;
-- then load online_education_dataset.csv into the online_education_dataset table
```

---

## 📈 Power BI Dashboard (`dataset.pbix`)

### KPI Cards
| KPI | Description |
|---|---|
| **Total Students** | Overall student population in the dataset |
| **Dropout Rate (%)** | Percentage of students who dropped out |
| **Average Score** | Average academic score across all students |
| **Average Clicks** | Average platform interaction per student |
| **Pass Rate (%)** | Percentage of students who passed the course |

### DAX Measures Used
```DAX
Total Students = DISTINCTCOUNT('online_education_dataset'[id_student])

Dropout Rate = 
DIVIDE(
    CALCULATE(COUNTROWS('online_education_dataset'), 'online_education_dataset'[dropout_flag] = 1),
    [Total Students]
) * 100

Average Score = AVERAGE('online_education_dataset'[avg_score])

Average Clicks = AVERAGE('online_education_dataset'[total_clicks])

Pass Rate = 
DIVIDE(
    CALCULATE(COUNTROWS('online_education_dataset'), 'online_education_dataset'[pass_flag] = 1),
    [Total Students]
) * 100
```

### Visualizations
- KPI Cards (Total Students, Dropout Rate, Average Score, Average Clicks, Pass Rate)
- Line chart — trend analysis
- Horizontal bar chart — comparisons across categories (e.g., region, education level)
- Donut chart — distribution breakdown (e.g., engagement/risk level)
- Pie chart — outcome distribution (Pass/Fail/Withdrawn/Distinction)
- AI-powered Decomposition Tree — drill-down analysis of factors affecting KPIs

### Interactive Filters / Slicers
The dashboard includes six dynamic slicers that let users interactively explore the data:
1. Gender
2. Engagement Level
3. Region
4. Performance Level
5. Risk Level
6. Final Result

Selecting any filter dynamically updates all KPIs and visuals, allowing comparison across student segments.

---

## 🔍 Key Insights

- Students with **higher engagement levels** tend to have higher average scores and lower dropout rates.
- **Low click-band students** (fewer platform interactions) show a noticeably higher dropout rate.
- Dropout rate varies meaningfully across **region** and **performance level**, highlighting where intervention may be needed.
- Students with **higher prior education** tend to have better average scores.

*(Update this section with the exact numbers/insights from your final dashboard.)*

---

## 🛠️ Tech Stack

- **SQL** (MySQL) — data exploration and aggregation
- **Power BI Desktop** — data modeling, DAX measures, and dashboard/report design
- **CSV** — source dataset

---

## 🚀 How to Use

1. Clone this repository:
   ```bash
   git clone <repo-url>
   ```
2. **SQL analysis:** Import `online_education_dataset.csv` into a MySQL database and run `ameesha.sql`.
3. **Power BI dashboard:** Open `dataset.pbix` in Power BI Desktop to explore the interactive dashboard and report pages.

---

## 👤 Author

Ameesha Syed


---

## 📄 License

This project is for educational/portfolio purposes.
