# Sales Orders Data Cleaning and Analysis

## Problem Summary

The objective of this project was to clean, validate, and analyze a raw sales orders dataset using Microsoft Excel. The dataset contained inconsistencies such as missing values, duplicate records, invalid dates, inconsistent text formatting, and business rule violations. The cleaned dataset was used to generate data quality reports and business summary pivot tables.

---

## Dataset Description

The project dataset consists of two worksheets:

* **Sheet1:** Raw sales order data containing customer, product, sales, shipping, and payment information.
* **Sheet2:** Business rules specifying the required data cleaning and validation logic.

The cleaned dataset was saved as:
* data/raw_orders.xlsx (original dataset)
* data/cleaned_orders.xlsx (cleaned dataset)

## Tools Used

* Microsoft Excel
* Excel Functions:

  * TRIM
  * SUBSTITUTE
  * IF
  * IFERROR
  * COUNTIF
  * COUNTIFS
  * DATE
  * DATEVALUE
  * YEAR
  * MONTH
  * TEXT
  * DATEDIF
* Pivot Tables
* Conditional Formatting
* Flash Fill
* Text to Columns

## Cleaning Steps Performed

### 1. Text Standardization

* Removed leading and trailing spaces.
* Removed unnecessary extra spaces.
* Standardized capitalization.
* Corrected inconsistent category names.

### 2. Date Cleaning

* Converted valid text dates into Excel date format.
* Standardized all valid dates to a consistent format (DD-MM-YYYY).
* Flagged:
  * Ship dates earlier than order dates

### 3. Duplicate Handling

* Identified exact duplicate rows.
* Removed verified exact duplicates.
* Identified duplicate Order IDs with conflicting information.
* Flagged conflicting records for manual review.

### 4. Business Rule Validation

* Filled missing Region values with Unknown.
* Filled missing Ship Mode values with Unknown.
* Replaced missing Discount values with 0 only when applicable.
* Flagged negative and out-of-range discounts.
* Excluded cancelled and failed payment orders from completed sales summaries.
* Summarized refunded orders separately.
* Flagged invalid shipping records.

### 5. Calculated Columns Created

* cleaned_discount
* calculated_sales
* calculated_profit
* profit_margin
* shipping_delay_days
* order_month
* order_year
* data_quality_flag

## Summary of Data Quality Issues Found

| Issue                       | Count |
| --------------------------- | ----: |
| Missing Region              |    25 |
| Missing Ship Mode           |    21 |
| Missing Discount            |    18 |
| Invalid Discount            |    15 |
| Missing Dates               |     0 |
| Invalid Dates               |     0 |
| Ship Date Before Order Date |     95| (before removing duplicates)
| Exact Duplicate Rows        |     40 |
| Duplicate Order IDs         |     24 |(after removing duplciates)
| Records Removed             |     20 |
| Records Flagged for Review  |     142 |


## Summary of Final Pivot Reports

The following Pivot Tables were created:

1. Sales and Profit by Region
2. Sales and Profit by Category and Sub-category
3. Order Count by Ship Mode
4. Profit Margin by Customer Segment
5. Refunded, Cancelled, and Failed Orders by Region
6. Monthly Sales Trend

## Key Business Insights


* The highest sales were generated from the **east** region.
* The  **Technology** category contributed the highest revenue.
* The **Small Business** customer segment achieved the highest profit margin.
* Standard shipping was the most frequently used shipping method.
* Refunded and cancelled orders represented only a small portion of total orders.

## Assumptions and Limitations

### Assumptions

* Missing Region values were replaced with Unknown.
* Missing Ship Mode values were replaced with Unknown.
* Missing Discount values were treated as 0 only when other sales fields were valid.
* Negative and out-of-range discounts were considered invalid.
* Cancelled and failed payment orders were excluded from completed sales analysis.
* Refunded orders were analyzed separately.

### Limitations

* Conflicting duplicate Order IDs were retained and flagged for manual review.
* Business rules were implemented only as specified in the assignment.

