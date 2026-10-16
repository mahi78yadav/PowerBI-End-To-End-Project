# AdventureWorks Power BI Project — Crisp Guide

Condensed from the 85-page guide (Maven Analytics / Udemy course *Microsoft Power BI Desktop for Business Intelligence*). Every table name, formula, setting, position and checkpoint number below is taken exactly from the full guide. Power BI Desktop runs on **Windows only**.

**Project goal:** as a BI Analyst at AdventureWorks (cycling equipment maker), turn raw CSV files into a cleaned data model, DAX measures and an interactive dashboard (KPIs for sales, revenue, profit, returns; regional comparison; product trends; high-value customers).

**Workflow (always):** Power Query (extract/transform) → Load → Model (relationships) → DAX → Report. Rule: do cleaning and column creation as close to the source as possible (Power Query); use DAX for calculations that must react to report filters.

## 1. Setup (Parts 1–2)

### 1.1 Folder structure (never rename/move a CSV afterwards — paths break refresh)

```
AdventureWorks Project\
  Raw Data\   (7 CSVs: Calendar Lookup, Customer Lookup, Product Lookup,
               Product Categories Lookup, Product Subcategories Lookup,
               Territory Lookup, Returns Data  +  Product Category Sales (Unpivot Demo).csv)
    Sales Data\   (AdventureWorks Sales Data 2020.csv, 2021.csv, 2022.csv)
  Images\     (logo + navigation icons)
  AdventureWorks.pbix
```

All CSV names start with `AdventureWorks ` (e.g. `AdventureWorks Territory Lookup.csv`). Sales rows: 2020 = 2,630; 2021 = 23,935; 2022 = 29,481; total **56,046**.

### 1.2 Install and settings (do carefully)

- Install: Microsoft Store (auto-updates), or powerbi.microsoft.com/downloads (manual), or Microsoft 365 plan. **No Power BI Pro account needed** for Desktop.
- **GLOBAL (once):** `File > Options and settings > Options > Preview features` → tick all → OK (restart if asked).
- **CURRENT FILE (repeat for every new .pbix — does not carry over):**
  1. `Data Load` → UNTICK both **Relationships** boxes (*Update or delete relationships when refreshing data*, *Autodetect new relationships after data is loaded*).
  2. `Data Load` → **Time intelligence**: UNTICK *Auto date/time*.
  3. `Regional Settings` → Locale for import = **English (United States)** (CSV dates are month/day/year).
- Save as `AdventureWorks.pbix`.

### 1.3 Interface

| Place | Side | Use |
|---|---|---|
| Power Query Editor (`Home > Transform data`) | Back-end | Connect, profile, clean, shape; each action = Applied Step |
| Model view | Front-end | Relationships, hide fields, data categories, hierarchies |
| Data (Table) view | Front-end | Inspect tables, calculated columns/measures, formats |
| Report view | Front-end | Visuals, pages, bookmarks |

## 2. Power Query (Part 3)

Power Query tabs: **Home** (Get data, Merge, Append, Group By, Parameters), **Transform** (modifies EXISTING columns), **Add Column** (CREATES new columns). `View > Layout` restores a missing formula bar / Query Settings.

**Generic load recipe:** `Home > Get data > Text/CSV` → pick file → **Transform Data** (not Load) → rename query in Query Settings → check Applied Steps (*Source, Promoted Headers, Changed Type*) and data types → `Home > Close & Apply`.

### 2.1 Table-by-table

| Query | Steps | Result check |
|---|---|---|
| **Territory Lookup** | Load; types: SalesTerritoryKey = Whole number; Region, Country, Continent = Text | 10 rows, 4 cols; Continents: North America (6 rows), Europe (FR, DE, UK), Pacific (Australia) |
| **Product Lookup** | Select ProductCost + ProductPrice → `Transform > Data Type > Fixed decimal number`; rename step `Change to currency` (delete any duplicate auto step); remove **ProductSize**; add **SKU Type**; replace 0 → NA in **ProductStyle** | 293 rows, 10 columns after ProductSize removed |
| **Product Categories Lookup** | Load; ProductCategoryKey = Whole number, CategoryName = Text | 4 rows |
| **Product Subcategories Lookup** | Load; ProductSubcategoryKey, ProductCategoryKey = Whole number, SubcategoryName = Text | 37 rows |
| **Customer Lookup** | 13 cols (CustomerKey, Prefix, FirstName, LastName, BirthDate, MaritalStatus, Gender, EmailAddress, AnnualIncome, TotalChildren, EducationLevel, Occupation, HomeOwner); profile; remove errors/empties in CustomerKey; add **Domain Name**, **Full Name** | 18,148 rows; CustomerKey 100% valid, Distinct = Unique = 18,148 |
| **Calendar Lookup** | One column `Date`; if errors: type icon > **Using Locale** > Date + English (United States); add 9 date columns | 912 rows, 1/1/2020–6/30/2022; 10 columns |
| **Sales Data** | Folder combine (see 2.3); add **Quantity Type** | 56,046 rows |
| **Returns Data** | Load; ReturnDate = Date (Using Locale if needed); TerritoryKey, ProductKey, ReturnQuantity = Whole number | 1,809 rows |

**SKU Type:** select ProductSKU → `Add Column > Extract > Text Before Delimiter`, delimiter `-`; rename column `SKU Type`; gear icon on the step → **Number of delimiters = 1** (stop at the second dash). Result: FR-R38B for FR-R38B-58; HL-U509 for HL-U509.

```
= Table.AddColumn(..., "Text Before Delimiter",
    each Text.BeforeDelimiter([ProductSKU], "-", 1), type text)
```

**ProductStyle:** select ONLY that column → `Transform > Replace Values`, find `0`, replace `NA`. Counts: U = 174, NA = 84, W = 28, M = 7 (total 293). (WATCH OUT: with several columns selected, the replacement runs on all.)

**Customer Lookup — Domain Name** (duplicate EmailAddress, rename `Domain Name`): `Transform > Extract > Text After Delimiter` `@` → `Text Before Delimiter` `.` → `Replace Values` `-` with a single space → `Format > Capitalize Each Word`. Result "Adventure Works" in all 18,148 rows.

**Customer Lookup — Full Name:** Capitalize Each Word on Prefix, FirstName, LastName; select them in that order (Prefix, FirstName, LastName) → `Add Column > Merge Columns` (NOT Transform > Merge, which replaces the originals), separator **Space**, name `Full Name`. Example: "Mr. Shannon Carlson".

