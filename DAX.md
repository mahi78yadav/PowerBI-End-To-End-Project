
# ADW-SalesAnalytics — DAX Measures Guide

This guide contains DAX measures for the AdventureWorks Power BI project, with simple explanations and extra plain-English detail for complex expressions.

## Before You Start

- Create each formula as a **Measure** in Power BI Desktop: right-click a table in the Fields pane and select **New measure**.
- Table and column names must match your model. Replace names below if your imported schema differs.
- Revenue and cost are estimated as quantity multiplied by listed product price or cost. If Sales Data contains actual sales amounts or transaction prices, use those instead.
- Product/category measures require correct relationships between Sales Data, Product Lookup, Product Subcategories Lookup, and Product Categories Lookup.
- Time-based measures require a continuous Calendar Lookup date table related to the relevant fact-table dates. Returns may need a separate relationship to Returns Date.

---

## 1. Basic Measures

### 1. Quantity Return

```dax
Quantity Return =
SUM ( 'Returns Data'[Return Quantity] )
```

**Simple meaning:** Add up the number of items returned.

### 2. Quantity Sold

```dax
Quantity Sold =
SUM ( 'Sales Data'[Order Quantity] )
```

**Simple meaning:** Add up the number of items sold.

### 3. Total Customers

```dax
Total Customers =
DISTINCTCOUNT ( 'Sales Data'[Customer Key] )
```

**Simple meaning:** Count each customer once, even if they placed multiple orders.

### 4. Total Orders

```dax
Total Orders =
DISTINCTCOUNT ( 'Sales Data'[Order Number] )
```

**Simple meaning:** Count each order number once, even when an order contains several products.

### 5. Total Revenue

```dax
Total Revenue =
SUMX (
    'Sales Data',
    'Sales Data'[Order Quantity]
        * RELATED ( 'Product Lookup'[Product Price] )
)
```

**Simple meaning:** For each sales row, multiply quantity by the product's listed retail price, then add the amounts.

**Why `SUMX` and `RELATED`?**

- `SUMX` works through Sales Data one row at a time and calculates an amount for each row.
- `RELATED` looks up that product's price from Product Lookup through the relationship.
- `SUMX` adds all the calculated row amounts together.

**Example:** 3 units × ₹100 each = ₹300 for that row.

> If Sales Data has an actual sales amount column, prefer summing that column instead of estimating revenue from the current product list price.

### 6. Total Cost

```dax
Total Cost =
SUMX (
    'Sales Data',
    'Sales Data'[Order Quantity]
        * RELATED ( 'Product Lookup'[Product Cost] )
)
```

**Simple meaning:** For each sales row, multiply quantity by listed product cost and add the results.

### 7. Total Profit

```dax
Total Profit =
[Total Revenue] - [Total Cost]
```

**Simple meaning:** Revenue minus cost. This is a basic gross-profit estimate before other expenses.

### 8. Total Returns

```dax
Total Returns =
[Quantity Return]
```

**Simple meaning:** Another name for returned quantity. It is not a count of return transactions.

### 9. Return Rate

```dax
Return Rate =
DIVIDE ( [Quantity Return], [Quantity Sold], 0 )
```

**Simple meaning:** Returned units divided by sold units. Format as **Percentage** in Power BI.

**Why `DIVIDE`?** It handles a zero denominator safely. The final `0` means the measure returns zero if quantity sold is zero.

---

## 2. Product and Category Measures

### 10. Red Sales

```dax
Red Sales =
CALCULATE (
    [Total Revenue],
    'Product Lookup'[Product Color] = "Red"
)
```

**Simple meaning:** Calculate revenue for red products only.

**Why `CALCULATE`?** It recalculates the existing revenue measure after applying an extra condition—in this case, Product Color must be Red.

### 11. Bike Returns

```dax
Bike Returns =
CALCULATE (
    [Quantity Return],
    'Product Categories Lookup'[Category Name] = "Bikes"
)
```

**Simple meaning:** Add up returned quantities for products in the Bikes category.

