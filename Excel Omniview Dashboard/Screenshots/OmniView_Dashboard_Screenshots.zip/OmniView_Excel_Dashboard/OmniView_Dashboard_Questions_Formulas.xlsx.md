OmniView Dashboard – Questions & Formulas
1) Highest Average Employment Rate (by Region)

Question: Which region shows the highest average Employment Rate %?
Formula:

=AVERAGEIFS(OmniView[Employment_Rate_%], OmniView[Region], "Asia")

2) Highest Average Economic Stability (by Country)

Question: Which country has the highest average Economic Stability Score?
Formula:

=AVERAGEIFS(OmniView[Economic_Stability_Score], OmniView[Country], "France")

3) Top 5 Countries with Highest AI Adoption

Question: Which 5 countries have the highest AI_Adoption_Level?
Formula:

=LARGE(OmniView[AI_Adoption_Level], {1,2,3,4,5})

4) Country with Highest Health Score

Question: Which country has the highest Health_Score?
Formulas:

=MAX(OmniView[Health_Score])
=INDEX(OmniView[Country], MATCH(MAX(OmniView[Health_Score]), OmniView[Health_Score], 0))

5) Total Renewable Energy % (by Region)

Question: What is the total Renewable_Energy_% for each region?
Formula:

=SUMIFS(OmniView[Renewable_Energy_%], OmniView[Region], "Europe")

6) Internet Usage Growth (1960s → 2020s)

Question: How has Internet_Usage_% changed from the 1960s to the 2020s?
Formula:

=AVERAGEIFS(OmniView[Internet_Usage_%], OmniView[Decade], "1990s")

7) Total Countries (KPI)

Question: How many unique countries are in the dataset?
Formulas (Excel 365 / non-365):

=COUNTA(UNIQUE(OmniView[Country]))
=SUMPRODUCT(1/COUNTIF(OmniView[Country], OmniView[Country]))

8) Average Income (overall / filtered)

Question: What is the average Avg_Income_USD?
Formulas:

=AVERAGE(OmniView[Avg_Income_USD])    /* overall */
=AVERAGEIFS(OmniView[Avg_Income_USD], OmniView[Region], "Asia")  /* by region */

9) Average Happiness Rating

Question: What is the average Happiness_Rating?
Formula:

=AVERAGE(OmniView[Happiness_Rating])

10) Average Income per Decade

Question: What is the average income for each decade?
Formula:

=AVERAGEIFS(OmniView[Avg_Income_USD], OmniView[Decade], "2000s")

11) Decades with Inflation Rate > 8%

Question: Which decades recorded Inflation_Rate_% > 8%?
Formula (Excel 365):

=UNIQUE(FILTER(OmniView[Decade], OmniView[Inflation_Rate_%] > 8))

12) Population Type: Highest → Lowest Communication Index

Question: Rank Population_Type by Communication_Index (highest to lowest).
Formula:

=AVERAGEIFS(OmniView[Communication_Index], OmniView[Population_Type], "Single")

13) Countries with Environmental Policy = "Yes" AND Economic Stability = "Excellent"

Question: Which countries meet both conditions?
Formula (Excel 365):

=FILTER(UNIQUE(OmniView[Country]), (OmniView[Environmental_Policy_Active] = "Yes") * (OmniView[Economic_Stability] = "Excellent"))

📌 Short Notes for Using Formulas (Highlighted)

Replace Table and Column Names – Use your own table name instead of OmniView and the correct column names.

Adjust Filter Values – Replace "Asia", "2000s", "Yes" with your actual categories or criteria.

PivotTables Setup –

Rows: Select the category (e.g., Decade, Region, Country)

Values: Select the field (e.g., Avg_Income_USD) and choose Average/Sum

Slicers: Add for interactive filtering.

KPI Cards – Use GETPIVOTDATA to fetch a single Pivot value for dashboards.

Dynamic Formulas – UNIQUE, FILTER, LARGE can show top items or filtered lists; adjust for your dataset.

Test & Verify – Always check formulas with a small sample of data before using them in your dashboard.