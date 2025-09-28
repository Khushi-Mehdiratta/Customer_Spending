# Customer_Spending

**Consumer Spending Data Cleaning Documentation**
**Dataset:** Percent Change in Consumer Spending (data.gov)
**Goal:** Prepare dataset for Tableau dashboard creation
**Date:** September 28, 2025

---

### Initial Issues

* Wide format: Each spending category in separate columns (C–Q).
* Truncated headers: “All merch”, “Accommo”, etc.
* FIPS codes only: States represented as numbers.
* Not analysis-ready for Tableau (no flexible filtering or grouping).

---

### Transformation Process

**1. Table Creation (Excel)**

* Converted raw data into Excel Table (Ctrl+T).
* Enabled structured referencing and Power Query functionality.

**2. Unpivot Columns (Power Query)**

* Unpivoted columns C–Q → created “Spending_Category” and “Percent_Change”.
* Converted dataset to long format (essential for Tableau filtering & analysis).

**3. Column Standardization**

* Renamed columns for clarity:

  * “Attribute” → “Spending_Category”
  * “Value” → “Percent_Change”
* Added **State_Name** column.

**4. Data Enrichment**

* Mapped FIPS codes to state names (e.g., 9 → Connecticut).
* Enabled geographic visualizations in Tableau.

---

### Final Data Structure

| State_FIPS | State_Name  | Date    | Spending_Category | Percent_Change |
| ---------- | ----------- | ------- | ----------------- | -------------- |
| 9          | Connecticut | 1/13/20 | All Merchant      | -2.3           |

---

### Quality Improvements

* ✅ Long format, analysis-ready
* ✅ Proper dimensions: State, Date, Category
* ✅ Clean numeric measure column
* ✅ Consistent date formatting
* ✅ Geographic fields prepared for mapping

---

### Dashboard Readiness

* **Filtering:** State, date, category
* **Visualization:** Time series, category comparisons, geographic maps
* **Performance:** Optimized structure, reduced complexity, scalable

---

### Optional Enhancements

* Simplify category names for readability (e.g., “Accommodation & Food”).
* Add regional groupings, per-capita metrics, and seasonal adjustments.

---

### Lessons Learned

* Data structure matters more than visuals.
* Power Query was critical for efficient transformation.
* Validation at each step ensured integrity.
* Documentation maintains reproducibility.

---

**Output:** `Consumer_Spending_Clean.xlsx` (validated, Tableau-ready, long format)

Next step, 
# Consumer Spending Dashboard

## Overview

After preparing and cleaning the dataset in Excel, I shifted to Tableau to build **interactive dashboards** and extract insights. To make the analysis more engaging, I framed it around a clear narrative:

**Data Story:** *The COVID-19 Consumer Spending Recovery*

---

## The Narrative Arc

**🎯 Main Question:** How did consumer spending patterns change during COVID-19, and which states/categories recovered fastest?

### Chapter 1: The Initial Impact (Jan–Apr 2020)

* Massive drops across all categories.
* **Key insight:** Arts/Entertainment vs. Grocery had contrasting impacts.
* **Geographic angle:** Urban states (NY, MA) suffered more.

### Chapter 2: The Recovery Pattern (2020–Present)

* Different recovery speeds by category.
* **Key insight:** Essential vs. non-essential spending trends.
* **Time angle:** When did states return to baseline (0% change)?

### Chapter 3: The New Normal (Recent Trends)

* Some categories rose above pre-COVID levels.
* **Key insight:** Permanent behavior changes vs. temporary shocks.
* **State angle:** Which states show strongest consumer confidence?

### Chapter 4: Category Winners & Losers

* Certain sectors never fully recovered, others boomed.
* **Key insight:** Online retail growth vs. entertainment decline.
* **Future angle:** Implications for businesses post-COVID.

---

## Dashboard Structure

**Page 1: Executive Overview**

* KPIs: Current vs. pre-COVID spending
* US map: State-level recovery status
* Category recovery timeline

**Page 2: Geographic Deep Dive**

* State comparison charts
* Regional/urban vs. rural patterns

**Page 3: Category Analysis**

* Winners vs. losers ranking
* Essential vs. non-essential spending trends
* Seasonal patterns

**Page 4: Time Evolution**

* Monthly spending trends
* Recovery milestone timeline
* Volatility analysis


