# 🧹 SQL Data Cleaning: Layoffs Dataset

This project demonstrates **SQL data cleaning techniques** on a layoffs dataset.  
The goal is to clean, standardize, and prepare the data for further analysis.

---

## 📌 Steps Performed

### 1. Remove Duplicates
- Used `ROW_NUMBER()` with a `PARTITION BY` clause to identify duplicate records.
- Created a staging table (`layoffs_staging2`) to store cleaned data.
- Removed duplicate rows to ensure unique entries.

### 2. Standardize the Data
- Trimmed extra spaces from company names.
- Standardized industry names (e.g., merging variations of "Crypto").
- Fixed inconsistent country names (e.g., "United States." → "United States").
- Converted `date` column from text to `DATE` type.

### 3. Handle Null or Blank Values
- Replaced blank industries with `NULL`.
- Used self-join to fill missing industries when possible (based on company and location).
- Removed rows where both `total_laid_off` and `percentage_laid_off` were `NULL`.

### 4. Remove Unnecessary Columns
- Dropped helper column `row_num` after cleaning.

---

## 🛠️ Technologies Used
- **MySQL 8+** (InnoDB engine, utf8mb4 collation)
- SQL Window Functions (`ROW_NUMBER()`)
- Data standardization techniques

---

## 📂 Files
- `data_cleaning.sql` → Full SQL script for data cleaning
- `README.md` → Documentation

---

## 🚀 How to Run
1. Import the raw layoffs dataset into a MySQL database (table: `layoffs_staging`).
2. Run the queries step by step from `data_cleaning.sql`.
3. Final cleaned table will be in `layoffs_staging2`.

---

## 📊 Example Use Cases
- Prepare clean data for **exploratory data analysis (EDA)**.
- Build dashboards and reports on layoff trends.
- Train machine learning models on structured data.

---

## 📜 License
This project is open-source. You’re free to use and modify it.
