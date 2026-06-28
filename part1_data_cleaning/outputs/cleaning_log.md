
# Task 5-Apply Business Rules

# Business Rules Applied

1. **Missing Region**

   * Blank values in the region column were replaced with "Unknown".
   * 25 missing values in region column were found after removing the duplicate rows.

2. **Missing Ship Mode**

   * Blank values in the ship_mode column were replaced with "Unknown".
   * 21 missing values in ship mode were found after removing duplicate rows

3. **Missing Discount**

   * Missing discount values were replaced with 0 only when quantity, unit price, and cost were available. Total of 18 mising discount values were found.
   
   * Records missing other required sales fields were left unchanged and flagged for review. 

4. **Negative Discount**

   * Negative discount values were treated as invalid. 
   * These records were flagged and included in the Invalid Discount Summary.

5. **Discount Above Allowed Range**

   * Discounts above the allowed range were flagged as invalid.The allowed range of 90% discount was kept and discounts above it were chosen as invalid.
   

6. **Cancelled Orders**

   * Cancelled orders were retained in the cleaned dataset but excluded from completed sales and profit summaries.

7. **Failed Payments**

   * Orders with failed payments were retained but excluded from completed sales and profit summaries.

8. **Refunded Orders**

   * Refunded orders were retained and summarized separately in the Pivot Summary Report.

9. **Ship Date Before Order Date**

   * Records where the ship date occurred before the order date were flagged as invalid shipping records. Total of 95 records were found to be invalid.
   * These records were included in the Date Issue Summary.
# Task 9- Write Cleaning Log
Issues Found-
*Extra spaces
*Inconsistent case
*Missing region
*Missing ship mode
*Invalid discounts
*Date issues
*Duplicate records
*Duplicate orderID

Actions Performed
For text related columns fuctions like TRIM,SUBSTITUTE,PROPER were used.
Date conversion
First the dates all the dates were present as text so it was converted to date format and still it was found that some dates were present as text so it was changed from mm/dd/yyyy format tp dd/mm/yyy format. All the dates were standardised in dd/mm/yyyy format.
Duplicate identification- 
Duplicate Handling
1. Exact duplicate rows were identified using duplicate row checks.
2. Exact duplicates were removed from the cleaned dataset.
3. Duplicate order IDs containing conflicting values were not removed.
4. Such records were flagged for review.
5. All duplicate statistics were documented in the Data Quality Report.

Business Rules Applied
All the business rules were applied and summarised.
Unknown region-
blank regions and ship mode were filled with Unknown after checking if the cell wa blank using countblank function in excel.Simplary for discount, blank cells were filled with 0.
Rows found to have issues have been flagged.

Assumptions
Maximum valid discount = 90%
And for calculating sales all the invalid discounts(negative disount and dicount above 90%) are considered as 0.

Records removed- 20 (duplicate rows)
Records Flagged-
*Duplicate order IDs
*Invalid discounts
*Invalid dates

Limitations
Conflicting duplicates and records flagged  require manual review
