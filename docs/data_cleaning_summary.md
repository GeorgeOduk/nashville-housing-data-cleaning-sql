# Data Cleaning Summary

## Project Objective

The purpose of this project was to clean and standardise a Nashville housing dataset using SQL Server. The raw dataset contained inconsistent date formats, missing property addresses, combined address fields, inconsistent categorical values, duplicate records, and redundant columns.

## Cleaning Steps Completed

### 1. Standardised Sale Date

The original sale date field was converted into a cleaner date-only format using SQL Server's `CONVERT()` function.

### 2. Populated Missing Property Addresses

Missing property address values were populated by matching records with the same `ParcelID`. A self join was used to identify matching rows and fill null property address values.

### 3. Split Property Address

The property address field was split into separate address and city columns using `SUBSTRING()` and `CHARINDEX()`.

### 4. Split Owner Address

The owner address field was split into address, city, and state components using `PARSENAME()` and `REPLACE()`.

### 5. Standardised Sold As Vacant Values

The `SoldAsVacant` column contained inconsistent values such as `Y` and `N`. These were standardised to `Yes` and `No` using a `CASE` statement.

### 6. Removed Duplicate Records

Duplicate records were identified using a CTE and `ROW_NUMBER()`, partitioned by key property sale fields including `ParcelID`, `PropertyAddress`, `SalePrice`, `SaleDate`, and `LegalReference`.

### 7. Removed Redundant Columns

After creating cleaner replacement columns, unused columns were removed to simplify the final dataset.

## Skills Demonstrated

- SQL data cleaning
- T-SQL scripting
- Data standardisation
- Missing value treatment
- Self joins
- String manipulation
- Duplicate detection
- CTEs
- Window functions
- Data preparation for analysis