# Power BI: Data Jobs Market Analysis (Portfolio Hub)

[![Power BI](https://img.shields.io/badge/Power%20BI-Portfolio-F2C811?logo=powerbi&logoColor=111111)](#)
[![DAX](https://img.shields.io/badge/DAX-Advanced%20Measures-6EA8FE)](#)
[![Status](https://img.shields.io/badge/Project-Multiple%20Iterations-2D2D2D)](#)

Welcome to my Data Job Market Analysis repository! This repository serves as a central hub for my Power BI projects exploring the global data market. 

The goal of this project is to uncover hiring trends, salary distributions, and in-demand skills, while practicing advanced Data Modeling, DAX, and UI/UX design. The analysis has evolved through multiple iterations:

## 📂 Project Directory

### 🟢 [Version 1: Initial Data Exploration & Foundation](https://github.com/abdulrahman0328/powerbi-data-job-market-dashboard)
*Located in: `Data_jobs_V1/`*
<img width="1150" height="664" alt="Screenshot 2026-08-21 173624" src="https://github.com/user-attachments/assets/3f220857-fcf7-4b18-b68d-75df6ead0fe7" />

*   **Focus:** Establishing the data model, cleaning the raw dataset (479K+ postings), and creating a foundational dashboard.
*   **Technical Highlights:** 
    *   **Power Query:** Extensive ETL, handling nulls, and standardizing job titles.
    *   **Data Modeling:** Built a Star Schema (Fact & Dimensions) for optimal performance.
    *   **DAX:** Implemented `MEDIAN` calculations to avoid skewed averages from outliers.
    *   **UI/UX:** Applied a basic Dark Mode JSON theme.

### 🔵 Version 2: Advanced Analytics & UI Refinement (Current)
*Located in: `Data_jobs_V2/`*
## 📸 Dashboard Preview: Market Overview
<img width="1217" height="697" alt="Screenshot 2026-10-20 155648" src="https://github.com/user-attachments/assets/56eaf99f-ff7b-4ea3-b8b0-69afd39a8364" />

*   **Focus:** Upgrading the technical depth of the report and refining the user experience based on V1 feedback.
*   **Technical Highlights:**
    *   **Advanced DAX:** Moved beyond basic aggregations to implement **Dynamic Ranking** using `RANKX`. This allows visuals (like Top 5 Jobs) to update automatically based on user slicers (e.g., filtering by Country).
   
    *   **Data Storytelling Layout:** Reorganized the report pages logically (Market Pulse vs. Compensation) to guide the user's eye through a narrative rather than isolated charts.
    *   **Advanced Visuals:** Added a scatter plot for Skills vs. Salary and structured the Top Platforms visual for better readability.
Here is a quick look at the main interface. The dashboard provides a high-level overview of the market, allowing users to instantly grasp the scale of the data and key financial metrics.
> **💡 What you're looking at:**
> *   **Top KPIs:** A snapshot of 479K+ job postings, median yearly ($113K) and hourly ($48) salaries.
> *   **Top Paying Jobs:** A ranking of data roles based on the selected salary metric.
> *   **In-Demand Skills:** The most frequently requested tools (e.g., Python, SQL).
> *   **Hiring Trends & Platforms:** A timeline of posting volume and the top platforms driving the market (e.g., LinkedIn).
> *   **Interactive Slicers:** The filters at the top allow users to drill down by Job Title, Country, and Employment Type.
---

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

## 🛠️ Core Tech Stack Used

| Tool / Feature | Purpose |
| --- | --- |
| Power BI Desktop | Report design, data model, interactions, and visuals |
| Power Query | Importing, cleaning, transforming, and shaping data |
| DAX | KPI calculations, median salary measures, and dynamic ranking logic  |
| Git / GitHub | Version control and project documentation |

