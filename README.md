# Talent Acquisition Analytics Dashboard

## Project Overview

This project analyzes the recruitment process using Excel, SQL, and Power BI. The objective is to understand candidate progression through hiring stages, identify key rejection factors, evaluate recruitment strategies, and measure overall hiring effectiveness.

## Business Problem

Organizations receive large numbers of job applications but often struggle to identify why candidates drop out during the hiring process and which recruitment strategies generate the best hiring outcomes.

This project helps answer:

* Where do most candidates drop out?
* What are the major rejection reasons?
* Which recruitment strategy performs best?
* How effectively are high-performing candidates selected?

## Dashboard Preview

![Talent Acquisition Dashboard](Power%20BI/Dashboard.png)

## Data Cleaning & Preparation

Before analysis, the dataset was cleaned and prepared using Excel and SQL:

* Removed duplicate records
* Removed blank recruitment strategy records
* Handled missing values
* Standardized data formats
* Validated candidate status records
* Created hiring stage metrics
* Calculated selection KPIs

## Tools Used

* Excel – Data Cleaning & Preparation
* SQL – Data Analysis & KPI Calculation
* Power BI – Dashboard Development & Visualization

## Dataset

The dataset contains recruitment and hiring information for 1,498 candidates.

### Key Fields

* Candidate ID
* Gender
* Education Level
* Resume Score
* Technical Score
* Personality Score
* Recruitment Strategy
* Hiring Decision
* Final Status
* Drop Stage
* Drop Reason

## Dashboard Features

* Total Applicants KPI
* Candidates Selected KPI
* Average Resume Score KPI
* Selection Rate KPI
* Candidate Hiring Journey Funnel
* Recruitment Strategy Performance Analysis
* Candidate Rejection Reason Analysis
* High Performer Selection Analysis
* Interactive Filters (Slicers)
* Custom Tooltip Analysis

## Key KPIs

| KPI                  | Value  |
| -------------------- | ------ |
| Total Applicants     | 1,498  |
| Candidates Selected  | 520    |
| Average Resume Score | 58.6   |
| Selection Rate       | 34.69% |

## Key Business Insights

* More than half of candidates were eliminated during the screening stage.
* Low Resume Score was the leading rejection reason.
* Moderate Recruitment Strategy generated the highest number of successful hires.
* High-performing candidates accounted for the majority of selected candidates.
* Candidate quality significantly influenced final hiring decisions.

## Business Recommendations

* Improve resume screening criteria.
* Focus on attracting higher-quality applicants.
* Continue using Moderate Recruitment Strategy for better hiring outcomes.
* Strengthen technical assessment processes.
* Monitor candidate drop-off stages regularly.

## Project Workflow

1. Data Collection
2. Data Cleaning using Excel
3. Data Analysis using SQL
4. KPI Calculation
5. Power BI Dashboard Development
6. Insight Generation
7. Business Recommendations

## Repository Structure

```text
Talent-Acquisition-Analytics-Dashboard
│
├── README.md
│
├── Power BI
│   ├── Talent_Acquisition_Analytics_Dashboard.pbix
│   └── Dashboard_Screenshot.png
│
├── data
│   ├── recruitment_mydata.csv
│   └── Recruitment_Dataset.xlsx
│
└── sql
    └── SQL_Queries.sql
```

## Skills Demonstrated

* Excel
* SQL
* Power BI
* Data Cleaning
* Data Analysis
* Data Visualization
* Dashboard Design
* KPI Reporting
* Recruitment Analytics
* Business Analysis

## About

An end-to-end recruitment analytics project built using Excel, SQL, and Power BI to evaluate hiring performance, candidate progression, recruitment strategies, and selection effectiveness.