> Use the exact category text in your data. It may be `Bikes`, not `Bike`.

### 12. Bike Sales

```dax
Bike Sales =
CALCULATE (
    [Total Revenue],
    'Product Categories Lookup'[Category Name] = "Bikes"
)
```

**Simple meaning:** Calculate revenue for Bikes-category products only.

### 13. Bike Return Rate

```dax
Bike Return Rate =
DIVIDE (
    [Bike Returns],
    CALCULATE (
        [Quantity Sold],
        'Product Categories Lookup'[Category Name] = "Bikes"
    ),
    0
)
```

**Simple meaning:** Returned bike units divided by sold bike units. Format as **Percentage**.

**Step by step:**

1. Calculate bike returns.
2. Calculate bike sales quantity.
3. Divide returned units by sold units.

---

## 3. Measures That Ignore Filters

### 14. All Returns

```dax
All Returns =
CALCULATE (
    [Quantity Return],
    REMOVEFILTERS ()
)
```

**Simple meaning:** Show returned quantity for the whole model, ignoring all report filters.

**Example:** If a slicer selects 2022, this measure still shows returns across all years.

**Why these functions?**

- `CALCULATE` recalculates a measure under changed filter conditions.
- `REMOVEFILTERS()` clears filters from the calculation, so selections such as year, product, and territory do not restrict this total.

### 15. % All Returns

```dax
% All Returns =
DIVIDE ( [Quantity Return], [All Returns], 0 )
```

**Simple meaning:** Returns in the current selection divided by returns across the whole model. Format as **Percentage**.

**Example:** 100 returns in the selected year divided by 1,000 returns overall = 10%.

### 16. Avg Retail Price

```dax
Avg Retail Price =
AVERAGE ( 'Product Lookup'[Product Price] )
```

**Simple meaning:** Average the prices of products currently in context. Product/category filters can change the result.

### 17. Overall Avg Price — Ignores Product Hierarchy Filters

```dax
Overall Avg Price =
CALCULATE (
    AVERAGE ( 'Product Lookup'[Product Price] ),
    REMOVEFILTERS ( 'Product Lookup' ),
    REMOVEFILTERS ( 'Product Subcategories Lookup' ),
    REMOVEFILTERS ( 'Product Categories Lookup' )
)
```

**Simple meaning:** Average catalogue prices across all products, ignoring filters on Product, Subcategory, and Category.

**Example:** Selecting Bikes will not change this average; it still considers products from all categories.

**Important:** This version ignores those three product-related tables, but another filter, such as a date or territory filter, could still affect the result through your model.

If the average must ignore **every report filter**, use this version:

```dax
Overall Avg Price - All Filters Removed =
CALCULATE (
    AVERAGE ( 'Product Lookup'[Product Price] ),
    REMOVEFILTERS ()
)
```

### 18. High Ticket Orders

```dax
High Ticket Orders =
VAR OverallAverage =
    [Overall Avg Price]
VAR QualifyingRows =
    FILTER (
        'Sales Data',
        RELATED ( 'Product Lookup'[Product Price] ) > OverallAverage
    )
RETURN
    CALCULATE (
        DISTINCTCOUNT ( 'Sales Data'[Order Number] ),
        QualifyingRows
    )
```

**Plain-English explanation:**

This counts **unique orders containing at least one product whose listed price is above the overall average product price**.

Imagine the overall average catalogue price is ₹500.

1. `OverallAverage` stores the average price, ₹500, so the formula can reuse it.
2. `FILTER` checks sales rows and looks up the listed price for each product.
3. A row qualifies if its product price is greater than ₹500.
4. `CALCULATE` counts distinct order numbers among those qualifying rows.
5. If an order contains several qualifying products, it is still counted just once.

**Important:** This checks each product's listed price—not the total value of the order. “Orders whose total order value is above average” would require a different formula.

---

## 4. Previous-Month Measures

These use the `Calendar Lookup` date column. The calendar should contain continuous dates and be related correctly to the relevant fact table.

### 19. Previous Month Returns

