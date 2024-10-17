# Sales Data Analysis Dashboard - Power BI Project

This project involves the creation of a **Sales Data Analysis Dashboard** using **Power BI** to visualize key sales metrics and insights for data-driven decision-making. The dashboard includes various visualizations such as bar charts, pie charts, donut charts, and line charts to display sales performance and trends.

## Key Metrics and Insights:
1. **Total Sales**: Aggregated total sales value across all regions and products.
2. **Profit Margins**: Profit margins per product and region.
3. **Sales Growth**: Month-over-month sales growth and trend analysis.
4. **Top Performing Products**: Identification of top-selling products by revenue.
5. **Sales by Region**: Geographic breakdown of sales performance.
6. **Inventory Turnover**: Analysis of how quickly inventory is sold.
7. **Customer Segmentation**: Segmentation of customers based on purchase behavior.

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

- Bar Charts: Show sales trends by category and time.
- Pie Charts & Donut Charts: Represent distribution of sales across categories.
- Line Charts: Highlight monthly sales growth over time.
- Geographical Map: Display sales by region.
- Tree Maps: Illustrate the contribution of products to total sales.

