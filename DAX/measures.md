# DAX Measures

This page contains the DAX measures used in the Sales Performance Dashboard.

The measures support the analysis of sales, profit, costs, customers, orders, quantity, and target performance.

---

## Sales & Performance Measures

### 1. Total Sales

Calculates the total sales amount.

```DAX
Total Sales =
SUM(Sales[SalesAmount])
```

### 2. Total Profit

Calculates the total profit generated from sales.

```DAX
Total Profit =
SUM(Sales[ProfitAmount])
```

### 3. Total Cost

Calculates the total cost associated with sales.

```DAX
Total Cost =
SUM(Sales[CostAmount])
```

### 4. Profit Margin %

Calculates the profit margin based on total profit and total sales.

```DAX
Profit Margin % =
DIVIDE(
    [Total Profit],
    [Total Sales],
    0
)
```

### 5. Total Quantity

Calculates the total quantity of products sold.

```DAX
Total Quantity =
SUM(Sales[Quantity])
```

### 6. Number of Customers

Calculates the distinct number of customers.

```DAX
Number of Customers =
DISTINCTCOUNT(Sales[CustomerID])
```

### 7. Number of Orders

Calculates the distinct number of orders.

```DAX
Number of Orders =
DISTINCTCOUNT(Sales[SalesID])
```

---

## Target Measures

### 8. Profit Target

Calculates the total profit target.

```DAX
Profit Target =
SUM(Targets[ProfitTarget])
```

### 9. Sales Target

Calculates the sales target for the selected month by matching the selected month with the corresponding target period.

```DAX
Sales Target =
CALCULATE(
    SUM(Targets[SalesTarget]),
    TREATAS(
        VALUES('Date'[MonthStartDate]),
        Targets[TargetMonthStart]
    )
)
```

### 10. Sales Target Achievement %

Calculates the percentage of total sales achieved against the sales target.

```DAX
Sales Target Achievement % =
DIVIDE(
    [Total Sales],
    [Sales Target],
    0
)
```

---

## Measure Summary

| Measure | Purpose |
|---|---|
| Total Sales | Total sales amount |
| Total Profit | Total profit amount |
| Total Cost | Total cost amount |
| Profit Margin % | Profitability percentage |
| Total Quantity | Total quantity sold |
| Number of Customers | Distinct customer count |
| Number of Orders | Distinct order count |
| Profit Target | Total profit target |
| Sales Target | Sales target for the selected month |
| Sales Target Achievement % | Percentage of sales target achieved |

---

## Notes

- The measures are created using DAX in Power BI.
- The measures respond to report filters and slicers.
- The Sales Target measure uses the selected month to match sales data with the corresponding target period.
- DIVIDE is used for percentage calculations to safely handle cases where the denominator is zero.
