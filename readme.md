
# Retail Sales Performance Dashboard (Power BI)

   * Beginner Power BI project analyzing sales data at product, region, and customer level.


## Project overview:

   * Interactive Power BI dashboard built on the Superstore dataset to analyze sales, profit, product performance, and customer trends.



## Problem statement:

   * Provide clear insights into sales and profitability across products and regions to support data-driven decisions.



## Dataset:

   * Raw and clean dataset have been attached along in the repository.


## What I built:

   * Star schema: `Fact_Sales` + `Dim_Product`, `Dim_Customer`, `Dim_Region`, `Dim_Date`. Built all the dimension tables from a single fact table and built     
                relationship between various dimension tables and fact tables.

   * Power BI dashboards: Sales Performance, Product Performance, Customer Analysis.

   * Key measures: 
  	1.  Total_Sales = sum(Fact_Sales[Sales])
	2.  Total Sales LY = CALCULATE([Total_Sales],SAMEPERIODLASTYEAR(Dim_Date[Date]))
	3.  Growth % = DIVIDE(([Total_Sales]-[Total Sales LY]),[Total Sales LY])
  	4.  Total_Profit = sum(Fact_Sales[Profit])
  	5.  Profit_Margin = DIVIDE([Total_Profit],[Total_Sales],0)
  	6.  Total_Quantity_Sold = SUM(Fact_Sales[Quantity])
  	7.  Total_Order_Count = DISTINCTCOUNT(Fact_Sales[Order ID])
  	8.  Average_Order_Value = DIVIDE([Total_Sales],[Total_Order_Count],0)
  	9.  Average Quantity Sold Per Order = DIVIDE([Total_Quantity_Sold],[Total_Order_Count],0)
  	10. Total Customers Count = DISTINCTCOUNT(Fact_Sales[Customer ID])
	11. Sales per Customer = DIVIDE([Total_Sales],[Total Customers Count]) 
	12. Rank = RANKX(ALL(Dim_Product[Product ID]),[Total_Sales],,DESC,Skip)
	13. Top 100 Products Sales = CALCULATE([Total_Sales],TOPN(100,ALL(Dim_Product),[Total_Sales],DESC)
	14. Top 100 Products Contribution = DIVIDE([Top 100 Products Sales],[Total_Sales],0)
	

## How to run locally:

	1. Download raw data from `Datasets` >> `Bad\_data` >> `Superstore\_bad\_data.csv`
	2. Download clean data from `Datasets` >> `Clean\_Data` >> `Clean Data.xlsx`
	3. Open Power BI Desktop → Get Data → CSV/Excel → load the sample files.  
	4. Open `Superstore\_Project.pbix` for relationships between various dimension tables and fact table.


## Files included:

	1.  `Dataset` — For raw and clean dataset. 

	2.  `Dashboard Screenshots` —  for dashboard screenshots for sales performance, product performance and customer analysis. 

	3.  `Superstore\_Project.pbix` - for Power BI file for detailed analysis.



## Key insights:

	1. Top 100 products out of total 1862 products contribute 43% of total sales.    
	2. Q4 sales are highest among all 4 quarters (seasonal impact).
	3. 'Consumer segment' contributes 50.56 % of the total sales out of all customer segments.
	4. Western region has the highest sales across all regions.



## Author: 

	 Aashish Rohila\[LinkedIn](https://www.linkedin.com/in/yourprofile) — email: aashish0292@gmail.com





