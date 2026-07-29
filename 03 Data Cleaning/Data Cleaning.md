# Data Cleaning Process

## Overview

Before performing any analysis, the dataset was cleaned and transformed to improve data quality, ensure consistency, and prepare it for visualization in Power BI.

The objective was to create an analysis-ready dataset that accurately reflects investor behavior and supports reliable business insights.

---

# Step 1: Data Inspection

The dataset was first profiled to understand its overall structure and identify potential data quality issues.

The following checks were performed:

- Reviewed the number of rows and columns
- Verified data types for each field
- Identified missing values
- Checked for duplicate records
- Reviewed unique values in categorical columns
- Validated Age values
- Checked for blank or inconsistent text entries

This initial assessment provided the basis for the cleaning activities that followed.

---

# Step 2: Handling Missing Values

Missing values were reviewed across both numeric and text fields.

## Numeric Columns

Missing numeric values were replaced using the project requirements.

Examples include:

- **Age** → Replaced with the column average (where applicable)
- **Investment Amount** (if available) → Replaced with the column average
- Other numeric fields → Replaced with the average value or 0 where specified

---

## Text Columns

Blank text values were standardized by replacing them with:

```text
Not Specified
```

This ensured consistency and prevented blank categories from appearing in visualizations.

---

# Step 3: Standardizing Text Values

Categorical values were standardized to eliminate inconsistencies caused by different spellings or capitalization.

Examples include:

| Before | After |
|---------|-------|
| male | Male |
| MALE | Male |
| female | Female |
| Government bond | Government Bonds |
| Gov Bonds | Government Bonds |

This step ensured that similar responses were grouped correctly during analysis.

---

# Step 4: Removing Duplicate Records

The dataset was checked for duplicate rows.

Exact duplicate records were removed to ensure that each respondent was represented only once in the analysis.

---

# Step 5: Renaming Columns

Column names were standardized to improve readability and consistency.

Examples include:

| Original | Updated |
|----------|---------|
| gender | Gender |
| Mutualfund | Mutual Funds |
| GovBond | Government Bonds |

Clear and descriptive column names improve model readability and make report development easier.

---

# Step 6: Creating Age Groups

To support demographic analysis, respondents were grouped into three business-defined age categories.

| Age Range | Age Group |
|-----------|-----------|
| 21–25 | Early Adulthood |
| 26–30 | Established Adulthood |
| 31–35 | Experienced Adulthood |

### Power BI (DAX)

```DAX
Age Group =
SWITCH(
    TRUE(),
    'Data'[Age] <= 25, "Early Adulthood",
    'Data'[Age] <= 30, "Established Adulthood",
    "Experienced Adulthood"
)
```

---

# Data Quality Outcome

After completing the cleaning process, the dataset was:

- Free from duplicate records
- Consistent across categorical fields
- Standardized for reporting
- Prepared for demographic segmentation
- Ready for Power BI visualization and KPI development

---

# Impact on Analysis

Cleaning and transforming the dataset ensured that:

- Investment preferences were accurately grouped.
- Age-based analysis was consistent.
- Visualizations reflected reliable counts and categories.
- KPIs were calculated using standardized and validated data.

The resulting cleaned dataset served as the foundation for all business insights, dashboard visualizations, and executive recommendations presented in this project.
````
