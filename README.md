# Data-Analysis-Bootcamp
A documentation of my journey through a Data Analysis bootcamp, featuring weekly notes, practical exercises, and data manipulation projects starting with Google Sheets.



# 📊 Data Analysis Bootcamp - Notes & Practices

This repository tracks my progress, notes, and practical exercises throughout my Data Analysis training. I will be updating this weekly with new techniques, formulas, and projects I complete.

## 🗓️ Week 1: Google Sheets Fundamentals, Data Manipulation, and Summarization

This week, I focused on gathering scattered data, connecting different datasets, and extracting meaningful summaries from large raw data files using Google Sheets.

### 1. Importing External Data
Learned how to automate data extraction from external sources and other files using built-in Google Sheets functions:

* **IMPORTDATA:** Used to pull raw data in CSV or TSV format directly from a live web URL.
  `=IMPORTDATA("https://example.com/data.csv")`

* **IMPORTRANGE:** Used to sync a specific range of cells from an entirely different Google Sheets file into the current workspace. *(Note: Requires clicking "Allow Access" on the `#REF!` error when connecting files for the first time).*
  `=IMPORTRANGE("spreadsheet_url", "SheetName!A1:B9")`

### 2. Data Merging and Queries (XLOOKUP)
Explored `XLOOKUP` as a modern, more flexible alternative to traditional `VLOOKUP` for joining data across different tables using common keys. Practical use cases included:

* **Campaign Mapping:** Matching Campaign IDs to their respective Campaign Names.
  `=XLOOKUP(A2, Details!A:A, Details!B:B, "")`

* **Employee Departments:** Assigning employees to their departments based on their last names.
  `=XLOOKUP(B2, Departments!A:A, Departments!B:B, "No Record")`

* **Inventory Tracking:** Pulling real-time stock levels from a master database using Product Codes.
  `=XLOOKUP(A2, Products!A:A, Products!B:B, "Product Not Found")`

### 3. Dynamic Arrays (ARRAYFORMULA)
Instead of dragging formulas down thousands of rows, I learned how to use array formulas to populate entire columns from a single cell. This makes spreadsheets lighter and fully automated.
  `=ARRAYFORMULA(IF(A2:A="", "", XLOOKUP(A2:A, Products!A:A, Products!B:B, "Product Not Found")))`

### 4. Pivot Tables & Basic Data Logic
Mastered the basics of transforming massive datasets into digestible reports using Pivot Tables:
* **Grouping:** Categorizing data by months, departments, or product types.
* **Metrics:** Calculating core metrics like Sum, Average, and Count in seconds.
* **Filtering:** Slicing the data to focus on specific segments or timeframes.
