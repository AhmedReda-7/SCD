# SCD
Essay about SCD types and its role in DWH

Introduction to Data Warehousing (Quick Series)

Before diving into the fundamentals of Data Warehousing, it's essential to understand one of the core concepts in data management:
Slowly Changing Dimensions (SCD).

In any data system, we typically deal with two main types of data:

Historical Data – previously stored records

New Data – incoming records from the data extraction process

Why do we need SCD?
In real-world scenarios, data changes over time.

For example:

An employee gets promoted, resulting in a salary increase

A customer changes their residential address

A client updates their marital status from "Single" to "Married"

These kinds of changes don’t occur frequently, but when they do, we need a structured approach to manage and track them.
This is where Slowly Changing Dimensions (SCD) come into play—offering multiple strategies to handle data changes effectively.

Common Types of SCD:
🔹 SCD Type 0 – Fixed (No Change)

The data remains unchanged regardless of any updates

Changes are ignored as they are considered irrelevant for analysis

🔹 SCD Type 1 – Overwrite

The existing value is replaced with the new one

No historical data is retained

🔹 SCD Type 2 – Full Historical Tracking ✅

The most widely used type

Every change is recorded as a new row with a version, flag, or date range

Example:
An employee’s salary progression: 1600 → 2000 → 5000 → 8000
Each salary record is stored with flags (e.g., 1 for current, 0 for historical) or date ranges (e.g., Start_Date and End_Date)
The most recent record may have a NULL End_Date or a default far-future date like 31/12/9999

🔹 SCD Type 3 – Current and Previous Values

Stores only the current and immediately previous values

Useful when full history is not required, but the most recent change matters

🔹 SCD Type 4 – Historical Table

Historical data is stored in a separate table

This approach improves data integrity and maintains a clean structure in the main dimension table

These are the most commonly used SCD types. Understanding them is crucial when designing and maintaining a Data Warehouse.

In the next post, I’ll discuss the structure and design principles of a Data Warehouse.
# ![SCD](https://raw.githubusercontent.com/AhmedReda-7/SCD/main/SCD.png)
