# Sales Data Analysis Dashboard - Power BI Project

This project involves the creation of a **Sales Data Analysis Dashboard** using **Power BI** to visualize key sales metrics and insights for data-driven decision-making. The dashboard includes various visualizations such as bar charts, pie charts, donut charts, and line charts to display sales performance and trends.

## Key Metrics and Insights:
1.**Total Profit**: The total profit generated across all sales channels.
2.**Total Revenue**: Revenue segmented by various dimensions like channels, customers, and products.
3.**Total Order Quantity**: Total quantity of orders processed over different time periods.
4.**Total Unit Cost**: The total cost of units sold, segmented by different sales channels (e.g., Wholesale, Distributor, Export).
5.**Top 5 Customers by Order Quantity**: Identifying the top 5 customers contributing the most to order volume.
6.**Total Revenue by Products**: Shows revenue contribution by different product categories.
7.**Order Quantity by Month and Year**: Visualization of order volume over months for multiple years (2017, 2018, 2019).
8.**Unit Costs by Currency**: Unit cost breakdown by currency (AUD, EUR, GBP, etc.).


## Skills & Technologies Used:
- **Power BI**: For data visualization, modeling, and reporting.
- **DAX (Data Analysis Expressions)**: Used to create measures, calculated columns, and key metrics.
- **Data Cleaning**: Handling missing data, duplicates, and inconsistencies in sales data.
- **Data Modeling**: Establishing relationships between sales, product, and region tables.
- **Power Query**: For transforming and loading data from external sources.

## DAX Queries Used:
1. **Total Sales**:
   ```DAX
   Total Sales = SUM(Sales[SalesAmount])
2. **Profit Margin**:
   ```DAX
   Profit Margin = DIVIDE(SUM(Sales[Profit]), SUM(Sales[SalesAmount]))
3. **Sales Growth (Month-over-Month)**:
   ```DAX
   Sales Growth = IF(
    ISBLANK([Total Sales]),
    BLANK(),
    ([Total Sales] - CALCULATE([Total Sales], DATEADD(Date[Date], -1, MONTH))) 
    / CALCULATE([Total Sales], DATEADD(Date[Date], -1, MONTH)))
4. **Top Selling Products**:
   ```DAX
   Top Products = TOPN(5, Product[ProductName], [Total Sales], DESC)

## Visualizations Included:

1.**Bar Chart**:
   - Displays total order quantity across months and years (2017-2019).
   - Visualizes revenue and order quantity by products.
2. **Pie Chart**:
   - Shows customer index, depicting the top 5 customers by order quantity.
4. **Stacked Bar Chart**:
   - Displays the total unit cost by channel, categorized by currency codes (AUD, EUR, GBP, NZD, USD).
5. **KPI Cards / Gauge Charts**:
   - Total profit, total revenue, total order quantity, and total unit cost are highlighted using circular KPI visuals.
6. **Line and Bar Combo Chart**:
   - Combines line and bar charts to show both the sum of total revenue and the sum of order quantity across product descriptions.
     
## Project Objectives:
 - Provide insights into sales performance, customer segmentation, and profit margins.
 - Allow users to explore data interactively by filtering by years, products, or channels.
 - Highlight the top contributing customers and channels for revenue and cost management.
