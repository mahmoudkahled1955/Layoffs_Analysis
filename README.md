# 📉 Layoffs Analysis

![MySQL](https://img.shields.io/badge/MySQL-005C84?style=for-the-badge&logo=mysql&logoColor=white)
![Data Analysis](https://img.shields.io/badge/SQL-Data_Cleaning_&_EDA-blue?style=for-the-badge)

## 📋 Project Overview
This project involves a deep dive into a dataset containing layoff records from over 2,000 companies. The goal was to take raw, messy data and transform it into a clean, structured format, followed by an Exploratory Data Analysis (EDA) to uncover trends regarding which industries, countries, and specific companies were hit the hardest over time.

## ⚙️ Technical Workflow & SQL Techniques

### Phase 1: Data Cleaning (Staging & Transformation)
* **Deduplication:** Created a staging table and utilized `ROW_NUMBER()` over partitioned data to identify and remove duplicate rows safely.
* **Data Standardization:** * Used `TRIM()` to remove whitespace from text fields.
  * Standardized inconsistent industry names (e.g., grouping various 'Crypto' entries).
  * Cleaned country names (removing trailing periods).
  * Converted string date fields into proper `DATE` formats using `STR_TO_DATE`.
* **Handling Missing Data:** * Implemented **Self-Joins** to intelligently populate `NULL` industry values based on other records from the same company.
  * Safely removed rows where both `total_laid_off` and `percentage_laid_off` were empty, as they provided no analytical value.

### Phase 2: Exploratory Data Analysis (EDA)
* **High-Level Aggregations:** Calculated total layoffs by company, industry, country, and year.
* **Time-Series Analysis:** Generated a rolling total of layoffs month-by-month using **CTEs** and the `SUM() OVER()` window function.
* **Advanced Ranking:** Identified the Top 5 companies with the most layoffs for each specific year.

---

## 🚀 Conclusion
This project demonstrates end-to-end data processing in MySQL, moving from unstructured, dirty data to clean, analytically ready tables, and finally extracting complex business insights using advanced SQL querying.
