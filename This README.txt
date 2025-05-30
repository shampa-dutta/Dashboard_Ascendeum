This README explains the approach, data model, and steps taken to build the Power BI dashboard for the Dashboarding Skills Test. It is intended to help users understand the structure of the report and how to interact with its visuals.

1. Data Import and Model Setup

Data Sources:
The dashboard uses four tables: users, products, orders, and page_views, imported from Excel.
Relationships:

orders[user_id] → users[user_id]
orders[product_id] → products[product_id]
page_views[user_id] → users[user_id]


Data Cleaning:
Ensured all columns were properly formatted (e.g., dates, numbers).


2. Key Measures Created

Revenue:
Calculated as the sum of orders[quantity] * products[price] using a DAX measure.
Total Orders:
Count of all orders.
Average Order Value (AOV):
Revenue divided by total orders.
New User Conversion Rate:
Percentage of new users who placed an order.
Orders by Region, Referrer, and Product Category:
Aggregated using DAX measures and relationships.


3. Visuals and Their Construction

A. Monthly Revenue Trend

Purpose: Show revenue over time.
How Built:

Used a Line Chart.
Axis: orders[order_date] (set to Month).
Value: Revenue measure.



B. Orders and AOV by Region

Purpose: Compare order volume and AOV across regions.
How Built:

Used a Clustered Column Chart.
Axis: users[region].
Values: Orders and AOV measures.



C. Top Referrers

Purpose: Identify which referrers drive the most orders.
How Built:

Used a Bar Chart.
Axis: users[referrer].
Value: Orders measure.
Sorted by descending order count.



D. Product Category Performance

Purpose: Analyze sales by product category.
How Built:

Used a Table visual.
Rows: products[category].
Values: Orders, Revenue, and Average Quantity measures.



E. Drill-Down from Region to User-Level

Purpose: Allow users to see user-level details within each region.
How Built:

Created a hierarchy in the Fields pane: region → user_id.
Added the hierarchy to a Table or Matrix visual.
Enabled drill-down using the visual’s drill controls.



F. New User Conversion Funnel

Purpose: Show metrics.
How Built:

Used Card visuals


