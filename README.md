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
