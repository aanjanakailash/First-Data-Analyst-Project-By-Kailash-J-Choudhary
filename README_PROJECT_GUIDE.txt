Power BI Industry Sales Loss Analysis Project

Files:
1. messy_sales_orders_5060_rows.csv
   Main raw transaction table. It intentionally contains duplicates, mixed date formats, blanks, lower-case city values, uppercase categories, zero/negative quantities, returns/cancellations, and high discounts.

2. products_lookup.csv
   Product master table.

3. customers_lookup.csv
   Customer master table.

4. city_targets.csv
   City-level target, demand index, and production capacity.

5. discount_policy.csv
   Recommended maximum discount and minimum profit margin by product category.

Main business questions:
- Why is company profit low or negative?
- Which cities/categories/segments cause losses?
- Which products are sold at high sales but low profit?
- Which cities should increase production capacity?
- Where should discount be reduced?
- Which sales channel/payment mode has more returns?
- Which city misses sales/profit target?

Suggested Power BI model:
customers_lookup[Customer_ID] 1 -> many messy_sales_orders[Customer_ID]
products_lookup[Product_ID] 1 -> many messy_sales_orders[Product_ID]
city_targets[City] 1 -> many messy_sales_orders[City]
discount_policy[Product_Category] 1 -> many messy_sales_orders[Product_Category]

Important DAX:
Net Sales = SUMX(Orders, Orders[Quantity] * Orders[Unit_Price] * (1 - Orders[Discount_Percent]/100))
Total Cost = SUMX(Orders, Orders[Quantity] * Orders[Unit_Cost] + Orders[Shipping_Cost] + Orders[Marketing_Cost])
Profit = [Net Sales] - [Total Cost]
Profit Margin % = DIVIDE([Profit], [Net Sales]) * 100
Return Rate % = DIVIDE(CALCULATE(COUNTROWS(Orders), Orders[Order_Status] = "Returned"), COUNTROWS(Orders)) * 100