**Calendar Lookup columns** (select `Date`, then `Add Column > Date`; rename and set types):

| Column | Path | Type |
|---|---|---|
| Day Name | Day > Name of Day | Text |
| Start of Week / End of Week | Week > Start of Week / End of Week | Date |
| Start of Month | Month > Start of Month | Date |
| Start of Quarter | Quarter > Start of Quarter | Date |
| Start of Year | Year > Start of Year | Date |
| Year | Year > Year | Whole number |
| Month Number | Month > Month | Whole number |
| Month Name | Month > Name of Month | Text |

Check: 7/1/2020 = Wednesday, Start of Week 6/28/2020, Start of Month 7/1/2020, Start of Quarter 7/1/2020, Start of Year 1/1/2020, Year 2020, Month Number 7, Month Name July.

### 2.2 Numerical tools exercise (then UNDO)

Statistics tools (Sum, Min, Max, Median, Average, Std Dev, Count Values, Count Distinct) return ONE value and replace the table — delete each Statistics step (red X) afterwards, or the model breaks. Answers: average ProductCost **$413.66**; distinct ProductColor **10** (Black, Blue, Grey, Multi, NA, Red, Silver, Silver/Black, White, Yellow); distinct CustomerKey **18,148**; max AnnualIncome **$170,000**.

### 2.3 Combine the Sales files from a Folder

`Home > Get data > More... > Folder` → Browse to `Sales Data` → OK → **Combine & Transform Data** → OK in Combine Files dialog (builds helper queries Sample File, Parameter, Transform File, Transform Sample File) → rename main query `Sales Data`. Types: Source.Name (Text); OrderDate, StockDate (Date); OrderNumber (Text); ProductKey, CustomerKey, TerritoryKey, OrderLineItem, OrderQuantity (Whole number). Fix date errors with Change Type with Locale (English (United States)). A new year file added to the folder is appended on refresh.

**Quantity Type** (`Add Column > Conditional Column`): If OrderQuantity = 1 → `Single Item`; Else If OrderQuantity > 1 → `Multiple Items`; Otherwise `Other`. Result: Single Item 31,421; Multiple Items 24,625 (total 56,046; max OrderQuantity 3).

### 2.4 Other Power Query tools (demos — not part of final numbers)

| Tool | How | Note |
|---|---|---|
| Index column | `Add Column > Index Column > From 1` | Unique row IDs; delete step if unneeded |
| Group By | Duplicate Sales Data → `Transform > Group By` ProductKey (+ CustomerKey via Advanced), `Total Quantity` = Sum of OrderQuantity | Fields not named are lost → always on a duplicate (`Sales Summary Demo`, Enable load OFF) |
| Unpivot | Select 3 region columns → `Transform > Unpivot Columns`; rename Attribute → `Region`, Value → `Sales` | 20 rows → 60 rows. Pivot reverse: Values = Sales, **Don't Aggregate**. Transpose ≠ pivot |
| Merge Queries | `Home > Merge Queries` on ProductKey with Product Lookup | Adds COLUMNS; redundant memory — prefer relationships; undo it |
| Append Queries | Stacks tables with identical structure | Adds ROWS |
| Rolling Calendar | Blank Query → `= #date(2023,1,1)`; fx step below; `List Tools > Transform > To Table`; rename column `Date`, type Date; add Month Name, Month Number, Start of Year, Year; group in `Demo` | If first step isn't named *Source*, use its real name |
| Parameters | `Home > Manage Parameters`: `Server` = 127.0.0.1, `Database` = mavenfuzzyfactory_development | One change switches servers |
| Database / Web demos | MySQL at 127.0.0.1 / `mavenfuzzyfactory_development`; web URL `https://en.wikipedia.org/wiki/List_of_asset_management_firms` (query `Largest Asset Management Firms`) | **Enable load OFF** on all demo queries |

```
= List.Dates(Source,
    Number.From(DateTime.LocalNow()) - Number.From(Source),
    #duration(1,0,0,0))
```

**Data profiling** (`View` tab: Column quality, Column distribution, Column profile; set status bar to **Column profiling based on entire data set**): Valid/Error/Empty %; Count, Distinct (different values), Unique (appear once), Min, Max.

**Storage modes:** Import (default; in memory, <1 GB, full features) · DirectQuery (stays in source) · Composite/Dual (mix) · Live Connection (published dataset). Project uses **Import**.

**Refresh control:** untick *Include in report refresh* for static lookups and Rolling Calendar; keep for Sales Data and Returns Data. `Home > Data source settings > Change Source` fixes moved files. `File > Import > Power Query, Power Pivot, Power View` imports Excel models.

### 2.5 Final load check

Eight tables loaded: Calendar Lookup 912 · Customer Lookup 18,148 · Product Lookup 293 · Product Categories Lookup 4 · Product Subcategories Lookup 37 · Territory Lookup 10 · Sales Data 56,046 · Returns Data 1,809. Demo queries (MySQL tables, web table, Sales Summary Demo) = Enable load OFF; Rolling Calendar and the unpivot demo are loaded then hidden in Model view.

## 3. Data Model (Part 4)

**Concepts:** *Fact tables* (numbers to add up): Sales Data, Returns Data. *Dimension/lookup tables* (descriptions): Calendar, Customer, Product, Territory, Categories, Subcategories. *Primary key* = unique value per row in a lookup (e.g. Product Lookup[ProductKey]); *foreign key* = same key repeated in a fact table. **Star schema** = fact table surrounded by dimensions; **snowflake** adds dimension-to-dimension links (Product → Subcategory → Category). Ideal cardinality is **one-to-many**; avoid many-to-many.

**Model view layout:** dimensions on TOP, fact tables at the BOTTOM (filters flow downward, one side → many side).

### 3.1 The 10 relationships

Create by dragging PK onto FK, or `Home > Manage relationships > New`. All must be **Many to one (\*:1)**, cross-filter **Single**.