```dax
Previous Month Returns =
CALCULATE (
    [Quantity Return],
    DATEADD ( 'Calendar Lookup'[Date], -1, MONTH )
)
```

**Simple meaning:** Show returns for the month before the month currently being viewed.

### 20. Previous Month Orders

```dax
Previous Month Orders =
CALCULATE (
    [Total Orders],
    DATEADD ( 'Calendar Lookup'[Date], -1, MONTH )
)
```

**Simple meaning:** Show the number of orders in the previous month.

### 21. Previous Month Profit

```dax
Previous Month Profit =
CALCULATE (
    [Total Profit],
    DATEADD ( 'Calendar Lookup'[Date], -1, MONTH )
)
```

**Simple meaning:** Show profit for the previous month.

### 22. Previous Month Revenue

```dax
Previous Month Revenue =
CALCULATE (
    [Total Revenue],
    DATEADD ( 'Calendar Lookup'[Date], -1, MONTH )
)
```

**Simple meaning:** Show revenue for the previous month.

**How `DATEADD` works:** It shifts the dates in the current visual context back by one month. `CALCULATE` evaluates the measure over those shifted dates.

> If Returns Data uses `Returns Date` but its relationship to Calendar Lookup is missing or inactive, Previous Month Returns needs a suitable relationship, often activated using `USERELATIONSHIP`, to work as intended.

---

## 5. Rolling, YTD, and Target Measures

### 23. 90 Day Rolling Profit

```dax
90 Day Rolling Profit =
CALCULATE (
    [Total Profit],
    DATESINPERIOD (
        'Calendar Lookup'[Date],
        MAX ( 'Calendar Lookup'[Date] ),
        -90,
        DAY
    )
)
```

**Simple meaning:** Calculate profit over the 90-day period ending at the latest date in the current visual context.

**Step by step:**

1. Find the latest date currently being shown.
2. Build a date range going back 90 days from that date.
3. Calculate profit across that date range.

### 24. YTD Revenue

```dax
YTD Revenue =
TOTALYTD (
    [Total Revenue],
    'Calendar Lookup'[Date]
)
```

**Simple meaning:** Add revenue from the beginning of the year through the current date in the visual.

**Example:** For 15 April, YTD revenue covers 1 January through 15 April of that year.

### 25. 10 Day Rolling Revenue

```dax
10 Day Rolling Revenue =
CALCULATE (
    [Total Revenue],
    DATESINPERIOD (
        'Calendar Lookup'[Date],
        MAX ( 'Calendar Lookup'[Date] ),
        -10,
        DAY
    )
)
```

**Simple meaning:** Calculate revenue over the 10-day period ending at the latest date in the current visual context.

> `DATESINPERIOD` works with calendar dates, not “the last 10 rows.” The exact inclusive date window follows DAX date-interval behavior.

### 26. Order Target

```dax
Order Target = 1000
```

**Simple meaning:** Sample target of 1,000 orders. Replace `1000` with your approved target.

### 27. Revenue Target

```dax
Revenue Target = 1000000
```

**Simple meaning:** Sample revenue target of 1,000,000 in your model's currency. Replace it with the actual target.

### 28. Profit Target

```dax
Profit Target = 200000
```

**Simple meaning:** Sample profit target of 200,000 in your model's currency. Replace it with the actual target.

### 29. Order Target Gap

```dax
Order Target Gap =
[Total Orders] - [Order Target]
```

**Simple meaning:** Actual orders minus target orders. Positive means above target; negative means below target.

### 30. Revenue Target Gap

```dax
Revenue Target Gap =
[Total Revenue] - [Revenue Target]
```

**Simple meaning:** Actual revenue minus revenue target.

### 31. Profit Target Gap

```dax
Profit Target Gap =
[Total Profit] - [Profit Target]
```

**Simple meaning:** Actual profit minus profit target.

---

## 6. Top Customer Measures

These formulas rank customers by **Total Orders first**, then use **Total Revenue** to break ties. If both are tied, the smallest Customer Key wins.

### 32. Top Customer Name

