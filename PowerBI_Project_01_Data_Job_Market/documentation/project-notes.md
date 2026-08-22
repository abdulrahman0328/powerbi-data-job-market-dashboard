# 📖 Project Documentation — Data Job Market Dashboard

**Project:** Power BI Report — Data Job Market Dashboard  
**Author:** Abdulrahman Muhammad  
**Tools:** Power BI · DAX · Power Query · Excel  
**Status:** ✅ Completed — Project #01

---

## The Story Behind This Report

Every week, thousands of people search for their next data role.  
They open job boards, scroll through listings, and try to piece together a picture of the market — one posting at a time.

But the picture is never complete.

Salary information is scattered. Job platforms don't agree. Some roles are remote, some aren't. Some require a degree, others don't mention it at all.

**This dashboard was built to solve that fragmentation.**

Instead of searching across platforms and guessing, a job seeker, a career switcher, or anyone exploring data roles can open one report and find what they need — clearly, quickly, and interactively.

---

## Chapter 1 — Defining the Problem

Before touching any data or building any visual, the first question was:

> **Who is this report for, and what do they actually need to know?**

Three types of people came to mind:

- **Job Seekers** — looking for real salary numbers and which platforms have the most postings
- **Career Switchers** — comparing roles to understand what's realistic for someone transitioning into data
- **Job Explorers** — people who want a broad view of the market before committing to a direction

Once the audience was clear, the business questions followed naturally:

| Question | Why It Matters |
|---|---|
| How many data jobs exist? | Gives a sense of market size |
| What are typical salaries? | Sets realistic expectations |
| How do salaries differ by job title? | Helps people choose a direction |
| How does job demand change over time? | Reveals seasonal and market trends |
| Which platforms post the most jobs? | Tells job seekers where to focus |
| How are jobs distributed globally? | Useful for remote or relocation decisions |
| How common is WFH? | Critical for lifestyle decisions |
| Do most roles require a degree? | Helps people without degrees understand their options |

These questions became the blueprint for every visual in the report.

---

## Chapter 2 — Preparing the Data

The dataset came in through **Excel**, containing job postings with fields like job title, salary (yearly and hourly), employer name, location, platform, employment type, WFH availability, and degree requirements.

**Power Query** handled the preparation:

- Removed nulls and inconsistent entries
- Standardized job title names
- Separated yearly and hourly salary columns
- Cleaned platform names for consistent grouping
- Parsed date fields to enable time-based filtering

The goal at this stage was simple: arrive at a clean, reliable table that Power BI could model and query without surprises.

---

## Chapter 3 — Building the Report

The report was structured across **two pages**:

1. **Main Dashboard** — the market overview
2. **Job Title Drill-Through** — a deep dive into a single role

This separation was intentional. The main dashboard answers broad questions. The drill-through page answers specific ones.

---

### 🏠 The Home Page

The first page a user sees is not the dashboard — it's a landing screen.

![Home Page](assets/01_Home.png)

The home page was designed to communicate three things immediately:

1. **What this report is about** — *"The Data Job Market, All in One Place"*
2. **Who built it and why** — author identity, mission statement
3. **How to navigate** — a clear *"Go To The Dashboard"* button, plus links to Portfolio, LinkedIn, and GitHub

This screen sets the tone. It tells the user they are about to explore something purposeful, not just a collection of charts.

---

### 📊 The Main Dashboard

![Main Dashboard](assets/02_Dashboard.png)

The main dashboard opens with four KPI cards at the top:

| KPI | Value |
|---|---|
| **Job Count** | 479K |
| **Job Rating** | ⭐⭐⭐⭐⭐ (DAX star rating measure) |
| **Median Yearly Salary** | $113K |
| **Median Hourly Salary** | $48 |

These four numbers tell the story of the market in seconds. Before a user reads a single chart, they already know the scale and the salary range.

**Below the KPIs, the story continues in layers:**

**Job Trending in 2024**  
A line chart showing monthly job postings throughout the year. The market peaked in February at 55K and fell significantly toward the end of the year, dropping to 14K in November before a slight recovery in December. This pattern suggests that hiring activity is front-loaded — most opportunities appear in the first half of the year.

**Median Yearly Salary vs. Median Hourly Salary**  
A scatter plot that maps the relationship between yearly and hourly compensation across job titles. The positive correlation — higher yearly salaries tend to correspond to higher hourly rates — is visible immediately, and the dashed trend line makes the direction clear.

**Job Title Breakdown Table**  
A table listing the top job titles with their job count, median yearly salary, median hourly salary, and a sparkline trend. This is where the real comparison happens:

- Data Analyst: 112K jobs — $90K/year
- Data Engineer: 129K jobs — $126K/year
- Machine Learning Engineer: 13K jobs — $155K/year

Higher pay tends to correlate with lower volume. Niche roles pay more but have fewer openings. The table makes this trade-off visible.

**Filters Panel**  
On the right side, two filters control the entire dashboard:

- **Job Title** — dropdown with all available titles
- **Posted Date** — a date slider from 1/1/2024 to 12/31/2024

A *"Clear all Filters"* button resets the view. The Drill-through button in the top-right sends the user to the job-level detail page for the currently selected title.

---

### 🔎 The Job Title Drill-Through Page

![Job Title Drill-Through](assets/03_job_title_drillthrough.png)

When a user selects a specific job title — for example, **Data Analyst** — and triggers the drill-through, they arrive at a page dedicated entirely to that role.

The page opens with the selected title as a large heading: *"Job Title Drilled — Data Analyst"*

**What the user sees:**

**Salary Gauges**  
Two gauge visuals show average vs. median salary — both yearly and hourly. For Data Analyst:
- Median Yearly: $93K (Average: $94K, range: $18K–$445K)
- Median Hourly: $33 (Average: $39, range: $8–$140)

The wide salary range across both metrics tells an important story: this role varies enormously depending on employer, location, and seniority — even though the median sits at a reliable number.

**Work From Home (WFH)**  
A donut chart: 8K roles offer WFH, 75K do not. For Data Analyst, remote work is not the norm — it is the exception. This is useful context for anyone expecting flexibility.

**Degree Requirement**  
Another donut: 31K postings don't mention a degree, 51K do. For this role, most employers do mention degree requirements — but a significant portion do not, which opens a door for people without formal credentials.

**Jobs Globally**  
A map visual showing where Data Analyst roles are concentrated globally. The United States dominates, with a tooltip showing 21,490 jobs in the US alone at a median salary of $94,500. Other markets are visible but significantly smaller.

**Most Popular Platforms**  
A horizontal bar chart ranking job platforms by posting volume. LinkedIn leads clearly, followed by BeBee, Indeed, and others.

**Types of Jobs**  
A treemap showing the distribution of employment types. Full-time is overwhelmingly the most common — it fills most of the visual space. Contract, part-time, and internship roles exist but are a small fraction.

**Navigation**  
A back arrow in the top-left returns the user to the main dashboard, preserving the filter context they came from.

---

## Chapter 4 — Design Decisions

Every visual choice in this report was made for a reason.

**Why a table instead of a bar chart for job titles?**  
The table allows salary and trend data to live side by side. A bar chart would show one metric at a time. The table shows four. For job comparison, breadth matters more than visual impact.

**Why a scatter plot for salary comparison?**  
Because the question isn't "what is the salary" — it's "how do yearly and hourly compensation relate to each other." A scatter plot is the only visual that can answer a relationship question.

**Why a gauge for the drill-through salary?**  
Gauges show where a value sits within a range. The average alone means little without context. The gauge immediately communicates that $93K is near the low end of a very wide range — which a single number never could.

**Why a landing page?**  
Because first impressions matter. A dashboard that opens directly on charts asks the user to orient themselves. A landing page orients them first.

---

## Chapter 5 — What This Project Taught Me

This was my first Power BI report. The skills I practiced here will carry into every report I build after it.

**Technical skills practiced:**

- Building a Power BI data model from an Excel source
- Writing DAX measures — including a custom star rating measure
- Using Power Query for data cleaning and transformation
- Designing slicers and cross-filtering interactions
- Implementing drill-through navigation between pages
- Choosing the right visual type for each business question
- Designing a landing/home page in Power BI
- Applying consistent visual hierarchy and layout

**Thinking skills practiced:**

- Starting from the audience and working toward the visuals — not the other way around
- Framing data as answers to specific business questions
- Using visual composition to guide the reader's eye
- Treating the report as a story, not a collection of charts

---

## What Comes Next

This is Project #01.

The next Power BI projects will go deeper — more advanced DAX, more complex data models, stronger business context, and tighter visual design.

The goal is not to build many reports. The goal is to build better ones.

---

## Tools Used

| Tool | Role |
|---|---|
| **Power BI Desktop** | Report design and publishing |
| **DAX** | Custom measures and calculations |
| **Power Query** | Data preparation and transformation |
| **Excel** | Source data |

---

## Connect

**Portfolio:** https://abdodatanerd.figma.site/  
**LinkedIn:** https://www.linkedin.com/in/abdulrahman-m-2003march  
**GitHub:** https://github.com/abdulrahman0328

---

*Abdulrahman Muhammad — Data Analyst | Excel · Power BI · SQL*  
*Turning Financial Data into Business Insights*