| # | Many side (FK) | One side (PK) | Status |
|---|---|---|---|
| 1 | Sales Data[OrderDate] | Calendar Lookup[Date] | ACTIVE |
| 2 | Sales Data[StockDate] | Calendar Lookup[Date] | INACTIVE |
| 3 | Returns Data[ReturnDate] | Calendar Lookup[Date] | ACTIVE |
| 4 | Sales Data[CustomerKey] | Customer Lookup[CustomerKey] | ACTIVE |
| 5 | Sales Data[ProductKey] | Product Lookup[ProductKey] | ACTIVE |
| 6 | Returns Data[ProductKey] | Product Lookup[ProductKey] | ACTIVE |
| 7 | Sales Data[TerritoryKey] | Territory Lookup[SalesTerritoryKey] | ACTIVE |
| 8 | Returns Data[TerritoryKey] | Territory Lookup[SalesTerritoryKey] | ACTIVE |
| 9 | Product Lookup[ProductSubcategoryKey] | Product Subcategories Lookup[ProductSubcategoryKey] | ACTIVE (snowflake) |
| 10 | Product Subcategories Lookup[ProductCategoryKey] | Product Categories Lookup[ProductCategoryKey] | ACTIVE (snowflake) |

- Fact tables connect only through shared dimensions. **Returns Data has NO CustomerKey** → returns can be analysed by product, territory, date — not by customer.
- Relationship won't create → key columns have different data types; fix in Power Query.
- Only ONE Calendar relationship can be active; the StockDate one is created inactive (dashed). To switch, deactivate one first (*Make this relationship active*). An inactive relationship can be used in a measure with **USERELATIONSHIP**.
- Check star: Report view matrix with OrderQuantity in Values and one dimension field per test (Year, Full Name, ProductName, Country, CategoryName) — numbers must differ per row. No filter total = **84,174**. A repeated identical number means the field is from a fact table or the relationship is missing.

### 3.2 Filter flow and bi-directional filters

Filters flow ONE → MANY only (downstream). A filter on Territory Lookup reaches Sales and Returns; a filter on Sales Data[TerritoryKey] cannot reach Returns. **Always filter with dimension fields.** Cross-filter **Both** allows two-way flow but causes ambiguity — use only when necessary.

**Assignment 6 (product 338):** matrix with Product Lookup[ProductKey] in Rows, OrderQuantity + ReturnQuantity in Values. Temporarily set Returns Data → Product Lookup to **Both**: product 338 (**Road-650 Black, 44**, has sales but no returns) loses all its orders. Set back to **Single** immediately.

### 3.3 Model housekeeping

- **Hide in report view** (right-click, or *Is hidden* in Properties): Sales Data: ProductKey, CustomerKey, TerritoryKey, OrderDate, StockDate. Returns Data: ProductKey, TerritoryKey, ReturnDate. Recommended also: Product Lookup[ProductSubcategoryKey], Product Subcategories Lookup[ProductCategoryKey]; hide demo tables (Rolling Calendar, unpivot demo).
- **Model layouts** (bottom tabs, `+`): `Sales View`, `Returns View` — views only, no duplication.
- **Formats:** ProductCost, ProductPrice = Currency ($ English (United States)), 2 decimals; OrderQuantity, ReturnQuantity = Whole number + thousands separator. Territory Lookup: Continent → Data category **Continent**; Country → **Country/Region**; leave Region blank. Key/year/month-number columns: Summarization = **Don't summarize**.
- **Sort Month Name by Month Number** (`Column tools > Sort by column`).
- **Hierarchies:** *Territory Hierarchy* = Continent, Country, Region (right-click Continent > Create hierarchy, add the others). *Date Hierarchy* (Calendar Lookup) = Start of Year, Start of Month, Start of Week, Date (Start of Quarter may be added after Year).
- **Best practices:** normalized model; dimensions above facts; prefer 1-to-many and one-way filters; hide FKs.

**Part 4 checkpoint:** 8 working tables, 10 relationships (9 active, 1 inactive = StockDate), 2 hierarchies, FKs hidden, demo tables hidden.

## 4. DAX (Part 5)

DAX is the front-end formula language (not M). Syntax: `'Table Name'[Column]` for columns (quotes if a space); `[Measure]` for measures. DAX ignores case in names.

| | Calculated column | Measure |
|---|---|---|
| Evaluated | Per row (row context) | Per filter context in the visual |
| Stored | In the table (adds file size) | Not stored; calculated on the fly |
| Best for | Filtering / grouping | Aggregating (sum, count, rate) |

- Use **explicit measures** (written DAX), not implicit drag-and-drop sums. **Never use SUM/COUNT in a calculated column** (stamps the grand total on every row).
- **Filter context:** active filters from rows/columns, slicers, page/report filters. Each cell (including Grand Total) is evaluated independently — a total is NOT the sum of rows above. Steps: (1) filters detected; (2) flow downstream to related tables; (3) measure evaluated on the filtered table.
- **Measures Table:** `Home > Enter data`, name `Measures Table`, Load; hide empty Column1 (alternative: `Measures Table = { "" }`). Create each measure with the table selected: `Home > New measure` (Shift+Enter = new line).
- Operators: `+ - * / ^`; `= > < >= <= <>`; `&` (join text); `&&` AND; `||` OR; `IN { }`.
- Function families: Math/stats (SUM, AVERAGE, DIVIDE, COUNT, COUNTA, COUNTROWS, DISTINCTCOUNT); Logical (IF, IFERROR, AND, OR, SWITCH); Text (LEFT, MID, RIGHT, UPPER, LOWER, LEN, SEARCH, SUBSTITUTE, CONCATENATE); Filter (CALCULATE, FILTER, ALL, ALLEXCEPT, SELECTEDVALUE); Date (YEAR, MONTH, DAY, TODAY, NOW, WEEKDAY, WEEKNUM, EOMONTH, DATEDIFF); Time intelligence (DATESYTD/QTD/MTD, DATEADD, DATESBETWEEN, DATESINPERIOD); Relationship (RELATED, USERELATIONSHIP); Iterators (SUMX, AVERAGEX, COUNTX, MAXX, MINX, RANKX).
- COUNT = non-empty cells (excl. Boolean); COUNTA = incl. Boolean; DISTINCTCOUNT = distinct values; COUNTROWS = rows.

### 4.1 Calculated columns

