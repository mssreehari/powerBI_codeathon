# Sales Data Analysis using Power BI

## Project Overview
This project focuses on analyzing customer order and sales data using Microsoft Power BI. The objective is to clean the raw dataset, perform data analysis, create meaningful visualizations, and derive insights into regional order distribution, product performance, and profit trends.

## Dataset Description
**Dataset:** `SalesData_1000Rows_WithIssues_copy.csv`

The dataset contains customer order information with the following attributes:

- OrderID
- OrderDate
- CustomerName
- Region
- Product
- Category
- Quantity
- UnitPrice
- Sales
- Cost
- Profit

The original dataset contained missing values, duplicate records, and date-format inconsistencies.

## Tools and Technologies Used
- Microsoft Power BI Desktop
- Power Query Editor
- DAX (Data Analysis Expressions)
- CSV Dataset

## Data Cleaning and Preprocessing

The following data-cleaning operations were performed using Power Query Editor:

1. Imported the CSV dataset into Power BI.
2. Identified missing values across different columns.
3. Removed records with missing CustomerName, Region, and Product values.
4. Replaced missing numerical values in UnitPrice, Sales, Cost, and Profit with 0.
5. Removed records with missing OrderDate values.
6. Removed duplicate rows.
7. Standardized the OrderDate column using the Date data type and English (United Kingdom) locale.
8. Loaded the cleaned dataset into the Power BI data model.

## Data Visualization

Three visualizations were created to analyze the sales data.

### 1. Regional Order Distribution – Pie Chart
- Displays the distribution of orders across different geographical regions.
- Uses Region as the legend.
- Uses Count of OrderID as the value.
- Helps compare order distribution across regions.

### 2. Top 5 Trending Products – Column Chart
- Displays the five most frequently ordered products.
- Uses Product on the X-axis.
- Uses Count of OrderID on the Y-axis.
- Applies a Top N filter to display only the top five products.
- Helps identify popular products based on order frequency.

### 3. Profit Trend Over Time – Line Chart
- Displays profit trends over time.
- Uses OrderDate on the X-axis.
- Uses Sum of Profit on the Y-axis.
- Helps analyze changes in profit over different dates.

## DAX Calculations

Three DAX objects were created as part of the analysis.

### 1. Calculated Table – EastRegionOrders

Creates a separate table containing only orders from the East region.

```dax
EastRegionOrders =
FILTER(
    SalesData,
    SalesData[Region] = "East"
)
```

### 2. Calculated Column – ProfitCostDifference

Calculates the difference between Profit and Cost for each order.

```dax
ProfitCostDifference =
SalesData[Profit] - SalesData[Cost]
```

### 3. Measure – TotalProfit

Calculates the total profit earned.

```dax
TotalProfit =
SUM(SalesData[Profit])
```

*Note: Replace `SalesData` with the actual table name in Power BI if it differs.*

## Key Analysis Performed

- Analyzed order distribution across different regions.
- Identified the top five products based on order frequency.
- Examined profit trends over time.
- Isolated orders belonging to the East region.
- Calculated profit-cost differences for individual records.
- Calculated total profit using a DAX measure.

## Project Outcome

Successfully developed a Power BI sales analysis report by performing data cleaning, data transformation, visualization, and DAX-based calculations.

The project demonstrates the use of Power BI for preparing raw business data, analyzing sales performance, and presenting information through interactive visualizations.

## Conclusion

This project provided practical experience in using Power BI Desktop, Power Query Editor, and DAX to transform raw sales data into meaningful analytical information. The resulting report helps understand regional order distribution, popular products, and profit trends.
