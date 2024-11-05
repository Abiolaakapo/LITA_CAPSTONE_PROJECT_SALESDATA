
### LITA_CAPSTONE_PROJECT_SALESDATA

### Project  Title: LITA Capstone Sales Analysis

### Project Overview
This project Analysis aims at generating insightful sales performance, top selling product, regional performance and monthly sales trends of a retail store over the past year. By analyzing quantity sold at each regions and total revenue generated through the data we received to be able to make an insightful and reasonable decisions.

### Data Sources
The primary data source used is Data Sales.CSV and this is an open source data that can be easily downloaded from an open online data source such as Kaggle, FRED or any other data repository site.

### Tools Used
- Microsoft Excel [Download Here](https://www.microsoft.com)
  1. Data Cleaning
  2. Data Analysis
  3. Data Visualization.
     
- SQL - Structured Query Language for Querying of Data.

- Power BI
 1. For Data Cleaning
 2. For Data Tranformation
 3. For Data Visualization

- Github For portfolio building.

 ### Data Cleaning And Preparations
In data cleaning and preparation, the following actions were performed:
 1. Data loading
 2. Data cleaning and formatting
 3. Handling missing variables

### Column Description
- OrderID: A unique identifier for each order placed.
- CustomerID: A unique identifier for each customer.
- Product: This is the item offered for sale.
- Region: A geographical location where sales is being made such as North, South, East and West.
- OrderDate: A specific day when a sale is made.
- Quantity: This is the number of product/s purchased.
- Unit Price: This is a fixed amount per product.
- Total Sales: This the total amount generated from the quantity of the products sold which is calculated as quantity by unit sold.

 ### Exploratory Data Analysis
 Exploratory Data Analysis involves deeper anwsers to the following critical questions regarding the SalesData:
 - To retrieve the total sales for each product category.
 - To calculate total sales by region.
 - To calculate the total sales made monthly.
 - To find the top-selling product.
 - To find the highest sales by region.
 - To find the average sales by product.
 - To find the least selling product.
 - To find the highest sales by month.

  ### Data Analysis
  The Data Analysis is carried out by data querying with the use of some select statements such as:
  

```SQL
SELECT * FROM LITA_SALES_DATA

DELETE FROM [dbo].[LITA_SALES_DATA]
WHERE REGION IS NULL

.........RETRIEVE TOTAL SALES fOR ALL PRODUCT
SELECT PRODUCT,
SUM(Quantity * UnitPrice) AS TOTAL_SALES 
FROM LITA_SALES_DATA
GROUP BY PRODUCT


........NUMBER OF SALES TRANSACTION IN ALL REGION.......
SELECT REGION,
COUNT(Quantity * UnitPrice)
AS TOTAL_SALES FROM LITA_SALES_DATA
GROUP BY REGION

........HIGHEST SELLING PRODUCT.......
SELECT TOP 1 PRODUCT,
SUM(Quantity * UnitPrice) AS TOTAL_SALES
FROM [dbo].[LITA_SALES_DATA]
GROUP BY PRODUCT


.....TOTAL REVENUE PER PRODUCTS........
SELECT PRODUCT,
SUM(Quantity * UnitPrice) AS 
TOTAL_REVENUE
FROM [dbo].[LITA_SALES_DATA]
GROUP BY PRODUCT

.........MONTHLY SALES TOTAL FOR THE CURRENT YEAR........
SELECT MONTH(OrderDate) AS MONTH,
SUM(Total_Sales) AS Monthly_Sales
FROM [dbo].[LITA_SALES_DATA]
WHERE YEAR(OrderDate)=2024
GROUP BY MONTH(OrderDate)
ORDER BY MONTH(OrderDate)

.........MONTHLY SALES TOTAL FOR THE PREVIOUS YEAR........
SELECT MONTH(OrderDate) AS MONTH,
SUM(Total_Sales) AS Monthly_Sales
FROM [dbo].[LITA_SALES_DATA]
WHERE YEAR(OrderDate)=2023
GROUP BY MONTH(OrderDate)
ORDER BY MONTH(OrderDate)


.......TOP 5 CUSTOMERS BY TOTAL PURCHASE AMOUNT........
SELECT TOP 5 Customer_Id,
SUM(Quantity * UnitPrice) AS Total_Purchase_Amount
FROM [dbo].[LITA_SALES_DATA]
GROUP BY Customer_Id
ORDER BY Total_Purchase_Amount DESC


.........PERCENTAGE OF TOTAL SALES CONTRIBUTED BY EACH REGION........
SELECT Region,
SUM(Total_Sales) AS Regional_Sales
FROM [dbo].[LITA_SALES_DATA]
GROUP BY Region


.......PRODUCT WITH NO SALES IN THE LAST QUARTER.........
SELECT Product FROM [dbo].[LITA_SALES_DATA]
WHERE (OrderDate) < DATEADD(QUARTER,-1,2024)
GROUP BY Product
```

### Data Visualization


[LITA CAPSTONE PROJECT (SALES DATA).xlsx](https://github.com/user-attachments/files/17627693/LITA.CAPSTONE.PROJECT.SALES.DATA.xlsx)









### Results
From the Analysis carried out, it was deduced that our customers love to shop for quality and affordability which is the goal of the shopping store. The total revenue generated was 2,101,090 approximately 2Milllion. From the Grand Total , the Southern region made their way to the top as it has a total of 927,820 which is exactly 44.16% of the total revenue. Second on the chart is the Eastern region with 23.13%, followed by the Northern region with 18.42% while the Western region, with not so good performance but added their quota of 14.29% to the total revenue generated. The dataset also shows an insight on the month with the highest sales amounting to 546,300 which is February while September recorded the lowest sales amounting to 34,720, but still very crucial as it added to the total revenue for the year. The most lucrative product of the year is Shoes with an outstanding sales of 613,380 while the Average Sales by product is 211.78 which in all honesty is a good sales number for the year. 

    
    








  
 


  


          
