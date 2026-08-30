# DAX Measures

This file contains the DAX measures used in the Sales Performance Dashboard.

## 1. Number of Customers

Calculates the distinct number of customers.

```DAX
Number of Customers =
DISTINCTCOUNT(Sales[CustomerID])
