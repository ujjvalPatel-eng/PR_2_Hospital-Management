# Hospital Patient Analytics Dashboard

## 📊 Project Overview

**Project File:** `PR_2_Hospital.pbix`

This Power BI project is a **Hospital Patient Analytics Dashboard**
built using a healthcare admissions dataset. The report analyzes patient
volume, medical conditions, hospital revenue, insurance coverage, length
of stay, admission trends, and billing performance.

The dashboard is designed to demonstrate practical **Power BI, Power
Query, data transformation, filtering, aggregation, and visualization**
techniques.

------------------------------------------------------------------------

## 🎯 Project Objectives

The main objectives of this project are to:

-   Analyze the total number of hospital patients.
-   Understand patient distribution by medical condition.
-   Compare hospital billing revenue.
-   Analyze monthly admission trends.
-   Examine patients by insurance provider.
-   Analyze average and total billing amounts.
-   Analyze average length of hospital stay.
-   Categorize patients based on age, length of stay, billing, and risk.
-   Associate medical conditions with relevant hospital departments.
-   Provide detailed patient-level information.
-   Analyze billing by department, billing tier, and insurance provider.
-   Provide interactive filtering through slicers.

------------------------------------------------------------------------

## 🗂️ Report Pages

The PBIX file contains **three main report pages**.

### 1. Hospital Patient Analytics Dashboard

The main dashboard provides a high-level overview of hospital
operations.

Key metrics and visuals include:

-   Total Patients
-   Total Revenue
-   Average Billing
-   Average Length of Stay
-   Patient count by Medical Condition
-   Top 10 Hospitals by Total Billing Revenue
-   Monthly Patient Admissions
-   Patient distribution by Insurance Provider
-   Admission Type filter
-   Medical Condition filter
-   Admission Year filter

This page is intended to provide a quick management-level overview of
the healthcare dataset.

------------------------------------------------------------------------

### 2. Patient Detail Table

This page provides detailed patient-level information.

The table includes fields such as:

-   Patient Name
-   Age
-   Age Category
-   Gender
-   Medical Condition
-   Department
-   Admission Type
-   Stay Category
-   Length of Stay
-   Billing Amount
-   Test Results
-   Other patient-related attributes

Interactive slicers are available for filtering the detailed patient
data.

------------------------------------------------------------------------

### 3. Billing Analysis

This page focuses on financial and billing analysis.

It includes:

-   Billing Tier analysis
-   Department-level billing analysis
-   Insurance Provider vs. Medical Condition billing matrix
-   Admission Year filtering

This page can be used to identify departments, conditions, and insurance
categories associated with higher billing amounts.

------------------------------------------------------------------------

## 🔄 Power Query / Data Preparation

The project contains several Power Query queries used for transformation
and analysis.

### Main Queries

  -----------------------------------------------------------------------
  Query                               Purpose
  ----------------------------------- -----------------------------------
  `healthcare_dataset`                Original healthcare dataset

  `Condition_Dept_Lookup`             Lookup table mapping medical
                                      conditions to departments

  `Admissions_Pre2022`                Admissions before 2022

  `Admissions_2022Plus`               Admissions from 2022 onward

  `Admissions_Full`                   Combined admissions dataset

  `Condition_Summary`                 Summary by medical condition

  `Hospital_Summary`                  Summary by hospital

  `Insurance_Summary`                 Summary by insurance provider

  `Condition_Pivot`                   Pivoted admission-type analysis

  `Monthly_Admissions`                Monthly admission analysis
  -----------------------------------------------------------------------

------------------------------------------------------------------------

## 🏥 Department Lookup

A lookup table named `Condition_Dept_Lookup` is used to assign a
hospital department to each medical condition.

  Medical Condition   Department
  ------------------- ---------------
  Cancer              Oncology
  Diabetes            Endocrinology
  Hypertension        Cardiology
  Obesity             Bariatrics
  Asthma              Pulmonology
  Arthritis           Rheumatology

