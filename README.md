# 📊 Customer Retention Analysis — Weekly Cohort Tracking
See link to Project Here: [Google Sheet](https://docs.google.com/spreadsheets/d/14kM12hg_r_Uyw9D-x63hqAQT5SDomSeveIny0wqpJlk/edit?gid=1788478059#gid=1788478059) and [SQL](https://console.cloud.google.com/bigquery?sq=147855269776:2eca9498e044429285dacba2a47b9888)
#### 📁 Overview
This project analyzes weekly customer retention using subscription data from a digital platform. It was conducted in response to a Product Manager's request to move away from traditional monthly retention metrics, which can mask critical churn trends in the early lifecycle.

Instead, we built a week-by-week cohort analysis that tracks how many users remain subscribed from week 0 to week 6, based on the week they started their subscription.
📌 Business Objective
> “Track and visualize weekly churn patterns across subscriber cohorts to quickly surface drop-off trends and guide product retention strategies.”

#### 📐 Methodology
> Google BigQuery SQL was used to construct cohort retention model:

📘 Query: cohort_week-based Model ( (Window Functions, CTEs, Date Functions):
* Truncates subscription_start and subscription_end to weekly buckets.
* Uses a cross join with the latest cohort (max_cohort_week) to prevent future-week bias.
* Counts how many users remain active in each subsequent week (0–6).

#### 🔍 Key Insights
🟨 Early Retention Drop

> On average, customer retention dropped by 13.8% each week over the first 6 weeks.

🟩 Best-Performing Cohort: 2020-12-20

> This cohort retained almost 93% of its users after 6 weeks — the lowest churn rate at ~7%.

🟦 Other Strong Cohorts

> The 2020-12-27 cohort followed closely, with less than 8% churn over 6 weeks.

🟥 Stable Retention from 2020-12-06 to 2021-01-24

> Churn rates ranged from 5% to 10%, showing relatively steady customer loyalty during that period.
