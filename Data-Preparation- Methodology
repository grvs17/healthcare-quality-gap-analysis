# 🏥 CMS Healthcare Quality Gap Analysis 
**Data Preparation Methodology**  
**Dataset**: [CMS Hospital Readmissions and Deaths (Kaggle)](https://www.kaggle.com/datasets)  
**Tooling**: Excel, Tableau (simulated in SQL for clarity)  
**Author**: Giselle Rosario Veracruz  

---

## 📦 Dataset Overview

This dataset provides readmission rates and related outcomes for hospitals across the United States, as published by the Centers for Medicare & Medicaid Services (CMS). The goal of this project was to build a clean and analysis-ready version of the data to power a Tableau dashboard exploring:

- Readmission performance relative to national averages  
- Geographic disparities in healthcare outcomes  
- Indicators of systemic inefficiencies and equity gaps  

---

## 🧹 Data Cleaning & Transformation Steps

All steps below were performed in Excel, but are documented in SQL-style syntax for transparency and reproducibility.

---

### ✅ Step 1: Initial Load

```sql
SELECT * 
FROM raw_hospital_data;
```

---

### ✅ Step 2: Remove Unnecessary Columns

Columns dropped for clarity, performance, and analytical focus:

```sql
ALTER TABLE raw_hospital_data
DROP COLUMN 
  [Address],
  [Phone Number],
  [Hospital Ownership],
  [Emergency Services],
  [Hospital Type],
  [County Name],
  [Hospital overall rating],
  [Location],
  [Provider ID 2],
  [Measure Score Footnote],
  [Measure Code],
  [Hospital Referral Region],
  [State FIPS Code],
  [Provider Key],
  [Date Footnote],
  [Footnote 1],
  [Footnote 2],
  [Footnote 3],
  [Location Geo Point];
```

> These fields were either duplicative, sparse, or not required for the comparative analysis.

---

### ✅ Step 3: Remove Non-Reportable Records

To ensure only valid comparative records were analyzed:

```sql
DELETE FROM cleaned_hospital_data
WHERE [Score] IS NULL
   OR [Compared to National] = 'Not Available';
```

---

### ✅ Step 4: Normalize Performance Labels

Simplified verbose text values into clear, categorical indicators:

```sql
UPDATE cleaned_hospital_data
SET [Compared to National] = 
  CASE 
    WHEN [Compared to National] = 'Better than the National Rate' THEN 'Above'
    WHEN [Compared to National] = 'Worse than the National Rate' THEN 'Below'
    WHEN [Compared to National] = 'Same as the National Rate' THEN 'Same'
    ELSE [Compared to National]
  END;
```

---

### ✅ Step 5: Create a `Performance Category` Field

Added a new field to support filtering and color encoding in Tableau:

```sql
ALTER TABLE cleaned_hospital_data
ADD [Performance Category] AS (
  CASE 
    WHEN [Compared to National] = 'Above' THEN 'Above'
    WHEN [Compared to National] = 'Below' THEN 'Below'
    WHEN [Compared to National] = 'Same' THEN 'Same'
    ELSE 'Insignificant Case Load'
  END
);
```

---

## 📊 Outcome

The cleaned and transformed dataset was used to:

- Create a Tableau dashboard visualizing hospital performance across states  
- Filter by performance category, condition, and geography  
- Highlight potential equity gaps and regional inefficiencies in care delivery  

---









