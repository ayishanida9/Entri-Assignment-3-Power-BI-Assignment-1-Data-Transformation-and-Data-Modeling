# Power-BI-Assignment-1-Data-Transformation-and-Data-Modeling
##Instructions:-
*Import Data:
•Import “List of Orders.csv” into Power BI.
•Open “List of Orders” in Power Query Editor by clicking on ‘Transform’
•Import “Order Details.csv” and “Sales target.csv” into Power Query Editor.

Ans:Import all 3 CSV files
Open Power BI Desktop.
Click Home → Get data → Text/CSV.
Select List of Orders.csv.
Click Transform Data (not Load).
In Power Query Editor, click Home → New Source → Text/CSV and import:
Order Details.csv
Sales target.csv
Check that all three tables appear in the Queries list on the left.

*Data Transformation:
•Restrict the "List of Orders" table to only the first 500 rows.
•Ensure the “Order Date” column in the “List of Orders” table is set to data type 'Date'.
•Change the data type of “Amount” and “Target” columns to‘Fixed Decimal Number’.
•Format the "CustomerName" column into proper case, ensuring consistent
capitalization for each word.
•Merge the "State" and "City" columns to create a new column named "Location" in
the format ‘City, State’.
•Create a new custom column named "Profit Margin" as the percentage of "Profit"
divided by "Amount".
•Add a new conditional column named "Profit Status" based on the values in the
"Profit" column. The conditions are as follows: if the profit is less than 0, the label
should be "Loss"; if the profit equals 0, the label should be "Break-Even"; and if the
profit is greater than 0, the label should be "Profit".

Ans:Part 2: Data transformation in Power Query
  1. Keep only the first 500 rows
1. Select the List of Orders query.
2. Click Home → Keep Rows → Keep Top Rows.
3. Enter 500 and click OK.
  2. Change Order Date to Date type
Select the Order Date column.
Click the data type icon beside the column name.
Choose Date (calendar icon).
  3. Change Amount and Target to Fixed Decimal Number
Do this in the relevant queries:
In Order Details, select Amount.
In Sales target, select Target.
Click the data type icon → Fixed decimal number.
  4. Convert CustomerName to Proper Case
1. Select the CustomerName column.
2. Go to Transform → Format → Capitalize Each Word.
3. Check that names now have consistent capitalization.
   5. Create Location column (City, State)
For this assignment, you need a new column like Chennai, Tamil Nadu.
Recommended method — Add a Custom Column:
1.Select List of Orders.
2.Go to Add Column → Custom Column.
3.New column name: Location
4.Enter this formula:[City] & ", " & [State]
5. Click OK.
This creates Location without deleting your original City and State columns.
If you specifically want to select two columns side by side, hold Ctrl and click both column headings if they aren't next to each other. You can then use Transform → Merge Columns, but that replaces the selected columns, so the custom-column method is safer here.
   6. Create Profit Margin
1.Select Order Details.
2.Go to Add Column → Custom Column.
3.New column name: Profit Margin.
4.Formula: [Profit] / [Amount]
5. Click OK, then set the column type to Percentage.

   7. Create Profit Status
1.Go to Add Column → Conditional Column.
2.Set the rules:
Name the column Profit Status.

*Merging Data (Joins):

•Merge the "List of Orders" and "Order Details" tables into a new single table named
"Orders Data" based on the "Order ID" relationship.

Ans:Part 3: Merge the tables
1.Select List of Orders.
2.Go to Home → Merge Queries → Merge Queries as New.
3.Select Order Details as the second table.
4.Click Order ID in both tables.
5.Choose Left Outer join.
6.Click OK.
7.Rename the new query Orders Data.
8.Click the expand icon beside the merged column and select the fields you need.

*Handling Missing Data & Duplicate Data:

•Identify missing values in the data and determine a strategy to address them.
•Check for duplicate rows and define a strategy to handle duplicates.

Ans:Part 4: Missing and duplicate data
Missing values: Check for null values using column filters. Fill or remove them only when appropriate; don't automatically replace missing amounts or profits with zero.
Duplicates: Use Home → Remove Rows → Remove Duplicates only when rows are genuine duplicates. Check Order ID first because one order may legitimately have 
multiple product rows in Order Details.

*Sorting and Filtering Data:

•In the ‘Orders Data’ table, utilize sorting and filtering techniques on columns like
Order Date, State or Category to analyze data based on specific criteria:
◆ Sort the orders by Order Date in descending order to analyze recent trends.
◆ Filter the orders to focus only on a specific state (e.g., Tamil Nadu) for
regional analysis.

Ans:Part 5: Sort and filter
•Sort Order Date descending using the column dropdown.
•Filter State to Tamil Nadu for regional analysis.
•Remember: sorting and filtering change the resulting data. If you need all states in your final model, don't leave a temporary Tamil Nadu filter applied.

*Grouping and Aggregating Data:

•Duplicate the “Order Details” table and calculate the count of each Order ID, average
profit by Category or total amount by Sub-Category.
•Duplicate the “Sales Target” table and aggregate the total target amount by Month of
Order Date.

Ans:Part 6: Duplicate and group tables
For Order Details:
1.Right-click the query → Duplicate.
2.Select Order ID and use Home → Group By.
3.Choose Count Rows to count rows for each order ID.

You can create another duplicate and group by Category to calculate Average of Profit, or by Sub-Category to calculate Sum of Amount.

For Sales target:

1.Right-click the query → Duplicate.
2.Use Group By on the Month column.
3.Choose Sum of Target.

*Data Modeling:

•Establish a relationship between the “List of Orders” and “Order Details” tables using
the ‘Order ID’ column.
•Build a relationship between the “Order Details” and “Sales Target” tables based on
the ‘Category’ column. Click "Manage relationships" and ensure this relationship is active

Ans:Part 7: Data modeling
After transformations, click Home → Close & Apply.
In Model view:
•Connect List of Orders[Order ID] to Order Details[Order ID].
•Connect Order Details[Category] to Sales target[Category] only if the category values and relationship cardinality support a valid model. Avoid creating an ambiguous many-to-many relationship just to satisfy the instruction.
•Open Manage relationships and check that the intended relationship is active.
