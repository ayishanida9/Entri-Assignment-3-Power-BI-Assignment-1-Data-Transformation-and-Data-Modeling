# Power-BI-Assignment-1-Data-Transformation-and-Data-Modeling
Instructions:-
Import Data:
●
●
●
Import “List of Orders.csv” into Power BI.
Open “List of Orders” in Power Query Editor by clicking on ‘Transform’
.
Import “Order Details.csv” and “Sales target.csv” into Power Query Editor.
●
●
●
●
Data Transformation:
Restrict the "List of Orders" table to only the first 500 rows.
Ensure the “Order Date” column in the “List of Orders” table is set to data type 'Date'
.
Change the data type of “Amount” and “Target” columns to ‘Fixed Decimal Number’
.
Format the "CustomerName" column into proper case, ensuring consistent
capitalization for each word.
Merge the "State" and "City" columns to create a new column named "Location" in
the format ‘City, State’
.
Create a new custom column named "Profit Margin" as the percentage of "Profit"
divided by "Amount"
.
●
●
●
Add a new conditional column named "Profit Status" based on the values in the
"Profit" column. The conditions are as follows: if the profit is less than 0, the label
should be "Loss"; if the profit equals 0, the label should be "Break-Even"; and if the
profit is greater than 0, the label should be "Profit"
.
Merging Data (Joins):
●
Merge the "List of Orders" and "Order Details" tables into a new single table named
"Orders Data" based on the "Order ID" relationship.
Handling Missing Data & Duplicate Data:
●
●
Identify missing values in the data and determine a strategy to address them.
Check for duplicate rows and define a strategy to handle duplicates.
Sorting and Filtering Data:
●
In the ‘Orders Data’ table, utilize sorting and filtering techniques on columns like
Order Date, State or Category to analyze data based on specific criteria:
◆ Sort the orders by Order Date in descending order to analyze recent trends.
◆ Filter the orders to focus only on a specific state (e.g., Tamil Nadu) for
regional analysis.
Grouping and Aggregating Data:
●
●
Duplicate the “Order Details” table and calculate the count of each Order ID, average
profit by Category or total amount by Sub-Category.
Duplicate the “Sales Target” table and aggregate the total target amount by Month of
Order Date.
Data Modeling:
●
●
Establish a relationship between the “List of Orders” and “Order Details” tables using
the ‘Order ID’ column.
Build a relationship between the “Order Details” and “Sales Target” tables based on
the ‘Category’ column. Click "Manage relationships" and ensure this relationship is active