The lookup is merged with the main admissions data using:

**Medical Condition → Medical_Condition**

A **Left Outer Join** is used so that all patient records from the main
dataset are retained.

------------------------------------------------------------------------

## 🔀 Data Transformation Techniques

The project demonstrates several important Power Query techniques.

### Group By

Summary tables are created using Group By operations.

#### Condition Summary

-   Patient Count
-   Average Billing
-   Average Length of Stay

#### Hospital Summary

-   Total Patients
-   Total Revenue
-   Average Billing

#### Insurance Summary

-   Covered Patients
-   Total Claims
-   Average Claim

------------------------------------------------------------------------

### Merge Queries

`Condition_Dept_Lookup` is merged with the admissions data to add a
`Department` column.

------------------------------------------------------------------------

### Pivot

Admission Type data can be transformed into separate columns such as:

-   Elective
-   Emergency
-   Urgent

This allows admission patterns to be compared across medical conditions.

------------------------------------------------------------------------

### Unpivot

The pivoted admission-type columns can be converted back into a
tall/normalized structure using **Unpivot Selected Columns**.

------------------------------------------------------------------------

### Append Queries

Two admission datasets are combined:

-   `Admissions_Pre2022`
-   `Admissions_2022Plus`

The resulting query is:

`Admissions_Full`

This demonstrates how datasets with the same structure can be appended
into one complete table.

------------------------------------------------------------------------

## 📋 Important Data Fields

The report uses fields including:

-   `Patient_ID`
-   `Name`
-   `Age`
-   `Age_Category`
-   `Gender`
-   `Medical Condition`
-   `Department`
-   `Hospital`
-   `Insurance Provider`
-   `Admission Type`
-   `Admission_Year`
-   `Admisson_Month_Num`
-   `Length_of_Stay_Days`
-   `Stay_Category`
-   `Billing_Amount_Fixed`
-   `Billing_Amount_Rounded`
-   `Billing_Tier`
-   `Risk_Flag`
-   `Test Results`

> **Note:** Some column names in the PBIX contain spaces or leading
> spaces. When creating DAX expressions, use the exact column name shown
> in the Fields/Data pane.

------------------------------------------------------------------------

## 📈 Dashboard KPIs

The main dashboard contains KPI-style cards for:

### Total Patient

Counts patient records using `Patient_ID`.

### Total Revenue

Calculates total billing using:

`Billing_Amount_Fixed`

### Average Billing

Calculates the average billing amount.

### Average Length of Stay

Calculates the average number of hospital stay days.

------------------------------------------------------------------------

## 📊 Main Visualizations

### Patient Count by Medical Condition

A bar chart compares patient volume across medical conditions.

### Top 10 Hospitals by Revenue

A bar chart displays the top hospitals based on total billing revenue,
sorted in descending order.

### Monthly Admissions

A line chart displays patient admission trends by month.

### Insurance Provider Distribution

A donut chart shows the distribution of insured patients by insurance
provider.

### Billing Analysis

A column chart compares billing amounts by billing tier and department.

### Billing Matrix

A matrix compares billing amounts across:

-   Medical Condition
-   Insurance Provider

------------------------------------------------------------------------

## 🎛️ Filters and Slicers

The report uses interactive slicers for fields such as:

-   Admission Type
-   Medical Condition
-   Admission Year

These filters allow users to interactively explore different sections of
the hospital dataset.

------------------------------------------------------------------------

## 🧮 Data Analysis Concepts Demonstrated

This project demonstrates the following Power BI concepts:

-   Power Query
-   Data cleaning
-   Data type transformation
-   Group By
-   Merge Queries
-   Append Queries
-   Pivot
-   Unpivot
-   Reference Queries
-   Lookup tables
-   Filtering
-   Parameters
-   DAX
-   KPI cards
-   Bar charts
-   Column charts
-   Line charts
-   Donut charts
-   Tables
-   Matrix visuals
-   Slicers
-   Conditional categorization
-   Interactive dashboard design

