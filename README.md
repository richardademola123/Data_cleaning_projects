# Concert Revenue Data Cleaning (Excel) from kaggle 

## Project Overview
This project demonstrates how I cleaned a **messy, real-world dataset** of concert revenues (sourced from [Kaggle](https://www.kaggle.com/datasets/amruthayenikonda/dirty-dataset-to-practice-data-cleaning)).  
The dataset contained:
- Footnote markers (`†`, `‡`, `]`).
- Text-formatted currency (`$780,000,000.00`).
- Inconsistent values (`BLANKS` in numeric columns).
- Empty/duplicate columns.

The goal was to **transform messy raw data into analysis-ready form** using **Excel functions**.

---

## Tools & Functions
- **Excel** (data cleaning & formatting)
- Functions used:
  - `VALUE()`, `SUBSTITUTE()` → convert currency text to numbers
  - `TRIM()`, `CLEAN()` → remove spaces & hidden characters
  - `IF()` → handle “Unknown” values
  - `SUBSTITUTE()` → remove trailing symbols (`†`, `‡`, `]`, `a]`)
  

---

## Cleaning Steps

1. **Converted currency text → numbers**
   - `"$780,000,000.00"` → `780000000`
   - Formula:  
     ```excel
     =VALUE(SUBSTITUTE(SUBSTITUTE(A2,"$",""),",",""))
     ```

2. **Removed footnote symbols**
   - Cleaned `†`, `‡`, `]`, `a]` using `Find & Replace` and `SUBSTITUTE()`.

3. **Standardized year ranges**
   - Changed `2023–2024` (en dash) → `2023-2024` (hyphen).

4. **Replaced inconsistent values**
   - `"BLANKS"` → `"NULL"`.

6. **Trimmed spaces & cleaned characters**
   - Used `=TRIM(CLEAN(A2))` to ensure consistent text.

---

## Before vs After
| Issue | Before | After |
|-------|--------|-------|
| Currency | `$780,000,000.00` | `$780,000,000` |
| Trailing symbols | `Sticky & Sweet Tour ‡4]a]` | `Sticky & Sweet Tour` |
| Year formatting | `2023–2024` | `2023-2024` |
| Missing values | `BLANKS` | `NULL` |

---


## Results
- Dataset is now **analysis-ready**:
  - Can be used for PivotTables (e.g., average gross per artist/year).
  - Suitable for SQL database import.
  - Ready for dashboards and reporting.

---

