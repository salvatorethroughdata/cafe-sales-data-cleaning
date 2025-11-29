***Data Cleaning Steps, Cafe Sales Dataset***

This document explains step by step how the raw cafe sales dataset "dirty_cafe_sales.csv" was cleaned using the power query editor.

***1. Import Data**

- Loaded the CSV file "dirty_cafe_sales.csv" using Excel. Data > Get Data > From File CSV.

- The dataset has 8 columns, including Transaction ID, Item, Quantity, Price Per Unit, Total Spent, Payment Method, Location, and Transaction Date.

***2. Promote Headers**

***3. Trim and Clean Text**

- Removed extra spaces using Text.Trim.

- Removed non-printable characters using Text.Clean.

***4. Replace Missing Values**

- Replaced empty cells with "BLANK" in key columns: Item, Quantity, Price Per Unit, Total Spent, Payment Method, Location, Transaction Date.

***5. Fix Quantity Values**

- Added a new column `Quantity_`:
If Quantity (the original column) is "ERROR", "UNKNOWN", or "BLANK" but Price Per Unit and Total Spent are valid, calculated Quantity_ (the new column, note the underscore symbol) as *"Total Spent / Price Per Unit"* and convert it as a number type, otherwise keep the original value Quantity as it is (though it is ERROR, UNKNOWN or BLANK). If Quantity is a number (text type), so the first if doesn't run, convert it as number type. After this, the column has two types of values: TEXT and NUMBER,

- Reorder the new column,

- Remove the original Quantity column.

***6. Fix Price Per Unit Values**

- Added a new column `Price_per_unit`:
If Price Per Unit is "ERROR", "UNKNOWN", or "BLANK" but Quantity_ and Total Spent are valid, calculated Price_per_unit as *"Total Spent / Quantity_"*. In this case, I have converted only the Total Spent Value as number type because before I have already converted Quantity as a number type. If Quantity_ or Total Spent are not valid, keep the original value Price_per_unit as it is (though it is ERROR, UNKNOWN, BLANK). If Price_per_unit is a number (text type), so the first if doesn't run, convert it as number type. After this, the column has two types of values: TEXT and NUMBER,

- Reorder the new column,

- Remove the original Price per unit column.

***7. Fix Total Spent Values**

- Added a new column `Total_spent`:
Calculated as *"Quantity_ X Price_per_unit"* if both Quantity and Price are valid, otherwise, keep the original Total Spent,

- Reorder the new column,

- Remove the original Total Spent column.

***8. Add Flags for Data Quality***

- Added `Flag_transaction_date_inconsistent`: 1 if Transaction Date is invalid (ERROR, UNKNOWN, BLANK), 0 otherwise.

- Added `Flag_Location_inconsistent`: 1 if Location is ERROR, 0 otherwise.

- Added `Flag_inconsistent_Payment_method`: 1 if Payment Method is ERROR, 0 otherwise.

- Added `Flag_inconsistent_transaction`: 1 if there are at least two non valid values among (Quantity_, Price_per_unit and Total_spent), 0 otherwise.

***10. Summary**

- The dataset is now cleaned, numeric columns are corrected, missing values are handled, and flags indicate inconsistent or problematic rows.

- Ready for further analysis or visualization.

