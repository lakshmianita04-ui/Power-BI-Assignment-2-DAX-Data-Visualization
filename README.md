# Power-BI-Assignment-2-DAX-Data-Visualization
Answers  

Calculated Columns:
● Create a Calculated Column for 'Category Type': Add a calculated column in the Order Details table that combines the 'Category' and 'Sub-Category' columns into a
single 'Category Type' column.
Create a column Category Type = [Category]& " "&[Sub-Category]

● Calculate Revenue per Order in Order Details Table: Create a calculated column in the Order Details table to compute the revenue (Amount * Quantity) per order.
Create a column Revenue__ Order = [Amount]*[Quantity]
● Create a Calculated Column to Categorize Sales: Add a calculated column named ‘Sales Category’ in the Order Details table that categorizes.
Create a column Sales Category = IF([Amount]>1000, "Above Average", "Below Average")

Calculated Measures:
● Calculate Order Count: Define a measure to count the total number of orders in the Order Details table.
Create new measure Order Count = COUNT('Order Details '[Order ID])
● Calculate Average Profit in Delhi: Create a measure to calculate the average profit for orders placed in Delhi.
Create new measure Profit in Delhi = [Average Profit in Delhi]
● Calculate Year-to-Date (YTD) Sales: Define a measure to calculate the total sales amount accumulated from the earliest order date up to each order date.
Create new measure base_sales = sum('Order Details '[Amount]) Create new measure YTD = TOTALYTD([base_sales],Collection[Date])

Data Visualization:
Sales Target Achievement by Category: Compare actual sales with sales targets by category using a clustered column chart. Max Profit Margin by Sub-Category:
Create a CALENDAR by Collection = ADDCOLUMNS(CALENDAR(min('Sales target'[Month of Order Date]),(MAX('Sales target'[Month of Order Date]))),"Year",YEAR([Date]),"Monthnumber",MONTH([Date]),"Month_name",FORMAT([Date],"MMMM"),"QUARTER","Q "& QUARTER([Date]),"DAY",DAY([Date]),"Dayname",FORMAT([Date],"DDDD")) Select model view and order ID in the list of orders  is connected to order ID in the order details.sales target category connects to the category in the list of orders.Create report.