```
-- Customer Lookup
Parent = IF ( 'Customer Lookup'[TotalChildren] > 0, "Yes", "No" )

Customer Priority =
IF ( 'Customer Lookup'[Parent] = "Yes" && 'Customer Lookup'[AnnualIncome] > 100000,
     "Priority", "Standard" )

Income Level =
SWITCH ( TRUE (),
    'Customer Lookup'[AnnualIncome] >= 150000, "Very High",
    'Customer Lookup'[AnnualIncome] >= 100000, "High",
    'Customer Lookup'[AnnualIncome] >= 50000, "Average",
    "Low" )

Education Category =
SWITCH ( 'Customer Lookup'[EducationLevel],
    "High School", "High School",
    "Partial High School", "High School",
    "Bachelors", "Undergrad",
    "Partial College", "Undergrad",
    "Graduate Degree", "Graduate",
    "Other" )

Birth Year = YEAR ( 'Customer Lookup'[BirthDate] )

-- Calendar Lookup
Month Short = UPPER ( LEFT ( 'Calendar Lookup'[Month Name], 3 ) )

-- Product Lookup
SKU Category =
LEFT ( 'Product Lookup'[ProductSKU],
       SEARCH ( "-", 'Product Lookup'[ProductSKU] ) - 1 )
```

Checks: Parent Yes **13,068** / No **5,080**. Priority **1,269**. Income Level: Very High **300**, High **1,843**, Average **8,201**, Low **7,804** (= 18,148); labels must be spelled exactly (used by donut/filters). Education: Undergrad 10,227 (Bachelors 5,261 + Partial College 4,966), High School 4,796 (3,241 + 1,555), Graduate 3,125. Birth Year: Data type Whole number, Format **General** (no thousands separator, e.g. 1966), Don't summarize. Month Short: JAN…DEC (build from Month Name, not Day Name). SKU Category: FR for FR-R38B-58, HL for HL-U509; BK 97 products, FR 77.

### 4.2 Core measures

```
Quantity Sold = SUM ( 'Sales Data'[OrderQuantity] )
Quantity Returned = SUM ( 'Returns Data'[ReturnQuantity] )
Total Returns = [Quantity Returned]
Total Orders = DISTINCTCOUNT ( 'Sales Data'[OrderNumber] )
Total Customers = DISTINCTCOUNT ( 'Sales Data'[CustomerKey] )
Return Rate = DIVIDE ( [Quantity Returned], [Quantity Sold] )
```

Formats: counts = Whole number + thousands separator; Return Rate = Percentage, 2 decimals. Use **DIVIDE** (blank instead of divide-by-zero error). Unfiltered: Quantity Sold **84,174**; Quantity Returned **1,828**; Total Orders **25,164**; Total Customers **17,416** (fewer than 18,148 since only buyers count); Return Rate **2.17%**.

### 4.3 CALCULATE, ALL, FILTER, RELATED, iterators

- **RELATED(column)** pulls a value from the ONE side into each MANY-side row (like VLOOKUP); needs row context (calculated column or iterator). Better nested in SUMX than creating extra columns.
- **CALCULATE(expression, filter…)** modifies filter context and overrides competing report filters; filters must be fixed values (not measures).
- **ALL(table or columns)** removes filters → fixed "% of total" denominator.
- **FILTER(table, condition)** returns a table; can reference measures; row-by-row so can be slow — use only when plain CALCULATE can't.
- **Iterators (X functions)** evaluate an expression per row then aggregate (like SUMPRODUCT).

```
Red Sales = CALCULATE ( [Quantity Sold], 'Product Lookup'[ProductColor] = "Red" )

Bike Returns = CALCULATE ( [Quantity Returned], 'Product Categories Lookup'[CategoryName] = "Bikes" )
Bike Sales   = CALCULATE ( [Quantity Sold],     'Product Categories Lookup'[CategoryName] = "Bikes" )
Bike Return Rate = DIVIDE ( [Bike Returns], [Bike Sales] )

All Returns = CALCULATE ( [Quantity Returned], ALL ( 'Returns Data' ) )
% of All Returns = DIVIDE ( [Quantity Returned], [All Returns] )

Average Retail Price = AVERAGE ( 'Product Lookup'[ProductPrice] )
Overall Average Price = CALCULATE ( [Average Retail Price], ALL ( 'Product Lookup' ) )
High Ticket Orders =
CALCULATE ( [Total Orders],
    FILTER ( 'Product Lookup', 'Product Lookup'[ProductPrice] > [Overall Average Price] ) )

Total Revenue =
SUMX ( 'Sales Data', 'Sales Data'[OrderQuantity] * RELATED ( 'Product Lookup'[ProductPrice] ) )
Total Cost =
SUMX ( 'Sales Data', 'Sales Data'[OrderQuantity] * RELATED ( 'Product Lookup'[ProductCost] ) )
Total Profit = [Total Revenue] - [Total Cost]
Average Revenue per Customer = DIVIDE ( [Total Revenue], [Total Customers] )
```

