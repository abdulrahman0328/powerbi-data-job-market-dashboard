# Data Jobs Market Dashboard

[![Power BI](https://img.shields.io/badge/Power%20BI-Report-F2C811?logo=powerbi&logoColor=111111)](#)
[![DAX](https://img.shields.io/badge/DAX-Measures-6EA8FE)](#)
[![Status](https://img.shields.io/badge/Project-Portfolio%20Analysis-2D2D2D)](#)

## 📸 Dashboard Preview: Market Overview

Here is a quick look at the main interface. The dashboard provides a high-level overview of the market, allowing users to instantly grasp the scale of the data and key financial metrics.

<img width="1217" height="697" alt="v2" src="https://github.com/user-attachments/assets/4d2ce430-0f7b-4388-9d9f-5626b015a6d4" />

> **💡 What you're looking at:**
> *   **Top KPIs:** A snapshot of 479K+ job postings, median yearly ($113K) and hourly ($48) salaries.
> *   **Top Paying Jobs:** A ranking of data roles based on the selected salary metric.
> *   **In-Demand Skills:** The most frequently requested tools (e.g., Python, SQL).
> *   **Hiring Trends & Platforms:** A timeline of posting volume and the top platforms driving the market (e.g., LinkedIn).
> *   **Interactive Slicers:** The filters at the top allow users to drill down by Job Title, Country, and Employment Type.

## 📖 The Story Behind the Dashboard

The global data job market is noisy and constantly shifting. Job seekers and career changers often need to compare information spread across thousands of postings. I built this dashboard to cut through the noise and bring several market signals into one interactive view. 

Instead of just presenting raw numbers, this report is designed to answer critical questions:
*   *Which data roles actually pay the most?*
*   *What skills are most frequently requested (Python, SQL, Cloud)?*
*   *How does compensation vary by country and employment type?*
*   *Which platforms are the most active for hiring?*

## 🎯 Who is this for? (The Audience)

This report is designed for three main audiences:
- **Job seekers** comparing roles, compensation, and frequently requested skills.
- **Career transitioners** identifying skills and job titles worth investigating.
- **Hiring and workforce researchers** exploring posting volume, geography, and recruitment platforms.

## 🚀 The Data Journey (Behind the Scenes)

A dashboard is only as good as the data behind it. Here is how the raw data was transformed into actionable insights:

- **Data Cleaning (Power Query):** Real-world data is messy. I filtered out null salary values to ensure accurate financial calculations, standardized job titles (mapping various titles into a clean `job_title_short` column), and converted text columns (like 'Yes/No') into true Booleans for seamless DAX filtering.
- **Data Modeling (Star Schema):** To keep the report fast and scalable, I avoided a flat table. The model utilizes a Fact Table (`job_postings_fact` containing salaries and IDs) connected to Dimension tables (`company_dim`, `skills_dim`, and a custom `date_dim` for time-intelligence).

## Key Features

- **Market KPIs:** Total job postings, average skills per posting, median yearly salary, and median hourly salary.
- **Top-paying roles:** Compare job titles using the selected compensation metric.
- **In-demand skills:** Identify frequently listed skills such as Python, SQL, cloud platforms, and BI tools.
- **Hiring trends:** Explore job-posting volume over time.
- **Global distribution:** Compare postings across countries.
- **Recruitment platforms:** View leading platforms by posting count.
- **Interactive filtering:** Use Job Title, Country, and Employment Type slicers to narrow the analysis.
- **Dark theme:** Apply the reusable JSON theme in `assets/dark-theme.json` for a consistent visual style.

## Tech Stack

| Tool / Feature | Purpose |
| --- | --- |
| Power BI Desktop | Report design, data model, interactions, and visuals |
| Power Query | Importing, cleaning, transforming, and shaping data |
| DAX | KPI calculations, median salary measures, and dynamic ranking logic |
| JSON report theme | Reusable dark visual styling and color palette |
| Git / GitHub | Version control and project documentation |

## Repository Structure

```text
Data-Jobs-Market-Dashboard/
├── .gitignore
├── LICENSE
├── README.md
├── assets/
│   ├── dashboard-preview.png
