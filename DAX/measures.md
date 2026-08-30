# DAX Measures

This page contains the DAX measures used in the Sales Performance Dashboard.

The measures are organized by purpose and support the analysis of sales, profit, costs, customers, orders, quantity, and target performance.

---

## Sales & Performance Measures

### 1. Total Sales

Calculates the total sales amount.

```DAX
Total Sales =
SUM(Sales[SalesAmount])