------------------------------------------------------------------------

## ⚙️ Parameters

The project workflow includes parameter-based filtering concepts such
as:

### MinAge

A numeric parameter used to control the minimum patient age included in
the analysis.

Example:

``` text
MinAge = 18
```

Changing the value to:

``` text
MinAge = 65
```

can be used to focus the analysis on senior patients.

### AdmissionType

A text parameter can be used to control admission type filtering.

Possible values include:

-   Elective
-   Emergency
-   Urgent
-   All

------------------------------------------------------------------------

## 🔄 Data Refresh

To refresh the report:

1.  Open `PR_2_Hospital.pbix` in Power BI Desktop.
2.  Select **Home → Refresh**.
3.  If Power Query changes are required, select **Transform data**.
4.  Review the queries and transformations.
5.  Select **Close & Apply**.
6.  Refresh the report.

------------------------------------------------------------------------

## 📁 Data Source

The main project workflow uses a healthcare dataset and supporting
lookup data.

Typical source files include:

``` text
healthcare_dataset.csv
Condition_Dept_Lookup.csv
```

If the PBIX is moved to another computer, the CSV file paths may need to
be updated.

Use:

**File → Options and settings → Data source settings**

Then select the relevant source and choose **Change Source** when
required.

------------------------------------------------------------------------

## 🚀 How to Use the Dashboard

1.  Open `PR_2_Hospital.pbix` using **Power BI Desktop**.
2.  Wait for the model to load.
3.  Refresh the data if the source files have changed.
4.  Start from the **Hospital Patient Analytics Dashboard** page.
5.  Use the slicers to filter the analysis.
6.  Navigate to **Patient Detail Table** for patient-level information.
7.  Navigate to **Billing Analysis** for financial analysis.
8.  Hover over charts to view additional information.
9.  Use selections in charts and slicers to cross-filter the report.

------------------------------------------------------------------------

## 💡 Key Business Questions

The dashboard can help answer questions such as:

-   How many patients are represented in the dataset?
-   Which medical conditions have the highest number of patients?
-   Which hospitals generate the highest billing revenue?
-   How do patient admissions change over time?
-   Which insurance providers cover the most patients?
-   What is the average billing amount?
-   What is the average patient length of stay?
-   Which departments generate higher billing?
-   How does billing vary by medical condition and insurance provider?
-   How does admission type affect patient volume?

------------------------------------------------------------------------

## 🛠️ Requirements

To open and modify this project, use:

-   **Microsoft Power BI Desktop**
-   Access to the source healthcare dataset, if a refresh is required
-   Any supporting lookup files used by the Power Query model

------------------------------------------------------------------------

## 📌 Project Structure

``` text
PR_2_Hospital.pbix
│
├── Hospital Patient Analytics Dashboard
│   ├── KPI Cards
│   ├── Patient Condition Analysis
│   ├── Hospital Revenue Analysis
│   ├── Monthly Admission Trend
│   ├── Insurance Provider Analysis
│   └── Interactive Slicers
│
├── Patient Detail Table
│   ├── Patient Information
│   ├── Medical Information
│   ├── Admission Information
│   └── Billing Information
│
└── Billing Analysis
    ├── Billing Tier Analysis
    ├── Department Analysis
    ├── Insurance Provider Matrix
    └── Admission Year Filter
```

------------------------------------------------------------------------

## 👤 Project Type

**Power BI Healthcare Analytics Project**

This project is suitable for demonstrating practical knowledge of:

-   Data Analytics
-   Business Intelligence
-   Power BI
-   Power Query
-   DAX
-   Healthcare Data Analysis
-   Dashboard Development
-   Data Visualization

------------------------------------------------------------------------

## 📄 License

This project is intended for **learning, practice, and portfolio
purposes** unless a separate license or data-use agreement applies to
the underlying dataset.
