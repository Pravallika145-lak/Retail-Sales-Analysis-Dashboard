# Retail-Sales-Analysis-Dashboard
Key Objectives

Understand the influence of age and gender on purchasing behavior,
Identify sales patterns across time periods and seasons,
Determine popular product categories and pricing trends,
Analyze transaction sizes and their contribution to revenue,

Approach

Data Preparation:
Extracted fields from the date column (Year, Month, Day of Week).
Grouped customers into age brackets (e.g., 18-25, 26-35).
Added a Sales per Unit column to measure efficiency.

Key DAX Measures:
To facilitate dynamic and insightful analysis, the following DAX measures were created:

Total Sales:
Total Sales = SUMX('Sales Data','Sales Data'[Quantity] * 'Sales Data'[UnitPrice])

Total Quantity Sold:
Total Quantity Sold = SUM('Sales Data'[Quantity])

Average Sales per Transaction:
Average Sales per Transaction = DIVIDE([Total Sales], COUNTROWS('Sales Data')

Sales Contribution by Product Category:
Sales Contribution by Product Category = DIVIDE(
    CALCULATE([Total Sales], ALLEXCEPT('Sales Data','Sales Data'[ProductCategory])),
    CALCULATE([Total Sales]))

Sales by Age Group:
Sales by Age Group = CALCULATE(
    [Total Sales],
    ALLEXCEPT('Sales Data','Sales Data'[Age Bracket]))

Peak Month Sales:
Peak Month Sales = MAXX(
    SUMMARIZE(
        'Sales Data','Sales Data'[Month],
        "MonthlySales", [Total Sales]
    ),
    [MonthlySales])

Dashboard Construction in Power BI
The dashboard was organized into two distinct pages, each focusing on specific aspects of the analysis.

Page 1: Customer Insights & Time-Based Trends

Heading: Customer Behavior and Sales Over TimeKPIs:

KPIs:
Total Sales,
Total Quantity,
Average Sales per Transaction,

Stacked Column Chart:
Title: Purchasing Behavior by Age Group and Gender,
Purpose: Compare purchasing behaviors across age groups and genders.

Donut Chart:
Title: Gender Contribution to Sales,
Purpose: Highlight the percentage of total sales by gender.

Line Chart:
Title: Sales Trends Over Time,
Purpose: Identify sales patterns and peaks across months.

Table:
Title: Sales by Day of Week and Month,
Purpose: Explore which days and months see higher sales activity.

Slicers:
Age Group,
Product category
