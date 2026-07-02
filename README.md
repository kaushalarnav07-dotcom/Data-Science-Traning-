# OPD Patient & Admissions Analysis Dashboard

An interactive Power BI dashboard analyzing outpatient (OPD) admissions, patient demographics, length of stay, and billing performance for a hospital, built as part of a Summer Training project in Power BI.

## Problem Statement

Hospital staff tracked OPD admissions, bed occupancy, and billing manually, with no single view tying patient volume, length of stay, and revenue together — so trends by condition and month took days to spot. This dashboard gives the OPD Manager and Hospital Administration team a live view of patient inflow, condition mix, and billing performance without compiling weekly Excel reports.

## Project Objectives

- Connect & clean the raw dataset using Power Query
- Build a star schema data model with correct relationships
- Create at least 5 meaningful DAX measures
- Design an interactive multi-page dashboard with 5+ visual types
- Publish the final report to Power BI Service

## Dataset

| | |
|---|---|
| **Source** | [Healthcare Dataset — Kaggle](https://www.kaggle.com/datasets/prasad22/healthcare-dataset) |
| **File Type** | CSV |
| **Rows** | 55,500 |
| **Columns** | 15 |

**Key columns used:**

| Column | Role in Dashboard |
|---|---|
| Name | Patient identifier for record-level detail |
| Date of Admission | Date dimension — monthly trend analysis |
| Medical Condition | Diagnosis grouping for slicers and bar chart |
| Billing Amount | Revenue — base for SUM and KPI measures |
| Room Number | Bed/room occupancy tracking |
| Admission Type | Elective / Urgent / Emergency slicer |

**Power Query cleaning steps:**
- Removed duplicate rows
- Fixed null values in Medication and Test Results
- Changed data types (Date, Number)
- Renamed columns for clarity
- Filtered out incomplete admission records
- Created `LOS_Days` and `Admission Month` calculated columns

## Dashboard Pages

### Page 1 — OPD Overview
![OPD Overview](screenshots/overview-page.png)

- KPI Cards — Total Patients, Avg LOS, Readmission %
- Bar Chart — Patients by Medical Condition
- Line Chart — Monthly Admission Trend
- Column Chart — Patients by Gender
- Slicers — Condition / Timeline / Admission Type

### Page 2 — Patient Details
![Patient Details](screenshots/patient-details-page.png)

- Patient Table — Name, Condition, Doctor, Hospital, LOS
- KPI — Billing Amount vs Target
- Pie Chart — Blood Group Distribution
- Page Navigator — switch between report pages

## Key Findings

1. Patient load is evenly spread across all six tracked conditions (9.2K–9.3K each), so no single diagnosis dominates OPD capacity planning.
2. Monthly admissions hold a steady 4,500–5,000 patient band with a visible peak in August, useful for staffing and bed-allocation forecasts.
3. Gender split is nearly identical (28K male vs 28K female), confirming the patient base is balanced across demographics.
4. Average length of stay is 15.51 days with a 67.66% readmission rate, signalling room to improve discharge planning and follow-up care.
5. Total billing of 5.43M far exceeds the per-patient target, and all eight blood groups stay within a tight 12.4%–12.6% band, showing balanced billing performance and a representative patient mix.

## Tech / Skills Used

- **Power Query** — data cleaning and transformation
- **Data Modeling** — star schema relationships
- **DAX** — measures including `Avg LOS` and `Readmission %`, built using `DATEDIFF` and `DIVIDE` over the cleaned admission/discharge dates
- **Power BI Service** — report publishing

## Future Scope

- Add a predictive readmission-risk model
- Build a cost-per-condition page using the Billing Amount and Insurance Provider fields

## Files in this Repo

| File | Description |
|---|---|
| `power_bi_project.pbix` | Power BI Desktop file — open with [Power BI Desktop](https://powerbi.microsoft.com/desktop/) |
| `OPD_Project_Presentation.pptx` | Project presentation slide deck |
| `screenshots/` | Dashboard page exports |

## Author

**Arnav Kaushal**
B.Tech — CSE, Chandigarh Group of Colleges, Jhanjeri
Guided by Mr. Rahul Dev Singh
