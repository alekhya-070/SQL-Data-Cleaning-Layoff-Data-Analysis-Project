#Analysis of Layoffs During the COVID-19 Pandemic Using SQL

The COVID-19 pandemic caused a global economic disruption, leading to widespread layoffs across various industries and regions. This project focuses on analyzing layoff data during this challenging period to uncover trends, patterns, and insights. The analysis provides an understanding of how industries, countries, and companies were impacted by layoffs during the pandemic, helping stakeholders make informed decisions for the future.
The dataset, sourced from Kaggle Layoffs 2022, tracks layoffs across industries, companies, and locations.

Objectives:
Ensure the dataset is clean, standardized, and free of errors or inconsistencies.
Retain the integrity of the raw data by creating a staging table for cleaning.
Prepare the cleaned dataset for further analysis or visualization tasks.

Steps Performed:
1. Data Staging
Created a staging table (layoffs_staging) as a copy of the original dataset to preserve the raw data.
Inserted the raw data into the staging table for cleaning.
2. Removing Duplicates
Identified duplicates using the ROW_NUMBER() function with a PARTITION BY clause.
Validated duplicate entries manually to ensure legitimate entries were not removed.
Deleted duplicate rows where the row number exceeded 1.
3. Standardizing Data
Ensured uniformity in categorical columns such as industry and country.
Consolidated variations (e.g., "Crypto Currency" → "Crypto").
Trimmed unnecessary characters (e.g., periods in "United States.").
Standardized the date column by converting text strings to proper DATE format using STR_TO_DATE() and altered the column type accordingly.
4. Handling Null Values
Investigated null values in key columns (industry, total_laid_off, etc.).
Updated missing values in the industry column based on existing data for the same company.
Retained meaningful nulls in numeric fields to assist in accurate calculations during analysis.
5. Removing Useless Data
Removed rows with insufficient data (both total_laid_off and percentage_laid_off as NULL).
Dropped helper columns (row_num) created during the cleaning process.

Results:
The cleaned dataset (layoffs_staging2) is now ready for exploratory data analysis (EDA) and further transformations. The dataset ensures:
No duplicate entries.
Standardized categorical and date fields.
Consistency in numeric fields and missing values retained where appropriate.

Key Features
SQL Techniques Used:
Window functions (ROW_NUMBER)
Common Table Expressions (CTEs)
Joins and updates for cross-row validation
Data type conversions and column alterations

Dataset Insights:
Tracks layoffs across companies, industries, and countries.
Provides quantitative metrics (total_laid_off, funds_raised_millions) for analysis.

Tools
SQL Database: MySQL
Dataset Source: Kaggle

Next Steps
Perform exploratory data analysis to identify patterns and trends.
Use the cleaned data to build visualizations or dashboards for insightful reporting.
Explore predictive modeling opportunities based on layoff trends.

EDA:
This project involves exploratory data analysis (EDA) of global layoff data stored in a SQL database. It identifies trends, patterns, and insights, such as the largest layoffs, affected industries, locations, and temporal patterns. The goal is to derive actionable insights and support strategic decision-making.

Objectives
Perform exploratory data analysis (EDA) to understand the dataset.
Identify patterns and trends in layoffs by company, location, and industry.
Calculate metrics like rolling totals and rankings for better insights.
Summarize the impact of layoffs across time periods.

Dataset Description
The dataset (layoffs_staging2) contains information about layoffs, including:
company: Name of the company.
total_laid_off: Number of employees laid off.
percentage_laid_off: Percentage of the workforce laid off.
location: Location of the layoffs.
country: Country of the company.
date: Date of the layoff event.
industry: Industry of the company.
funds_raised_millions: Funds raised by the company in millions.
stage: Company's stage (e.g., startup, established).

Steps
1. Explore the Dataset
Use basic queries to examine the data, check for null values, and understand its structure.
View all data.
Identify the maximum layoffs in a single event.
Check the range of percentage layoffs.
3. Analyze Companies with 100% Layoffs
Find companies where the entire workforce was laid off and explore patterns like funds raised or industry type.
4. Aggregated Insights
Identify companies with the largest layoffs, both for single events and over time.
Analyze layoffs by location, country, and industry.
5. Temporal Analysis
Examine layoffs by year.
Calculate rolling totals of layoffs by month.
6. Advanced Queries
Use WITH and window functions for insights like top companies by layoffs per year and rolling totals.

Outcome
Uncovered companies and locations most affected by layoffs.
Derived insights into temporal trends like yearly or monthly layoffs.
Identified industries and company stages prone to layoffs.
Built foundational SQL skills for EDA and advanced analysis using window functions.