```dax
Top Customer Name =
VAR CustomerSummary =
    ADDCOLUMNS (
        VALUES ( 'Customer Lookup'[Customer Key] ),
        "@Orders", [Total Orders],
        "@Revenue", [Total Revenue]
    )
VAR TopCustomer =
    TOPN (
        1,
        CustomerSummary,
        [@Orders], DESC,
        [@Revenue], DESC,
        'Customer Lookup'[Customer Key], ASC
    )
RETURN
    CONCATENATEX (
        TopCustomer,
        CALCULATE ( SELECTEDVALUE ( 'Customer Lookup'[Full Name] ) ),
        ", "
    )
```

**Plain-English explanation:**

1. `VALUES` creates a list of customers visible under the current filters.
2. `ADDCOLUMNS` calculates each customer's order count and revenue and attaches those values to the list.
3. `TOPN(1, ...)` picks the customer with the most orders. If tied, higher revenue wins; if still tied, lower Customer Key wins.
4. `CONCATENATEX` returns the chosen customer's name as text.

**Note:** The result can change when report filters, such as year or territory, change the customers' sales.

### 33. Top Customer Orders

```dax
Top Customer Orders =
VAR CustomerSummary =
    ADDCOLUMNS (
        VALUES ( 'Customer Lookup'[Customer Key] ),
        "@Orders", [Total Orders],
        "@Revenue", [Total Revenue]
    )
VAR TopCustomer =
    TOPN (
        1,
        CustomerSummary,
        [@Orders], DESC,
        [@Revenue], DESC,
        'Customer Lookup'[Customer Key], ASC
    )
RETURN
    MAXX ( TopCustomer, [@Orders] )
```

**Simple meaning:** Return the order count for the top customer using the ranking rule above.

### 34. Top Customer Revenue

```dax
Top Customer Revenue =
VAR CustomerSummary =
    ADDCOLUMNS (
        VALUES ( 'Customer Lookup'[Customer Key] ),
        "@Orders", [Total Orders],
        "@Revenue", [Total Revenue]
    )
VAR TopCustomer =
    TOPN (
        1,
        CustomerSummary,
        [@Orders], DESC,
        [@Revenue], DESC,
        'Customer Lookup'[Customer Key], ASC
    )
RETURN
    MAXX ( TopCustomer, [@Revenue] )
```

**Simple meaning:** Return the revenue of that same top customer, ranked by orders first and revenue second.

> If you want the top customer **by revenue**, rank `[@Revenue]` first in `TOPN`, not `[@Orders]`.

---

## Quick Reference

| Measure | Meaning |
|---|---|
| Quantity Sold | Units sold |
| Quantity Return | Units returned |
| Total Customers | Unique customers who purchased |
| Total Orders | Unique order numbers |
| Total Revenue | Quantity × listed retail price, summed |
| Total Cost | Quantity × listed product cost, summed |
| Total Profit | Revenue − cost |
| Return Rate | Returned units ÷ sold units |
| Red Sales | Revenue for red products |
| Bike Sales / Bike Returns | Sales revenue / returned units for Bikes |
| All Returns | Returns ignoring all filters |
| % All Returns | Current returns ÷ all-model returns |
| Overall Avg Price | Average catalogue price ignoring product hierarchy filters |
| High Ticket Orders | Unique orders containing a product priced above the overall average |
| Previous Month measures | Measure evaluated over the previous month |
| Rolling measures | Measure over the preceding 90 or 10 calendar days |
| YTD Revenue | Revenue from year start to current date |
| Target Gap | Actual value − target |
| Top Customer | Customer ranked by orders, then revenue |

## Final Checklist

- [ ] Confirm the actual table and column names.
- [ ] Confirm relationships so product/category filters reach the appropriate sales and returns tables.
- [ ] Confirm Calendar Lookup contains continuous dates and is marked as the Date table.
- [ ] Format revenue, cost, profit, and price measures as currency.
- [ ] Format Return Rate, Bike Return Rate, and % All Returns as percentages.
- [ ] Replace example target values with approved business targets.
- [ ] Compare a few measures against manual calculations before building report visuals.