Checks: Red Sales = **4,011** on every row (CALCULATE overrides the row's colour). Orders by category: Accessories 16,983, Bikes 13,929, Clothing 6,976 add to 37,888 but Total = **25,164** (DISTINCTCOUNT: one order, e.g. SO74144, can contain a bike and a helmet). Bike Returns **429**, Bike Sales **13,929**, Bike Return Rate **3.08%** — returns volume rose but so did sales; the **rate** shows no concerning trend. % of All Returns: Accessories **61.82%**, Bikes **23.47%**, Clothing **14.72%**. Overall Average Price **$714.44**; High Ticket Orders **11,312**. Revenue **$24,914,567.18**; Cost **$14,456,871.39**; Profit **$10,457,695.79**; Avg Revenue per Customer **$1,430.56**; Profit by year 2020 **$2,601,602.73**, 2021 **$3,967,075.69**, 2022 **$3,889,017.38** (data ends June 30, 2022). Money measures = Currency ($), 2 decimals.

### 4.4 Time intelligence (needs a continuous Calendar related by date)

Templates: YTD `CALCULATE([M], DATESYTD(Calendar[Date]))` (DATESQTD / DATESMTD); previous period `DATEADD(Calendar[Date], -1, MONTH)`; running total `DATESINPERIOD(Calendar[Date], MAX(Calendar[Date]), -10, DAY)`; moving average = running total ÷ intervals.

```
Previous Month Returns = CALCULATE ( [Total Returns], DATEADD ( 'Calendar Lookup'[Date], -1, MONTH ) )
Previous Month Orders  = CALCULATE ( [Total Orders],  DATEADD ( 'Calendar Lookup'[Date], -1, MONTH ) )
Previous Month Profit  = CALCULATE ( [Total Profit],  DATEADD ( 'Calendar Lookup'[Date], -1, MONTH ) )
Previous Month Revenue = CALCULATE ( [Total Revenue], DATEADD ( 'Calendar Lookup'[Date], -1, MONTH ) )

Order Target   = [Previous Month Orders] * 1.1
Profit Target  = [Previous Month Profit] * 1.1
Revenue Target = [Previous Month Revenue] * 1.1

Order Target Gap   = [Total Orders]  - [Order Target]
Revenue Target Gap = [Total Revenue] - [Revenue Target]
Profit Target Gap  = [Total Profit]  - [Profit Target]

90-day Rolling Profit =
CALCULATE ( [Total Profit],
    DATESINPERIOD ( 'Calendar Lookup'[Date], MAX ( 'Calendar Lookup'[Date] ), -90, DAY ) )

YTD Revenue = CALCULATE ( [Total Revenue], DATESYTD ( 'Calendar Lookup'[Date] ) )
10 Day Rolling Revenue =
CALCULATE ( [Total Revenue],
    DATESINPERIOD ( 'Calendar Lookup'[Date], MAX ( 'Calendar Lookup'[Date] ), -10, DAY ) )
```

Formats: orders/returns measures and Order Target = Whole number; profit/revenue measures and targets = Currency. Gap < 0 = under target (used for conditional colours). Checks, June 2022: Total Orders **2,146**; Previous Month Orders **2,165**; Order Target **2,381.5**; Total Profit **$771,575.07**; Profit Target **$825,827.70** (May profit $750,752.46 × 1.1); Revenue Target **$1,945,273.69**; 90-day Rolling Profit at 6/30/2022 **$2,142,657.15**; YTD Revenue 2022 **$9,185,437.85**.

### 4.5 Top-customer measures (HASONEVALUE pattern — return a dash unless exactly one customer is in the filter)

```
Top Customer Name =
IF ( HASONEVALUE ( 'Customer Lookup'[CustomerKey] ), MAX ( 'Customer Lookup'[Full Name] ), "-" )
Top Customer Orders =
IF ( HASONEVALUE ( 'Customer Lookup'[CustomerKey] ), [Total Orders], "-" )
Top Customer Revenue =
IF ( HASONEVALUE ( 'Customer Lookup'[CustomerKey] ), [Total Revenue], "-" )
```

### 4.6 What-if parameter (Price Adjustment)

`Modeling > New parameter > Numeric range`: Name `Price Adjustment (%)`, Decimal number, Min **-1**, Max **1**, Increment **0.1**, Default **0**, Add slicer ON. Format the column as Percentage, 0 decimals.

```
Price Adjustment (%) Value = SELECTEDVALUE ( 'Price Adjustment (%)'[Price Adjustment (%)], 0 )
Adjusted Revenue = [Total Revenue] * ( 1 + [Price Adjustment (%) Value] )
Adjusted Profit  = [Adjusted Revenue] - [Total Cost]
```

Check: at 0% Adjusted Profit = Total Profit; at **+10%** Adjusted Revenue **$27,406,023.90**, Adjusted Profit **$12,949,152.51**.

### 4.7 DAX best practices

Calculated columns for filtering, measures for aggregating; explicit measures; fully qualified column references; push column calculations upstream; minimise expensive iterators (FILTER, SUMX on big tables). Optional: Display folders (Core, Returns, Time Intelligence).

## 5. Report Building (Part 6)

Canvas **1280 × 720** (`Format page > Canvas settings > Type 16:9`, `View > Page view = Fit to page`). Positions are **x, y** in px; sizes **width × height**; type exact values in `Format > General > Properties`. Fonts/colours are design choices (black nav bar and black rounded panels, white text, light teal/blue accent for big numbers); positions, fields, filters and settings are exact. **Name everything in the Selection pane** (`View > Selection pane`); Format Painter copies formatting.

**Design framework:** (1) define purpose, (2) choose metrics, (3) present effectively, (4) remove clutter, (5) layout focuses attention, (6) tell a story. Three key questions: what data type (time series, categorical, geospatial, hierarchical), what to communicate (comparison, composition, trend, top performers), who the user is (executives → KPIs first). Visual choice: compare = bar/column/matrix; trend = line/area/KPI; composition = donut/area/stacked; single number = card/KPI/gauge; location = map; detail = table/matrix; "why" = decomposition tree/key influencers/anomaly detection.

### 5.1 Pages

| # | Page | Type | Size |
|---|---|---|---|
| 1 | Exec Dashboard | Normal | 1280 × 720 |
| 2 | Map | Normal | 1280 × 720 |
| 3 | Product Detail | Drillthrough (ProductName) | 1280 × 720 |
| 4 | Customer Detail | Normal | 1280 × 720 |
| 5 | Category Tooltip | Tooltip (hidden) | 425 × 225 |
| 6 | Q & A | Normal (AI) | 1280 × 720 |
| 7 | Decomposition tree | Normal (AI) | 1280 × 720 |
| 8 | Key influencer | Normal (AI) | 1280 × 720 |

### 5.2 Fields parameters (`Modeling > New parameter > Fields`, slicer ON)

```
Customer Metric selection = {
    ("Total Customers", NAMEOF('Measures Table'[Total Customers]), 0),
    ("Revenue per Customer", NAMEOF('Measures Table'[Average Revenue per Customer]), 1)
}
Product Metric selection = {
    ("Orders", NAMEOF('Measures Table'[Total Orders]), 0),
    ("Revenue", NAMEOF('Measures Table'[Total Revenue]), 1),
    ("Profit", NAMEOF('Measures Table'[Total Profit]), 2),
    ("Returns", NAMEOF('Measures Table'[Total Returns]), 3),
    ("Return Rate", NAMEOF('Measures Table'[Return Rate]), 4)
}
```

Create Customer Metric (tick Total Customers, Average Revenue per Customer) on Customer Detail; Product Metric (tick the five measures) on Product Detail; edit labels as shown.

### 5.3 Navigation bar (build once on Exec Dashboard, group `Navigation`, paste to Map, Product Detail, Customer Detail)

| Object | x | y | Size | Notes |
|---|---|---|---|---|
| Left Nav Background (rectangle, black, no outline) | 0 | 0 | 59 × 720 | |
| AW Logo (image, scaling Normal; send to back) | 59 | 0 | 210 × 210 | |
| Dashboard button | 0 | 494 | 59 × 49 | Action: Page navigation → Exec Dashboard |
| Map button | 0 | 549 | 59 × 49 | → Map |
| Product button | 0 | 605 | 59 × 49 | → Product Detail |
| Customer button | 0 | 660 | 59 × 49 | → Customer Detail |
| Filter icon button | 0 | 55 | 59 × 50 | Action: bookmark Show slicer panel |
| Reset button (fill off) | 0 | 0 | 79 × 55 | Action: bookmark Clear Exec Filters; tooltip "Click to clear all the filters" |

Icons: `Format > Button > Style > Icon`, Shape **Custom**; Default = white icon (Dashboard_Icon, Map_Icon, Product_Icon, Customer_Icon); On hover and On press/Selected = the `_Blue` version.

### 5.4 Exec Dashboard

**KPI cards** (group cards `KPI values`, backgrounds `KPI Background`, both in `KPIs`): Card visuals at y 18, 210 × 147, x = **298 / 541 / 783 / 1026**, fields Total Revenue (name *Revenue*), Total Profit (*Profit*), Total Orders (*Orders*), Return Rate (*Return rate*). Callout value Segoe UI 38 Bold, display units Auto, 1 decimal; category label On, size 9 Bold white; Title and Background off. Backgrounds: rounded rectangles 186 × 108, black, no outline, sent to back, y 46, x = **310 / 553 / 795 / 1038**. Check: Revenue $24.9M, Profit $10.5M, Orders 25K, Return rate 2.17%.

| Visual | Position / size | Key settings |
|---|---|---|
| **Revenue Trending** line chart | x 79, y 176; 635 × 315 | X = Calendar Lookup[Start of Month] (single field, NOT the hierarchy); Y = Total Revenue; axis titles off; Zoom slider on; Analytics: Trend line on; title centred, Segoe UI Bold; tooltips Default. Forecast optional but **remove before anomaly detection** |
| **Orders by Category** clustered bar | x 728, y 176; 496 × 166 | Axis CategoryName; Values Total Orders; sort descending; data labels On, Outside end; axis titles off; Tooltip type Report page → *Category Tooltip*. Bars: Accessories 16,983 / Bikes 13,929 / Clothing 6,976 |
| **Monthly Revenue** KPI | x 124, y 524; 175 × 169 | Value Total Revenue; Trend axis Start of Month; Target Previous Month Revenue; Display units Millions |
| **Monthly Orders** KPI | x 322, y 524; 175 × 169 | Total Orders; Start of Month; Previous Month Orders; Thousands |
| **Monthly Returns** KPI | x 540, y 524; 175 × 169 | Total Returns; Start of Month; Previous Month Returns; units None; Direction = **Low is good**; Bad colour `#AB1818` |
| **Top 10 Products** matrix | x 783, y 342; 469 × 239 | Rows ProductName (name *Top 10 Products*); Values Total Orders (*Orders*), Total Revenue (*Revenue*), Return Rate (*Return%*); subtotals off; header centre; Orders = data bars (positive `#CCCCCC`, negative white); Return% = background gradient white → light accent; **Filter ProductName Top N = Top 10 by Total Orders**; sort Orders descending |
| Text boxes | `Most Ordered Product Type` x 778, y 586, 176 × 46; `Most Returned Product Type` x 1026, y 586, 185 × 46 | Background off |
| Cards | x 780, y 622, 229 × 45 and x 1026, y 621, 226 × 46 | Field SubcategoryName (First); label off; Segoe UI Bold 14 white; **Top N = Top 1** by Total Orders (left) / Total Returns (right). Result: Tires and Tubes (9,084 orders; 534 returned) |

KPI visuals: give each its own title (Monthly Revenue / Orders / Returns), title wrapping on, background on, border width 1, Goal text `Prev Month`.

**Filters pane levels:** visual · page · all pages · drillthrough. Types: Basic, Advanced (contains, is not blank, And/Or), **Top N** (Top/Bottom, number, **By value** measure, click *Apply filter*), Relative date. A visual-level filter can use a field not shown in the visual.

**Slicer panel** — group `Slicer panel`: rectangle x 0, y 0, 311 × 720 black; Year slicer (field Start of Year, List, header `Year`, x 16, y 72, 278 × 126, exclude Blank); Continent slicer (Territory Hierarchy Continent, header `Continent`, x 16, y 234, 278 × 126); left-arrow button 55 × 40 at x 243, y 6.

**Bookmarks** (`View > Bookmarks pane`) — set the visual state FIRST, then Add, then rename:

| Bookmark | State captured | Data | Used by |
|---|---|---|---|
| Hide slicer panel | Panel group hidden | **Untick Data** | Left-arrow button |
| Show slicer panel | Panel group visible | **Untick Data** | Filter icon button |
| Clear Exec Filters | All slicers/selections cleared | Data ticked | Reset button |

Finally hide the panel group in the Selection pane. Test with **Ctrl + click**. Button Action: Type = Bookmark.

**Edit interactions** (`Format > Edit interactions`): Revenue Trending line → bar chart **Filter**, three KPI visuals **None**. Top 10 matrix → line chart **Filter**; bar chart and both Top N cards **None**. (Defaults = cross-filtering; options Filter / Highlight / None.)

### 5.5 Category Tooltip page

`Format page > Canvas settings > Type = Tooltip` (425 × 225), hide the page. Multi-row card x 10, y 0, 140 × 225: Total Revenue, Total Profit, Total Orders, Total Returns, Return Rate (data labels 10; category labels 8 Bold white). Area chart x 150, y 0, 248 × 225: Axis Date Hierarchy (Start of Week level), Values Total Orders, title `Weekly Orders` size 8 centred. Hover over a bar to test.

### 5.6 Map page

Navigation pasted. Slicer: Continent, x 72, y 6, 1208 × 94, Horizontal, header off, items Bold. Map: x 93, y 100, 1187 × 593; Location = Country; Bubble size = Total Orders; Style **Dark canvas**; category labels On (background transparency ≈ 85%); title off. Country needs data category Country/Region; for drill use Territory Hierarchy as Location.

### 5.7 Product Detail page (drillthrough)

Drag Product Lookup[ProductName] into the **Drill through** well (Keep all filters optional; back button auto-added). Test: Exec Dashboard → right-click a product in Top 10 matrix → **Drill through > Product Detail**.

| Object | Position / size | Settings |
|---|---|---|
| Card *Selected Product* | x 78, y 46; 237 × 135 | ProductName (First), label off, Segoe UI Bold 25 white, black background; text box above `Selected Product` |
| Gauge Orders | x 350, y 29; 256 × 252 | Value Total Orders; Maximum **and** Target = Order Target; title *Monthly orders vs target* |
| Gauge Revenue | x 666, y 29; 256 × 252 | Total Revenue; Revenue Target; *Monthly Revenue vs target* |
| Gauge Profit | x 982, y 29; 256 × 252 | Total Profit; Profit Target; *Monthly Profit vs target* |
| Profit Trending line | x 331, y 251; 949 × 220 | Axis Date Hierarchy; Values Total Profit + Adjusted Profit; zoom slider, data labels, markers 3, legend on |
| Slicer Price Adjustment (%) | x 78, y 315; 237 × 155 | Reference starts at -30% |
| Returns Trending area | x 349, y 462; 571 × 238 | Axis Date Hierarchy (Start of Quarter level); Values Product Metric selection; zoom slider |
| Slicer Product Metric selection | x 78, y 470; 213 × 204 | Single select, Select all off |
| Smart narrative | x 971, y 518; 309 × 181 | See 6 |

Gauges: titles centred Segoe UI 12; each has visual filter **Start of Month Top N = Top 1 by Start of Month** (latest month); callout colour `fx > Rules`: red when the matching gap measure < 0, else grey.

### 5.8 Customer Detail page (build in this order)

| Object | Position / size | Settings |
|---|---|---|
| Card *Unique customers* | x 105, y 0; 150 × 151 | Total Customers; Segoe UI 38 Bold, 1 decimal; backing rounded rectangle 196 × 102 at x 82, y 27 |
| Card *Revenue per customer* | x 105, y 114; 150 × 151 | Average Revenue per Customer; backing rectangle 196 × 102 at x 82, y 151 |
| Tile slicer Customer Metric selection | x 312, y 0; 949 × 65 | Style Tile, Horizontal, header off, **Single select**, Select all off |
| Line chart *Total customers* | x 312, y 79; 949 × 221 | X = Date Hierarchy (opens at Start of Week); Y = Customer Metric selection; zoom slider; trend line (transparency 75%); axis titles off; title centred Segoe UI Bold 13. First/last weeks are partial weeks (look low). Drill arrows: up / single-down (drill mode) / forked (expand all down) |
| Donut *Orders by Income level* | x 63, y 266; 260 × 212 | Legend Income Level; Values Total Orders; detail labels Category, value, size 8, 1 decimal; legend off; filter **Income Level is not Very High** |
| Donut *Orders by Occupation* | x 64, y 488; 269 × 232 | Legend Occupation; **Top N = Top 3** by Total Orders (remove income filter). Top 3: Professional, Skilled Manual, Management |
| Table *Top 100 customers* | x 323, y 300; 446 × 396 | Columns CustomerKey (named *Top 100 customers*), Full Name, Total Orders (*Orders*), Total Revenue (*Revenue*); filter Full Name **Top N = Top 100 by Total Orders**; totals off; Orders data bars `#70BBFF`; Revenue gradient white → blue; sort Orders descending |
| Year slicer | x 827, y 300; 300 × 73 | Start of Year (Date Hierarchy); Style **Between**, Horizontal, header off, start 1/1/2020; exclude Blank |
| Text boxes + cards | Text `Top Customer (by Revenue):` x 785, y 372, 191 × 38 → Card Top Customer Name x 785, y 410, 476 × 67; Text `Orders:` x 785, y 496 → Card Top Customer Orders x 786, y 520, 164 × 94; Text `Revenue:` x 1049, y 496 → Card Top Customer Revenue x 1054, y 520, 181 × 94 | Cards Segoe UI Bold 30 white, dark background; **each card: visual filter Top N = Top 1 on CustomerKey by Total Revenue** |

**Trap:** Top N on *Full Name* can show a wrong person (same names) — always use **CustomerKey** plus the HASONEVALUE measures. Check: no filters → **Mr. Maurice Shan, 6 orders, $12,407.95**; Year slicer 2022 + Skilled Manual → **Ruben Suarez, $4,682.67** (≈ $4,683).

**Interactions:** Year slicer → **Filter** on all visuals; line chart → both donuts **Filter** (not Highlight); Top 100 table → line chart and both donuts **None**.

**Bookmarks/buttons:** bookmark `Customer insights` (filter e.g. Skilled Manual, 2022). Information button x 815, y 634; 358 × 85: Default text `Customer Insights from 2020 - 2022`, Selected text = your insight sentence, tooltip, Action bookmark *Customer insights*. Clear all filters → bookmark `Clear all customer Filters`; Reset button 100 × 40 at x 0, y 0, fill off, tooltip "Clear all customers filters click here". Alternative: `Insert > Buttons > Navigator > Page navigator`.

### 5.9 Optional extras

- **Custom visuals:** `Home > Get more visuals` (AppSource, account needed).
- **Row-level security:** `Modeling > Manage roles`; roles `Europe`, `North America`, `Pacific` on Territory Lookup with `[Continent] = "Europe"` etc.; test with `Modeling > View as`. Enforced only after publishing to Power BI Service.
- **Mobile layout:** `View > Mobile layout`. **Publish** button only previewed in the course.

**Visualization best practices:** answer the key questions first and sketch; most important KPIs top-left; remove clutter (axis titles, gridlines, unneeded legends); consistent fonts/colours/alignment; sparing, colour-blind-friendly conditional formatting; label titles, units and date range.

## 6. AI Visuals (Part 7)

| Visual / page | Setup |
|---|---|
| **Anomaly detection** (Exec Dashboard line chart) | Remove forecast first. Analytics pane > **Find anomalies > Add**; Sensitivity ≈ **79%**; band colour `#FBD111`; click an anomaly for AI explanation (*Explain by* subcategory, country). Needs: date X-axis, ≥ 4 points, ONE Y value, no legend/secondary axis, no forecast, no drill hierarchy |
| **Smart narrative** (Product Detail) | `Insert > Smart narrative` at x 971, y 518; 309 × 181; or right-click visual > Summarize. `+ Value` inserts dynamic values; date format `dddd, MMMM d, yyyy`; bold key numbers |
| **Q&A** (page `Q & A`) | `Insert > Q&A` at x 92, y 92; 697 × 462; ask `return rate by SKU category`; train with `Modeling > Q&A setup` synonyms / Teach Q&A; optional Matrix x 890, y 190 (CategoryName × Total Orders) |
| **Decomposition tree** (page `Decomposition tree`) | x 56, y 98; 994 × 485; Analyze Return Rate; Explain by CategoryName, SubcategoryName, ProductName; card Total Orders x 1036, y 142; 153 × 150; AI splits High value / Low value |
| **Key influencers** (page `Key influencer`) | Visual 1 x 10, y 0; 710 × 704: Analyze Customer Lookup[HomeOwner] (target **Y**), Explain by AnnualIncome, EducationLevel, Parent, MaritalStatus, Occupation. Visual 2 x 730, y 0; 550 × 704: Analyze ProductPrice, Explain by Sum of ProductCost (counting Absolute). Tabs: Key influencers, Top segments. Course illustration: parents ≈ 1.59× more likely to be homeowners; segment 93% vs 67.6% overall (your numbers depend on fields) |

## 7. Optimization (Part 8)

- **Optimize tab > Pause visuals:** edit fields without waiting; formatting blocked while paused; **Refresh visuals** to resume.
- **Presets:** *Interactivity* (default, Import mode) · *Query reduction* (DirectQuery; no cross-filter/highlight; Apply buttons) · *Customize*.
- **Apply all slicers button** (and clear all slicers button): one query run after several slicer changes.
- **Performance Analyzer:** `Optimize > Performance analyzer > Start recording` → Refresh visuals / interact → read **DAX query**, **Visual display**, **Other** (ms); long DAX query = heavy measure; Copy query / export JSON.
- **External tools:** DAX Studio, Tabular Editor, ALM Toolkit, Bravo (introduced only).
- Newer optional features (not needed): calculation groups, new Card visual, Button slicer, List slicer, Visual calculations, DAX query view / INFO.VIEW functions, TMDL view.
- Bonus project (Maven Market): repeat connect/shape → model → DAX → report.

## 8. Final Delivery

### 8.1 Checklist

1. Preview features on; Current File: no auto relationships, no auto date/time, English (United States).
2. Eight tables loaded with correct row counts; demo queries not loaded.
3. Product Lookup: currency types, ProductSize removed, SKU Type, ProductStyle 0 → NA.
4. Customer Lookup: errors removed; Full Name, Domain Name.
5. Calendar Lookup: Month Name, Month Number, Start of Year/Quarter/Month/Week, End of Week, Day Name, Year.
6. Sales Data from folder (56,046) + Quantity Type; Returns Data (1,809).
7. 10 relationships, StockDate inactive, fact-table keys hidden.
8. Territory Hierarchy, Date Hierarchy, data categories.
9. Measures Table with all measures; calculated columns in lookups.
10. Price Adjustment (%) parameter and two Fields parameters.
11. Exec Dashboard, Map, Product Detail, Customer Detail complete; Category Tooltip hidden.
12. Bookmarks, page navigation, drillthrough, slicer panel work (Ctrl + click).
13. AI pages added; Performance Analyzer run once.
14. Saved as `AdventureWorks.pbix`; screenshot of every page.

### 8.2 Numbers you should see (no filters unless stated)

| What | Expected |
|---|---|
| Rows: Calendar / Customer / Product / Categories / Subcategories / Territory | 912 / 18,148 / 293 / 4 / 37 / 10 |
| Rows: Sales Data / Returns Data | 56,046 (2,630 + 23,935 + 29,481) / 1,809 |
| Avg product cost; colours; distinct customers; max annual income | $413.66; 10; 18,148; $170,000 |
| Quantity Sold / Quantity Returned | 84,174 / 1,828 |
| Total Orders / Total Customers | 25,164 / 17,416 |
| Return Rate | 2.17% |
| Total Revenue / Cost / Profit | $24,914,567.18 / $14,456,871.39 / $10,457,695.79 |
| Average Revenue per Customer | $1,430.56 |
| Profit 2020 / 2021 / 2022 | $2,601,602.73 / $3,967,075.69 / $3,889,017.38 |
| Orders: Accessories / Bikes / Clothing (sum 37,888; total 25,164) | 16,983 / 13,929 / 6,976 |
| Bike Returns / Bike Sales / Bike Return Rate | 429 / 13,929 / 3.08% |
| % of All Returns: Accessories / Bikes / Clothing | 61.82% / 23.47% / 14.72% |
| Red Sales | 4,011 |
| Overall Average Price / High Ticket Orders | $714.44 / 11,312 |
| June 2022: Orders / Previous Month Orders / Order Target | 2,146 / 2,165 / 2,381.5 |
| June 2022: Profit / Profit Target / Revenue Target | $771,575.07 / $825,827.70 / $1,945,273.69 |
| 90-day Rolling Profit at 6/30/2022; YTD Revenue 2022 | $2,142,657.15; $9,185,437.85 |
| Adjusted Revenue / Profit at +10% | $27,406,023.90 / $12,949,152.51 |
| Income Level: Very High / High / Average / Low | 300 / 1,843 / 8,201 / 7,804 |
| Parents Yes / No; Priority customers | 13,068 / 5,080; 1,269 |
| Top customer (no filters) | Mr. Maurice Shan: 6 orders, $12,407.95 |
| Top customer, Skilled Manual, 2022 | Ruben Suarez, $4,682.67 |
| Most ordered / returned product type | Tires and Tubes (9,084 orders) / Tires and Tubes (534 returned) |
| Product 338 | Road-650 Black, 44; sales, no returns |

### 8.3 Common problems and fixes

| Problem | Fix |
|---|---|
| Date column shows errors | Change type using locale: Date, English (United States); check Regional Settings |
| Same number on every row | No relationship, or field is from the fact table — use the dimension field; check Model view |
| A product shows no sales | Bi-directional filter from Returns Data — set back to Single |
| Measure total ≠ sum of rows | Normal for DISTINCTCOUNT (an order can sit in several categories) |
| Time intelligence returns blanks | Calendar must be continuous and related to the fact date via Calendar Lookup[Date] |
| Cannot create a second active date relationship | Deactivate the first; USERELATIONSHIP in a measure |
| File path error after moving a CSV | `Home > Data source settings > Change source`, or use a parameter |
| Settings reset in a new file | Current File options don't carry over — redo Step 1.2 CURRENT FILE |
| Relationship won't create | Key columns have different data types — fix in Power Query |
| Anomaly detection missing | Remove forecast, legend, drill hierarchy; X-axis a date field with ≥ 4 points |
| Bookmark resets slicers | Untick Data in that bookmark's options |
| Top-customer card wrong | Top N on CustomerKey (not Full Name) + HASONEVALUE measures |
| Month Short shows MON/TUE | Built from Day Name — rebuild from Month Name |
