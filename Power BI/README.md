**You can download my Power BI project using this link:**
[Project in Power BI](https://drive.google.com/file/d/1aj1ZW16RY6LCLRXYQPCNllouuSpdtUqX/view?usp=drive_link)

**Tasks that were solved in this file:**
1. Revenue vs. Cost Analysis: Show the total Revenue, Total Profit, and Profit Margin % for the company. He suspects that high discounts are eating into profits.
2. Logistics Bottleneck: Identify the "Late Delivery" rate. Which specific Ship Mode (e.g., Standard vs. Express) has the highest percentage of late deliveries?
3. Return to Sender: Analyze the Returned status. Which specific Product Category has the highest return rate (Returned Quantity / Total Quantity Sold)?
4. Customer Geography: Map the total Sales by Region. Which region is underperforming compared to the others?
5. Product Performance: List the Top 5 products by Revenue and the Bottom 5 products by Profit.
6. Time Series Anomaly: Show a monthly trend of Sales vs. Profit. He specifically wants to know which Month had high sales but unexpectedly low profit (indicating a bad promotion or high returns).
7. Segment Targeting: Show Total Sales broken down by Customer Segment (Consumer, Corporate, Home Office). Which segment is the most profitable?
8. Shipping Efficiency: Calculate the average "Days to Deliver" (Ship Date - Order Date) per Region. He wants to know which region is suffering from the worst logistics delay.
9. Discount Impact: Create a scatter plot showing Discount (%) vs. Profit. He wants to visually see if high discounts are leading to negative profit (losses).
10. Executive Summary KPI Card: A single card view showing: Total Orders, Total Revenue, Average Delivery Days, and Return Rate (%) .

**This project used various charts and the following measures:**
1) Average delivery days = AVERAGE('Retail Order'[Days])
2) Correlation between Discount vs Profit = 
 VAR Avg_discount = AVERAGE('Retail Order'[Discount])
 VAR Avg_profit = AVERAGE('Retail Order'[Profit])
 VAR Sum_product = SUMX('Retail Order', ('Retail Order'[Discount] - Avg_discount)*('Retail Order'[Profit] - Avg_profit))
 VAR Sumsq_discount = SUMX('Retail Order', ('Retail Order'[Discount] - Avg_discount)^2)
 VAR Sumsq_profit = SUMX('Retail Order', ('Retail Order'[Profit] - Avg_profit)^2)
 RETURN DIVIDE(Sum_product, SQRT(Sumsq_discount*Sumsq_profit), 0)
3) Negative profit rate = DIVIDE(COUNTROWS(FILTER('Retail Order', 'Retail Order'[Profit] < 0)), COUNTROWS('Retail Order'), 0) 
4) Profit margin% = DIVIDE([Total profit], [Total revenue], 0)
5) Profit rate percent = DIVIDE([Total profit], [Total revenue], 0)
6) Return rate% = 
 VAR Sales_count = CALCULATE(COUNTA('Retail Order'[Returned]), ALL('Calculations'))
 VAR Returned_count = CALCULATE(COUNTA('Retail Order'[Returned]), 'Retail Order'[Returned] == "Yes")
 RETURN DIVIDE(Returned_count, Sales_count, 0)
7) Total orders = COUNTA('Retail Order'[Order ID])
8) Total profit = SUM('Retail Order'[Profit])
9) Total revenue = SUM('Retail Order'[Sales])


