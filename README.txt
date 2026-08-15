# Layoffs Data Cleaning & EDA (MySQL)

Cleaning and analysis of a global tech layoffs dataset using MySQL.

## Tools
MySQL

## Structure
```
├── raw_data/layoffs.csv
├── cleaned_data/layoffs_cleaned.csv
├── sql/
│   ├── 1_data_cleaning.sql
│   └── 2_eda.sql
├── outputs/
│   ├── top5_by_year.csv
│   └── yearly_rolling_total.csv
└── README.md
```

## 1. Data Cleaning
- Removed duplicates via `ROW_NUMBER()`
- Standardized `company`, `industry`, `country` fields
- Converted `date` to proper `DATE` type
- Fixed nulls/blanks, backfilled missing `industry` by company match
- Dropped rows with no layoff data at all

## 2. EDA
- Largest single layoff events & 100%-shutdown companies
- Total layoffs by company
- Layoffs by year, and monthly rolling total (CTE + window function)
- Top 5 companies laid off per year (`DENSE_RANK()`)

## Files
- `sql/1_data_cleaning.sql` — cleaning query
- `sql/2_eda.sql` — EDA query
- `outputs/` — exported CSVs of key results