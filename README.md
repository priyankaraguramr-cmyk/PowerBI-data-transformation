 PowerBI-data-transformation
 PowerBI_Assignment1 — E-Commerce Sales Data Analysis

Project Overview:
This project involves data preparation, transformation, and modeling of an E-commerce sales dataset using "Power BI"and "Power Query Editor" The goal is to perform data import, cleansing, aggregation, merging, and relationship modeling to build a structured data model for analysis.

Dataset Description:
Three CSV datasets were used:
Dataset and Attributes 
*List of Orders* Order ID, Order Date, Customer Name, City, State, Category, Amount, Profit 
*Order Details* Order ID, Category, Sub-Category, Quantity, Amount, Profit 
*Sales Target* Category, Month of Order Date, Target 

Tasks Completed
1. Data Import:
- Imported `List of Orders.csv` into Power BI
- Opened Power Query Editor using Transform Data
- Imported `Order Details.csv` and `Sales Target.csv` into Power Query Editor

2. Row Limiting & Data Types:
- Restricted "List of Orders" to first "500 rows"
- Set "Order Date" column to "Date" data type
- Changed "Amount" and "Target"columns to "Fixed Decimal Number"

3. Text Formatting:
- Formatted "CustomerName"column to "Proper Case" for consistent capitalization

4. Column Creation:
- Created "Location" column by merging City and State: `City, State` format
- Created "Profit Margin" column: `Profit / Amount` (expressed as a percentage)

 5. Conditional Column:
 Created "Profit Status" column based on:
- Profit < 0 → 'Loss'
- Profit = 0 → 'Break-Even'
- Profit > 0 → 'Profit'

 6. Data Merging (Joins):
- Merged "List of Orders"and "Order Details" tables using "Order ID"
- Join Type: "Left Outer Join"
- Output table named: "Orders Data"
- Expanded columns: Quantity, Category, Sub-Category

7. Handling Missing & Duplicate Data:
- Identified null values across tables
- Applied "Remove Duplicates" on Orders Data
- Retained nulls where Order IDs did not match (different ID ranges between tables)

8. Sorting and Filtering:
- Sorted "Orders Data" by "Order Date" in "Descending" order
- Filtered "Orders Data" to show only "Tamil Nadu" state records

9. Grouping and Aggregating Data:
Created 4 aggregation tables by referencing base tables:

| Table Name | Group By | Aggregation | Column |
| Count by Order ID | Order ID | Count Rows | 
| Avg Profit by Category | Category | Average | Profit |
| Total Amount by SubCategory | Sub-Category | Sum | Amount |
| Total Target by Month | Month of Order Date | Sum | Target |

10. Data Modeling:
Established relationships in Model View:

| From Table | Column | To Table | Column | Type |
| List of Orders | Order ID | Order Details | Order ID | Many to One |
| Order Details | Category | Sales Target | Category | Many to One |
Both relationships set as "Active"
Cross-filter direction: "Single"

 Queries in Power Query Editor (7 Total)
1. "Order Details" — base product-level data (600 rows)
2. "Sales Target" — monthly category targets (96 rows)
3. "List of Orders" — customer order data with transformations (500 rows)
4. "Orders Data" — merged table (List of Orders + Order Details)
5. "Count by Order ID" — aggregation table
6. "Avg Profit by Category"— aggregation table
7. "Total Amount by SubCategory" — aggregation table
8. "Total Target by Month" — aggregation table (referenced from Sales Target)

 Files Submitted:
| File | Description |
| 'PowerBI_Assignment1.pbix'| Power BI file with all transformations and data model |
| 'PowerBI_Assignment1_Report.pdf' | PDF with screenshots and transformation explanations |
| 'README.md' | This documentation file |

 Tools Used:
- "Power BI Desktop"
- "Power Query Editor"
- "DAX (Data Analysis Expressions)" — for data modeling
- "M Language" — used internally by Power Query

 Key Learnings:
- Data import and transformation using Power Query
- Creating calculated and conditional columns
- Merging tables using Left Outer Join
- Grouping and aggregating data
- Building data model relationships in Power BI

 Author:
"Assignment:" PowerBI_Assignment1  
"Subject:" Data Analytics — Power BI  
"Date:" June 2026
