# AdventureWorks Power BI Project

Complete step-by-step guide: from raw CSV files to a finished, interactive dashboard

| Course parts covered | Content |
|---|---|
| Part 1-2 | Getting started, installing and configuring Power BI Desktop |
| Part 3 | Connecting and shaping data (Power Query) |
| Part 4 | Creating the data model |
| Part 5 | Calculated fields with DAX |
| Part 6 | Visualizing data with reports (dashboard, exact positions and settings) |
| Part 7-8 | AI visuals and optimization tools |
| Part 9 + Appendices | Final checklist, verified numbers, DAX, Power Query and layout references |

Follows the Udemy course **Microsoft Power BI Desktop for Business Intelligence** (Maven Analytics), lecture by lecture, with every number checked against the project data.

## Contents

- **How to Use This Guide** — p. 6
  - The story and the goal — p. 6
  - How every step is laid out — p. 6
  - Where the details in this guide come from — p. 6
  - Names used throughout this guide — p. 7
- **Part 1: Getting Started (Udemy Section 1)** — p. 8
  - Step 1.1 - Course structure and outline — p. 8
  - Step 1.2 - Download the course resources and create the project folder — p. 8
  - Step 1.3 - Introducing the AdventureWorks project — p. 9
  - Step 1.4 - Setting expectations — p. 9
- **Part 2: Introducing Power BI Desktop (Udemy Section 2)** — p. 10
  - Step 2.1 - Meet Power BI and Excel vs. Power BI — p. 10
  - Step 2.2 - Download and install Power BI Desktop — p. 10
  - Step 2.3 - Adjust the settings (do this carefully) — p. 11
  - Step 2.4 - The Power BI interface and workflow — p. 11
  - Step 2.5 - Helpful resources, ribbon update and publishing preview — p. 12
- **Part 3: Connecting & Shaping Data (Udemy Section 3)** — p. 13
  - Step 3.1 - Orientation: front-end vs back-end, connectors and the Query Editor — p. 13
  - Step 3.2 - Basic table transformations — p. 14
  - Step 3.3 - Load the Territory Lookup table — p. 14
  - Step 3.4 - Load and clean the Product Lookup table — p. 14
  - Step 3.5 - Assignment 1: Category and Subcategory tables, SKU Type, Product Style — p. 15
  - Step 3.6 - Storage and connection modes — p. 16
  - Step 3.7 - Connecting to a database (demonstration) — p. 16
  - Step 3.8 - Extracting data from the web (demonstration) — p. 17
  - Step 3.9 - Data profiling: column quality, distribution and profile — p. 17
  - Step 3.10 - Assignment 2: Text tools (Domain Name and Full Name) — p. 18
  - Step 3.11 - Assignment 3: Numerical tools (leadership statistics) — p. 19
  - Step 3.12 - Calendar Lookup: load it and fix dates with Change Type with Locale — p. 20
  - Step 3.13 - Assignment 4: Add the calendar columns — p. 20
  - Step 3.14 - Pro tip: Rolling Calendar — p. 21
  - Step 3.15 - Combine the three Sales files from a Folder — p. 22
  - Step 3.16 - Index and Conditional columns — p. 23
  - Step 3.17 - Group By and aggregation — p. 23
  - Step 3.18 - Pivoting and unpivoting — p. 24
  - Step 3.19 - Merging and appending queries — p. 24
  - Step 3.20 - Data source settings, parameters, refresh control and Excel model import — p. 25
  - Step 3.21 - Load Returns Data and run the final Power Query check — p. 26
- **Part 4: Creating a Data Model (Udemy Section 4)** — p. 27
  - Step 4.1 - Data modeling 101: normalization, facts, dimensions and keys — p. 27
  - Step 4.2 - Open Model view and arrange the tables — p. 27
  - Step 4.3 - Create the table relationships — p. 28
  - Step 4.4 - Active and inactive relationships — p. 29
  - Step 4.5 - Star and snowflake schemas: Assignment 5 (rebuild the model) — p. 29
  - Step 4.6 - Relationship cardinality — p. 30
  - Step 4.7 - Connecting multiple fact tables — p. 30
  - Step 4.8 - Filter context, filter flow and bi-directional filters — p. 30
  - Step 4.9 - Hide fields and Assignment 6 (the "rogue" matrix, product 338) — p. 31
  - Step 4.10 - Model layouts — p. 32
  - Step 4.11 - Data formats and data categories — p. 32
  - Step 4.12 - Hierarchies: Territory Hierarchy and Date Hierarchy (Assignment 7) — p. 33
  - Step 4.13 - Data model best practices and Part 4 checkpoint — p. 33
- **Part 5: Calculated Fields with DAX (Udemy Section 5)** — p. 34
  - Step 5.1 - Calculated columns vs. measures — p. 34
  - Step 5.2 - Create a dedicated Measures Table — p. 35
  - Step 5.3 - Filter context (understand this before writing measures) — p. 36
  - Step 5.4 - DAX syntax, operators and function categories — p. 36
  - Step 5.5 - Math and statistical measures (Assignment 8) — p. 37
  - Step 5.6 - Logical functions (Assignment 9) — p. 38
  - Step 5.7 - Text functions (Assignment 10) — p. 40
  - Step 5.8 - Date and time functions (Assignment 11) — p. 40
  - Step 5.9 - RELATED — p. 41
  - Step 5.10 - CALCULATE (demo and Assignment 12: bike returns) — p. 41
  - Step 5.11 - ALL (Assignment 13: percent of all returns) — p. 42
  - Step 5.12 - FILTER — p. 43
  - Step 5.13 - Iterators and Assignment 14: revenue, cost and profit — p. 44
  - Step 5.14 - Time intelligence (Assignment 15) — p. 45
  - Step 5.15 - Target gap measures (used by the gauges and KPI formatting) — p. 46
  - Step 5.16 - Customer Detail measures (accurate "top customer" cards) — p. 47
  - Step 5.17 - What-if numeric range parameter (Price Adjustment) — p. 48
  - Step 5.18 - DAX best practices and Part 5 checkpoint — p. 48
- **Part 6: Visualizing Data with Reports (Udemy Section 6)** — p. 50
  - Step 6.1 - Plan the dashboard: the three key questions and the design framework — p. 50
  - Step 6.2 - Report view tour and formatting basics — p. 51
  - Step 6.3 - Create the report pages — p. 51
  - Step 6.4 - Create the two Fields parameters (used by Product Detail and Customer Detail) — p. 52
  - Step 6.5 - Left navigation bar, logo and page buttons (repeat on every main page) — p. 53
  - Step 6.6 - Exec Dashboard: KPI cards — p. 53
  - Step 6.7 - Exec Dashboard: Revenue Trending line chart (trend line, zoom, forecast) — p. 55
  - Step 6.8 - Exec Dashboard: Orders by Category bar chart — p. 56
  - Step 6.9 - Exec Dashboard: three KPI visuals — p. 56
  - Step 6.10 - The Filters pane: visual, page and report level, and Top N — p. 57
  - Step 6.11 - Exec Dashboard: Top 10 Products matrix with conditional formatting — p. 58
  - Step 6.12 - Exec Dashboard: Most Ordered / Most Returned Product Type cards — p. 58
  - Step 6.13 - Exec Dashboard: slicer panel with bookmarks and buttons — p. 59
  - Step 6.14 - Exec Dashboard: report interactions — p. 60
  - Step 6.15 - Category Tooltip page — p. 60
  - Step 6.16 - Map page — p. 61
  - Step 6.17 - Product Detail page (drillthrough) — p. 62

Step 6.18 - Customer Detail page (Assignments: cards, line chart, donuts, table, top customer) .  . 63

  - Step 6.19 - Customer Detail: report interactions, bookmarks and buttons — p. 67
  - Step 6.20 - Optional: custom visuals, row-level security, mobile layout and publishing — p. 68
  - Step 6.21 - Visualization best practices and Part 6 checkpoint — p. 69
- **Part 7: Artificial Intelligence Visuals (Udemy Section 7)** — p. 70
  - Step 7.1 - Anomaly detection (Exec Dashboard line chart) — p. 70
  - Step 7.2 - Smart narrative (Product Detail page) — p. 70
  - Step 7.3 - Q&A; visual (page: Q & A) — p. 70
  - Step 7.4 - Decomposition tree (page: Decomposition tree) — p. 71
  - Step 7.5 - Key influencers (page: Key influencer) — p. 71
- **Part 8: Power BI Optimization Tools (Udemy Section 8)** — p. 73
  - Step 8.1 - Optimize ribbon and pause visuals — p. 73
  - Step 8.2 - Optimization presets — p. 73
  - Step 8.3 - Apply all slicers button — p. 73
  - Step 8.4 - Performance Analyzer — p. 73
  - Step 8.5 - External tools — p. 74
- **Part 9: Final Delivery and Reference** — p. 75
  - Step 9.1 - Bonus project: Maven Market (outline) — p. 75
  - Step 9.2 - Newer features (optional extras from the course update section) — p. 75
  - Step 9.3 - Final project checklist — p. 76
  - Step 9.4 - Verification table: numbers you should see — p. 76
  - Step 9.5 - Common problems and fixes — p. 78
- **Appendix A: DAX Quick Reference** — p. 79
- **Appendix B: Power Query Applied Steps Summary** — p. 81
- **Appendix C: Page Layout Reference (1280 x 720 canvas)** — p. 82

## How to Use This Guide

This guide takes you from a folder of raw CSV files to a finished, interactive Power BI dashboard, in the same order as the Udemy course **Microsoft Power BI Desktop for Business Intelligence** (Maven Analytics). The course has eight sections in its left-hand panel; this guide has eight matching Parts, and inside each Part the steps follow the lecture and assignment order of the course ebook.

### The story and the goal

You are a Business Intelligence Analyst at AdventureWorks, a global manufacturer of cycling equipment and accessories. Management needs to track sales, revenue, profit and returns, compare regions, study product trends and find high-value customers. All you are given is a folder of raw CSV files about transactions, returns, products, customers and sales territories. You will connect and clean the data, build a relational model, write DAX calculations, and design an interactive dashboard.

### How every step is laid out

| Element | What it means |
|---|---|
| Step heading | One task. Do the steps strictly in order; later steps depend on earlier ones. |
| Course topic | The lecture or assignment topic from the course that the step belongs to, so you can find the matching video. |
| Goal | What the step achieves and why. |
| Numbered actions | Exactly what to click or type. Menu paths are written like `Home > Get data` `> Text/CSV`. |
| Grey code box | Text to type exactly (DAX or Power Query M). Copy it as written. |
| CHECKPOINT (green) | What you must see on screen, with real numbers computed from the project data. If your screen differs, stop and fix it. |
| TIP (yellow) | A shortcut or best practice. |
| WATCH OUT (red) | A mistake that breaks something later. |

### Where the details in this guide come from

- **The course ebook** (210 pages): every lecture topic and every assignment, with its brief and solution.
- **A finished reference build** of the project (.pbix): the exact table names, column names, relationships, measures, visuals, fields, filters, formats, positions and sizes. Page layouts in Part 6 are given as exact pixel positions on the 1280 x 720 canvas.
- **Your own Power Query / Data Modeling notes**, merged in at the matching steps.
- **Verified numbers.** Every number in a CHECKPOINT was calculated directly from the project data, not copied from memory. Where the ebook states a number (for example 25,164 total orders) it matches.

> **NOTE:** This guide cannot reproduce the instructor's spoken explanations. Small visual choices that are purely cosmetic (an exact shade of a colour, a font weight) are marked as design choices. They never change any result, so you may adjust them. Formulas, field names, filters and settings are exact.

### Names used throughout this guide

Use these table names exactly. They match the CSV file names and the reference build, and every formula in this guide refers to them.

| Table (query) name | Source file | Role | Rows loaded |
|---|---|---|---|
| Calendar Lookup | AdventureWorks Calendar Lookup.csv | Dimension (dates) | 912 |
| Customer Lookup | AdventureWorks Customer Lookup.csv | Dimension | 18,148 |
| Product Lookup | AdventureWorks Product Lookup.csv | Dimension | 293 |
| Product Categories Lookup | AdventureWorks Product Categories Lookup.csv | Dimension (snowflake) | 4 |
| Product Subcategories Lookup | AdventureWorks Product Subcategories Lookup.csv | Dimension (snowflake) | 37 |
| Territory Lookup | AdventureWorks Territory Lookup.csv | Dimension | 10 |
| Sales Data | Three files in the Sales Data folder (2020, 2021, 2022) | Fact | 56,046 |
| Returns Data | AdventureWorks Returns Data.csv | Fact | 1,809 |
| Measures Table | Created inside Power BI (Part 5) | Holds all measures | - |

Demo-only queries (never part of the final report numbers): the MySQL tables, the web table, Rolling Calendar, and the Product Category Sales (Unpivot Demo) query.

## Part 1: Getting Started (Udemy Section 1)

Section 1 of the course is short (7 lectures): course structure, resources, the project brief and your expectations. The only hands-on work is setting up your folder, which prevents the most common problem later: broken file paths.

### Step 1.1 - Course structure and outline

*Course topic: Course Structure & Outline*

The course is project-based and has six working modules, which become Parts 2 to 7 of this guide.

| Ebook module | What you do | Guide Part |
|---|---|---|
| 1 Introducing Power BI Desktop | Install, adjust settings, learn the interface and workflow | Part 2 |
| 2 Connecting & Shaping Data | Connect to files, database and web; clean and shape tables in Power Query | Part 3 |
| 3 Creating a Data Model | Relationships, cardinality, filter flow, hierarchies | Part 4 |
| 4 Calculating Measures with DAX | Calculated columns, measures, iterators, time intelligence | Part 5 |
| 5 Visualizing Data with Dashboards | Build and format the report, filters, bookmarks, drillthrough | Part 6 |
| 6 Optimizing Power BI Performance | Optimize ribbon, Performance Analyzer, external tools | Part 8 |
| Artificial Intelligence visuals | Anomaly detection, smart narrative, Q&A, decomposition tree, key influencers | Part 7 |

### Step 1.2 - Download the course resources and create the project folder

*Course topic: DOWNLOAD: Course Resources*

**Goal:** keep every file in one stable folder. Power BI stores the full file path of every CSV, so a file that is renamed or moved later breaks the refresh.

1. Download the course resources from the first lecture and unzip them.
2. Create a main folder, for example `AdventureWorks Project`.
3. Inside it create a folder `Raw Data` and copy these seven CSV files into it (names must stay exactly as shown):
   - `AdventureWorks Calendar Lookup.csv`
   - `AdventureWorks Customer Lookup.csv`
   - `AdventureWorks Product Lookup.csv`
   - `AdventureWorks Product Categories Lookup.csv`
   - `AdventureWorks Product Subcategories Lookup.csv`
   - `AdventureWorks Territory Lookup.csv`
   - `AdventureWorks Returns Data.csv`
   - `Product Category Sales (Unpivot Demo).csv` (used only for a demo in Part 3)
1. Inside `Raw Data` create a subfolder named `Sales Data`. Put exactly three files in it: `AdventureWorks Sales Data 2020.csv`, `AdventureWorks Sales Data 2021.csv` and `AdventureWorks Sales Data 2022.csv`.
2. Create a folder `Images` and copy the AdventureWorks logo and the navigation icon images from the course resources into it.
3. You will save the Power BI file in the main folder. From now on, never rename or move any CSV.

> **CHECKPOINT:** The Sales Data folder contains exactly three files. Row counts you will see later: 2020 = 2,630 rows, 2021 = 23,935 rows, 2022 = 29,481 rows, total 56,046.

### Step 1.3 - Introducing the AdventureWorks project

*Course topic: Introducing the Adventure Works Project*

**The situation:** you have just been hired as a BI Analyst at AdventureWorks. **The brief:** management needs KPIs (sales, revenue, profit, returns), a regional comparison, product-level trends and a way to spot high-value customers, and all they gave you is raw CSV files. **The objective:** connect and transform the raw data, build a relational data model, create calculated columns and measures with DAX, and design an interactive dashboard.

### Step 1.4 - Setting expectations

*Course topic: Setting Expectations*

- Your screen may differ slightly from the course: Power BI is updated every month.
- Power BI Desktop runs only on Windows (not on Mac).
- The course builds foundations. It does not cover advanced M code, advanced DAX, R/Python visuals or Power BI Service.
- You learn by following every demo and doing every assignment.

## Part 2: Introducing Power BI Desktop (Udemy Section 2)

Section 2 has 7 lectures (about 19 minutes). You install Power BI Desktop, fix three important settings, and learn the four places where you will work.

### Step 2.1 - Meet Power BI and Excel vs. Power BI

*Course topic: Meet Power BI*

Microsoft Power BI is a self-service business intelligence platform with desktop and web applications for connecting, modeling and visualizing data. Excel and Power BI are built on the same analytics engines: Power Query for data transformation, the Data Model, and DAX. Power BI adds report-building and publishing tools on top. You can even import a finished Excel data model into Power BI (see Step 3.20).

| Excel | Power BI |
|---|---|
| Spreadsheets, A1 notation, cell formulas | Report view and interactive dashboards |
| PivotTables | Custom visuals |
| Power Query, Data Model, DAX | Power Query, Data Model, DAX (same engines) |
| - | Power BI Service for publishing and sharing |

### Step 2.2 - Download and install Power BI Desktop

*Course topic: Downloading Power BI & Adjusting Settings*

| Option | How | Notes |
|---|---|---|
| 1. Microsoft Store | Search "Power BI Desktop" in the Microsoft Store | Windows handles automatic updates; no administrator access needed |
| 2. Manual download | powerbi.microsoft.com/downloads | No automatic updates (you control the version); administrator access may be required |
| 3. Microsoft 365 | Included in some enterprise Microsoft 365 plans | Ask your administrator for access |

> **TIP:** You do NOT need a Power BI Pro account to use Power BI Desktop.

### Step 2.3 - Adjust the settings (do this carefully)

*Course topic: IMPORTANT: Regional Settings (and Power BI Settings)*

**Goal:** turn on the newest features once, and stop Power BI from creating wrong relationships and hidden date tables.

#### Part A - GLOBAL settings (once per computer)

1. Open Power BI Desktop. On the start screen choose **Blank report**.
2. Go to `File > Options and settings > Options`.
3. In the left list under **GLOBAL**, click **Preview features** and tick every available option. These change with each monthly release; enabling all keeps your screen close to the course.
4. Click **OK**. If Power BI asks to restart, restart it and open a blank report again.

#### Part B - CURRENT FILE settings (repeat for every new .pbix file)

1. Go to `File > Options and settings > Options` and scroll the left list down to **CURRENT FILE**.
2. Click **Data Load**. Under **Relationships** UNTICK both: *Update or delete relationships when refreshing data* and *Autodetect new relationships after data is loaded*.
3. On the same page, under **Time intelligence**, UNTICK *Auto date/time*.
4. Click **Regional Settings**. In **Locale for import** choose **English (United States)**.
5. Click **OK**.

> **WATCH OUT:** The CURRENT FILE options do not carry over to new files. Repeat Part B every time you start a new .pbix. English (United States) is used for all course datasets regardless of where you live; the dates in the CSV files are in month/day/year order.

> **NOTE:** Your own notes used United Kingdom as the locale. Use English (United States) for this project, because the CSV dates are month/day/year. If a date column shows errors later, Step 3.12 (Change Type with Locale) repairs it.

> **CHECKPOINT:** Under Data Load the two Relationship boxes and the Auto date/time box are empty, and Regional Settings shows English (United States).

### Step 2.4 - The Power BI interface and workflow

*Course topic: The Power BI Interface & Workflow*

1. Click `File > Save as` and save the file as `AdventureWorks.pbix` in your project folder. Save often from now on.
2. Look at the left edge of the window: the icons are **Report view**, **Table view** (also called Data view) and **Model view**. The Power Query Editor opens in a separate window from `Home > Transform data` (older versions call it Edit Queries).

| Where | Side | What you do there |
|---|---|---|
| Power Query Editor | Back-end | Connect to raw data, profile it, clean and shape it. Every action is recorded as an Applied Step. |
| Model view | Front-end | Create relationships, hide fields, set data categories, build hierarchies. |
| Data (Table) view | Front-end | Inspect loaded tables, add calculated columns and measures, set formats. |
| Report view | Front-end | Design visuals, pages, bookmarks and the dashboard. |

The workflow is always the same: **extract and transform** in Power Query, **load**, **model**, **calculate**, then **visualize**.

### Step 2.5 - Helpful resources, ribbon update and publishing preview

*Course topic: Helpful Resources; UPDATE: New Power BI Ribbon; PREVIEW: Publishing to Power BI Service*

- The **Help** tab holds documentation, training videos, sample files and links to blogs and communities (Microsoft Power BI blog, the Microsoft Power BI YouTube channel, Power BI user groups).
- Power BI is updated monthly. The Desktop release notes are on Microsoft Learn (Power BI > Fundamentals > "Desktop latest update").
- The newer ribbon groups tools differently; the tool names used in this guide still exist in every version. If a button is not where the guide says, use the search box at the top of the window.
- The **Publish** button on the Home tab sends the report to Power BI Service. The course only previews it; Power BI Service is not covered.

> **CHECKPOINT:** Part 2 done: Power BI Desktop installed, Preview features on, the three Current File options set, and AdventureWorks.pbix saved in your project folder.

## Part 3: Connecting & Shaping Data (Udemy Section 3)

This is the Power Query part: 35 lectures, about 3 hours 12 minutes. Rule of the course: do cleaning and column creation as close to the source as possible (in Power Query), because this makes reports faster. DAX comes later, for calculations that must react to report filters.

> **NOTE:** The ebook order of the later lectures is: Index, Conditional columns, Group By, Pivot/Unpivot, Merge, Append (with the Folder pro tip). This guide loads the Sales Data folder first (Step 3.15) because those demos need the Sales table.

### Step 3.1 - Orientation: front-end vs back-end, connectors and the Query Editor

*Course topic: Front-End vs. Back-End; Types of Data Connectors; Power Query Editor; Query Editing Tools*

Power BI has two environments. The **back-end** (Power Query Editor) extracts, profiles, transforms and loads data (ETL). The **front-end** (Data, Model and Report views) builds the model, adds DAX and designs reports.

Power BI can connect to almost anything: flat files and folders (csv, text, xlsx), databases (SQL, Access, Oracle, IBM, MySQL), Power Platform (datasets, dataflows, Dataverse), Azure services, online services (SharePoint, GitHub, Salesforce, Google Analytics), and others (web feeds, R scripts, Spark, Hadoop).

#### Parts of the Power Query Editor

| Part | What it is |
|---|---|
| Ribbon: Home tab | General settings and common table tools (Close & Apply, Get data, Merge, Append, Group By, Manage Parameters). |
| Ribbon: Transform tab | Tools that modify EXISTING columns (split, format, extract, replace, statistics, pivot, unpivot). |
| Ribbon: Add Column tab | Tools that CREATE new columns (conditional, index, date, text extract, merge columns). |
| Formula bar | Shows the M code of the selected step. |
| Queries pane (left) | List of all queries (tables). |
| Query Settings (right) | The query Name and the Applied Steps (like a recorded macro). |
| Table preview (centre) | The data after the selected step. |

If a screen shows the formula bar or Query Settings missing, turn them on in `View > Layout`.

### Step 3.2 - Basic table transformations

*Course topic: Basic Table Transformations*

- Sort values (A-Z, low-high) from the column header drop-down.
- Change data type (date, currency, text, whole number) from the icon in the column header or `Transform > Data Type`.
- **Use First Row as Headers** promotes the first row to column names (Power BI normally does this automatically for CSV files).
- Duplicate, move or rename columns from the right-click menu (double-click a header to rename).
- **Choose Columns** / **Remove Columns**; **Remove Other Columns** when you want only a few.
- **Keep Rows** / **Remove Rows** (top rows, duplicates, errors, blank rows).

> **TIP:** Right-click a column header for fast access to the common tools. Use Remove Duplicates to create a new lookup table from scratch.

### Step 3.3 - Load the Territory Lookup table

*Course topic: Connecting to flat files (your first query)*

1. Click `Home > Get data > Text/CSV`.
2. Browse to `Raw Data`, select `AdventureWorks Territory Lookup.csv` and click **Open**.
3. In the preview window click **Transform Data** (not Load). The Power Query Editor opens.
4. In Query Settings, change the **Name** from *AdventureWorks Territory Lookup* to `Territory Lookup` and press Enter.
5. Check the Applied Steps: *Source*, *Promoted Headers*, *Changed Type*. Confirm the data types: SalesTerritoryKey = Whole number; Region, Country, Continent = Text.
6. Click `Home > Close & Apply` (also available under `File`).

> **CHECKPOINT:** Territory Lookup has 10 rows and 4 columns (SalesTerritoryKey, Region, Country, Continent). Continents: North America (6 rows: 5 United States regions and Canada), Europe (France, Germany, United Kingdom), Pacific (Australia).

### Step 3.4 - Load and clean the Product Lookup table

*Course topic: Basic table transformations applied to Product Lookup*

1. `Home > Get data > Text/CSV` > select `AdventureWorks Product Lookup.csv` > **Transform Data**.
2. Rename the query to `Product Lookup`.
3. Select **ProductCost**, hold Ctrl and select **ProductPrice**. On the **Transform** tab click **Data Type** and choose **Fixed decimal number** (this is the currency type).
4. In Applied Steps, right-click the new step > **Rename** and call it `Change to currency`. If Power BI also created a separate automatic step that changed the same two columns, delete the extra step (click the red X next to it) so the same columns are not converted twice.
5. Right-click the **ProductSize** column header > **Remove**. (This column is not needed.)
6. Leave the query open for the next step. You will click Close & Apply after Step 3.5.

> **CHECKPOINT:** Product Lookup has 293 rows. ProductCost and ProductPrice show the currency type icon. ProductSize is gone (10 columns remain).

### Step 3.5 - Assignment 1: Category and Subcategory tables, SKU Type, Product Style

*Course topic: ASSIGNMENT: Table Transformations*

**Objectives:** (1) connect to the two new CSV files and name the queries Product Categories Lookup and Product Subcategories Lookup; (2) check headers and data types; (3) add a new column that extracts the characters before the dash in ProductSKU, called SKU Type; (4) change it to return everything before the SECOND dash; (5) replace zeros in Product Style with NA; (6) close and load.

#### Part A - Two new queries

1. `Home > Get data > Text/CSV` > `AdventureWorks Product Categories Lookup.csv` > Transform Data. Rename to `Product Categories Lookup`.
2. Repeat for `AdventureWorks Product Subcategories Lookup.csv` and rename it `Product Subcategories Lookup`.
3. Check the types. Categories: ProductCategoryKey = Whole number, CategoryName = Text. Subcategories: ProductSubcategoryKey = Whole number, SubcategoryName = Text, ProductCategoryKey = Whole number.

#### Part B - SKU Type column (in Product Lookup)

1. Click the `Product Lookup` query, then click the **ProductSKU** column header.
2. Click `Add Column > Extract > Text Before Delimiter`. In the dialog type `-` (a dash) as the delimiter and leave Scan for the delimiter at the default, then click OK.
3. Rename the new column from *Text Before Delimiter* to `SKU Type` (double-click its header).
4. In Applied Steps click the **gear icon** next to *Inserted Text Before Delimiter*. Change **Number of delimiters** from 0 to `1`. Click OK. A value of 1 means "skip one dash and stop at the second".

```
= Table.AddColumn(..., "Text Before Delimiter",
    each Text.BeforeDelimiter([ProductSKU], "-", 1), type text)
```

#### Part C - Product Style (replace 0 with NA)

1. Click the **ProductStyle** column header (select only this column).
2. `Transform > Replace Values`. **Value To Find:** `0`. **Replace With:** `NA`. Click OK.
3. Click `Home > Close & Apply`.

> **CHECKPOINT:** SKU Type shows FR-R38B for SKU FR-R38B-58 (everything before the second dash) and HL-U509 for HL-U509 (only one dash, so the whole value stays). ProductStyle counts: U = 174, NA = 84, W = 28, M = 7 (total 293). Categories has 4 rows, Subcategories 37 rows.

> **WATCH OUT:** Select ONLY ProductStyle before Replace Values. With several columns selected, the replacement runs on all of them.

### Step 3.6 - Storage and connection modes

*Course topic: PRO TIP: Storage & Connection Modes*

| Mode | What it means | Use it when |
|---|---|---|
| Import (default) | Tables are stored in memory inside Power BI; queries use cached data. | Dataset under 1 GB after compression, source rarely changes, no limits on Power Query, modeling or DAX. |
| DirectQuery | Tables stay in the source; queries run on demand at the source. | Data too large for memory, source changes often, or policy says data can only be accessed at the source. |
| Composite (Dual) | A mix of Import and DirectQuery tables. | You want to tune storage per table or combine DirectQuery models with imported data. |
| Live Connection | Connect to a published dataset in Power BI Service or Azure Analysis Services. | One central source of truth shared by many report authors. |

This project uses **Import** mode.

### Step 3.7 - Connecting to a database (demonstration)

*Course topic: Connecting to a Database*

This shows that Power Query reads databases (SQL Server, Access, MySQL, PostgreSQL, Oracle, SAP and more). It is NOT part of the final AdventureWorks model.

1. `Home > Get data > MySQL database` (any database connector works the same way).
2. **Server:** `127.0.0.1`. **Database:** `mavenfuzzyfactory_development`. Click OK. If asked, choose the Database tab and enter credentials.
3. In the Navigator tick the tables you want and click **Transform Data**.
4. In the Queries pane, right-click each database query and UNTICK **Enable load** so it is not loaded to the model.
5. (Optional) In the connection window, **Advanced options** lets you paste a SQL statement instead of picking tables.

> **WATCH OUT:** This needs a local MySQL server and the MySQL connector. If you do not have them, read this step and skip it; nothing later depends on it.

### Step 3.8 - Extracting data from the web (demonstration)

*Course topic: Extracting Data from the Web*

1. `Home > Get data > Web`. Paste the URL `https://en.wikipedia.org/wiki/List_of_asset_management_firms` and click OK.
2. In the Navigator click the table that Power Query detected, check the preview, then click **Transform Data**.
3. Rename the query `Largest Asset Management Firms` and check the data types.
4. Right-click the query and UNTICK **Enable load**.

> **TIP:** Wikipedia pages change. If the table layout differs, choose any table on the page; the technique is what is being demonstrated.

> **CHECKPOINT:** The Queries pane now lists the four AdventureWorks queries so far plus the demo queries from this step and Step 3.7, with load switched off on the demos.

### Step 3.9 - Data profiling: column quality, distribution and profile

*Course topic: Data Profiling: Column Quality; Column Distribution; Column Profile*

**Goal:** find errors, empty values and duplicates before they reach the model.

1. `Home > Get data > Text/CSV` > `AdventureWorks Customer Lookup.csv` > Transform Data. Rename the query `Customer Lookup`.
2. Confirm the 13 columns and types: CustomerKey (Whole number), Prefix, FirstName, LastName (Text), BirthDate (Date), MaritalStatus, Gender, EmailAddress (Text), AnnualIncome (Whole number), TotalChildren (Whole number), EducationLevel, Occupation, HomeOwner (Text).
3. Open the **View** tab and tick **Column quality**, **Column distribution** and **Column profile**.
4. By default profiling covers only the TOP 1,000 rows. In the bottom-left status bar click the text *Column profiling based on top 1000 rows* and choose **Column profiling based on entire data set**.
5. Read **Column quality** for CustomerKey: it shows the percent Valid, Error and Empty. Hover over the bar to see the record counts.
6. To find the problems, right-click the CustomerKey header > **Keep Errors** to inspect the error rows (then delete that step), and use **Remove Errors** to remove them.
7. Remove empty rows the same way: filter CustomerKey to remove *null* and empty values (or use the options menu on the column quality bar).
8. Click the **Column profile** of any column to see Count, Distinct, Unique, Min and Max.

| Term | Meaning |
|---|---|
| Valid / Error / Empty | Column quality: percent of values that are fine, produce an error, or are blank. |
| Column distribution | Shape of the values, and the number of distinct and unique values. |
| Count | Total number of values in the column. |
| Distinct | Number of different values, whether they appear once or many times. |
| Unique | Number of values that appear exactly once. |
| Min and Max | Lowest and highest value (useful for numbers). |

> **CHECKPOINT:** After removing errors and empties, Customer Lookup has 18,148 rows; CustomerKey is 100% valid and Distinct = Unique = 18,148.

### Step 3.10 - Assignment 2: Text tools (Domain Name and Full Name)

*Course topic: Text Tools; ASSIGNMENT: Text Tools*

Text tools sit on both the **Transform** tab (they OVERWRITE the selected column) and the **Add Column** tab (they ADD a new column). Tools: Split Column (by delimiter or number of characters), Format (lowercase, UPPERCASE, Capitalize Each Word, Trim, Clean, Add Prefix/Suffix) and Extract (length, first/last characters, range, text before/after/between delimiters). Trim removes leading and trailing spaces; Clean removes non-printing characters.

**Objectives:** duplicate the email column and name it Domain Name; remove everything except the domain name; clean and capitalize it (for example "Adventure Works"); save and apply.

#### Part A - Domain Name

1. In Customer Lookup right-click the **EmailAddress** header > **Duplicate Column**. Double-click the new header *EmailAddress - Copy* and rename it `Domain Name`.
2. With Domain Name selected: `Transform > Extract > Text After Delimiter`, delimiter `@`, OK. (Example: jon24@adventure-works.com becomes adventure-works.com.)
3. `Transform > Extract > Text Before Delimiter`, delimiter `.` (a full stop), OK. (Result: adventure-works.)
4. `Transform > Replace Values`: Value To Find `-` (hyphen), Replace With a single space. (Result: adventure works.)
5. `Transform > Format > Capitalize Each Word`. (Result: Adventure Works.)

#### Part B - Clean the name columns and create Full Name (needed later on the Customer Detail page)

1. Select **Prefix**, **FirstName** and **LastName** and apply `Transform > Format > Capitalize Each Word`.
2. Now select Prefix, FirstName and LastName in that exact order (click Prefix, then Ctrl+click FirstName, then Ctrl+click LastName).
3. `Add Column > Merge Columns`. **Separator:** Space. **New column name:** `Full Name`. Click OK. (The original three columns are kept: choose to keep them by using Add Column > Merge Columns, not Transform > Merge Columns.)
4. `Home > Close & Apply`.

> **CHECKPOINT:** Domain Name shows "Adventure Works" in all 18,148 rows. Full Name shows values such as "Mr. Shannon Carlson".

> **WATCH OUT:** Use **Add Column > Merge Columns** (creates a new column). **Transform > Merge Columns** replaces the original three columns.

### Step 3.11 - Assignment 3: Numerical tools (leadership statistics)

*Course topic: Numerical Tools; ASSIGNMENT: Numerical Tools*

The **Statistics** tools (Sum, Min, Max, Median, Average, Standard Deviation, Count Values, Count Distinct Values) return ONE value and replace the whole table, so they are used to explore a table, not to prepare it. The **Standard** (add, multiply, divide), **Scientific** (power, logarithm), **Trigonometry** (sine, tangent), **Rounding** and **Information** tools (flags such as even, odd, positive, negative) apply to EVERY row. Use the Add Column tab if you want a new column.

Answer four questions for leadership, then return the tables to their original state:

| Question | How | Answer |
|---|---|---|
| Average product cost | Product Lookup > select ProductCost > `Transform >` `Statistics > Average` | $413.66 |
| Number of colours sold | Product Lookup > ProductColor > `Statistics >` `Count Distinct Values` | 10 |
| Distinct customers | Customer Lookup > CustomerKey > `Statistics >` `Count Distinct Values` | 18,148 |
| Maximum annual income | Customer Lookup > AnnualIncome > `Statistics >` `Maximum` | $170,000 |

1. Do each calculation and write the answer down.
2. After each one, in Applied Steps click the **red X** next to the Statistics step to delete it, then check the full table is back.
3. Click Close & Apply only after all four steps are deleted.

> **CHECKPOINT:** Product Lookup is back to 293 rows and Customer Lookup to 18,148 rows. The 10 colours are Black, Blue, Grey, Multi, NA, Red, Silver, Silver/Black, White, Yellow.

> **WATCH OUT:** If you forget to delete a Statistics step, the table becomes a single number and the model breaks.

### Step 3.12 - Calendar Lookup: load it and fix dates with Change Type with Locale

*Course topic: Date & Time Tools; Creating a Calendar Table; Change Type with Locale*

1. `Home > Get data > Text/CSV` > `AdventureWorks Calendar Lookup.csv` > Transform Data. Rename the query `Calendar Lookup`. The table has one column: Date.
2. If the Date column shows errors or a wrong icon: click the data type icon at the left of the Date header > **Using Locale**.
3. In the dialog set **Data Type = Date** and **Locale = English (United States)**. Click OK.
4. Confirm a calendar icon next to the column name and zero errors.

> **CHECKPOINT:** Calendar Lookup has 912 rows, dates 1/1/2020 through 6/30/2022, no errors.

### Step 3.13 - Assignment 4: Add the calendar columns

*Course topic: Date & Time Tools; ASSIGNMENT: Calendar Tables*

Date & time tools: **Age** (difference between today and each date), **Date Only**, **Year / Month / Quarter / Week / Day** (extract components), and **Earliest / Latest** (Transform menu only, return one value). You will almost always use them from the **Add Column** menu to build new fields.

1. Select the **Date** column. Use `Add Column > Date` to create these columns (one at a time, re-selecting Date each time):

| New column name | Menu path | Type |
|---|---|---|
| Day Name | `Add Column > Date > Day > Name of Day` | Text |
| Start of Week | `Date > Week > Start of Week` | Date |
| End of Week | `Date > Week > End of Week` | Date |
| Start of Month | `Date > Month > Start of Month` | Date |
| Start of Quarter | `Date > Quarter > Start of Quarter` | Date |
| Start of Year | `Date > Year > Start of Year` | Date |
| Year | `Date > Year > Year` | Whole number |
| Month Number | `Date > Month > Month` | Whole number |
| Month Name | `Date > Month > Name of Month` | Text |

1. Rename each new column to the name in the first column (double-click the header). Assignment 4 requires exactly Month Name (for example January), Month Number (1), Start of Year (1/1/2020) and Year (2020).
2. Set the type of each column as shown in the table (Start of Year / Month / Week / Quarter / End of Week as Date; Year and Month Number as Whole number).
3. Optional: reorder columns by dragging headers so that Date, Day Name, Start of Year, Start of Week, End of Week, Start of Month, Start of Quarter, Year, Month Number, Month Name appear in that order.
4. `Home > Close & Apply`.

> **CHECKPOINT:** Calendar Lookup has 10 columns and no errors. For 7/1/2020 you see Wednesday, Start of Week 6/28/2020, Start of Month 7/1/2020, Start of Quarter 7/1/2020, Start of Year 1/1/2020, Year 2020, Month Number 7, Month Name July.

> **TIP:** Pro tip from the course: load a table that has a single date column, and use the Date tools to build out an entire calendar table.

### Step 3.14 - Pro tip: Rolling Calendar

*Course topic: PRO TIP: Rolling Calendars*

**Goal:** a calendar that grows automatically up to today. This is a demonstration table; it is hidden in the model later.

1. In Power Query: `Home > New Source > Blank Query`. Rename the query `Rolling Calendar`.
2. In the formula bar replace the contents with a start date literal (year, month, day) and press Enter:

```
= #date(2023,1,1)
```

1. Click the **fx** button next to the formula bar to add a custom step, and enter:

```
= List.Dates(Source,
    Number.From(DateTime.LocalNow()) - Number.From(Source),
    #duration(1,0,0,0))
```

1. Go to `List Tools > Transform > To Table` and accept the defaults.
2. Rename the column from *Column1* to `Date` and set its type to **Date**.
3. Add columns with the Add Column tools: **Month Name**, **Month Number**, **Start of Year** and **Year**.
4. Select Rolling Calendar (and any other practice queries), right-click > **Move to Group > New Group** and name the group `Demo` to keep the Queries pane tidy.

> **WATCH OUT:** If the first Applied Step of your blank query is not called *Source* (common for non-US regional settings), use that step name inside the List.Dates formula.

> **CHECKPOINT:** Rolling Calendar starts at 1/1/2023 and ends today, with the five columns Date, Month Name, Month Number, Start of Year, Year. Applied Steps: Source, Custom1, Converted to Table, Renamed Columns, Changed Type, and the added columns.

### Step 3.15 - Combine the three Sales files from a Folder

*Course topic: PRO TIP: Appending Files from a Folder*

**Goal:** combine the yearly sales files into one table automatically. When a new year file is added later, a refresh appends it.

1. `Home > Get data > More... > Folder` > Connect.
2. Click **Browse**, choose the `Sales Data` folder, click OK, then OK again.
3. In the preview of the three files click **Combine & Transform Data**.
4. In the Combine Files dialog the first file is the sample file. Click OK. Power Query builds helper queries (Sample File, Parameter, Transform File, Transform Sample File) in a group named Helper Queries and one main query.
5. Rename the main query to `Sales Data`.
6. Check the columns and types: Source.Name (Text), OrderDate (Date), StockDate (Date), OrderNumber (Text), ProductKey, CustomerKey, TerritoryKey, OrderLineItem, OrderQuantity (all Whole number).
7. If a date column shows errors, use Change Type with Locale (Step 3.12) with English (United States).

> **CHECKPOINT:** Sales Data shows 56,046 rows: click the Source.Name column profile to see 2020 = 2,630, 2021 = 23,935 and 2022 = 29,481.

> **TIP:** The Source.Name column records which file each row came from. You may keep it. It is harmless.

### Step 3.16 - Index and Conditional columns

*Course topic: Index Columns; Conditional Columns; Calculated Column Best Practices*

#### Index column (demo)

1. Select Sales Data. `Add Column > Index Column > From 1`. Look at how each row is numbered (index columns create unique row IDs, which can be used to form relationships).
2. Delete the Index step (red X in Applied Steps) unless you need unique row IDs. You do not need it in this project.

#### Conditional column

1. `Add Column > Conditional Column`. **New column name:** `Quantity Type`.
2. Rule 1: If **OrderQuantity** equals `1` then `Single Item`. Click **Add Clause**.
3. Rule 2: Else If **OrderQuantity** is greater than `1` then `Multiple Items`.
4. **Otherwise:** `Other`. Click OK.

> **CHECKPOINT:** Quantity Type shows Single Item in 31,421 rows and Multiple Items in 24,625 rows (total 56,046). The largest OrderQuantity is 3.

> **NOTE:** Best practice: table transformations and column calculations should ideally happen as close to the original data source as possible (data source, then Power Query, then Power BI front-end, then published reports). It is not a strict rule, so the course practises both Power Query columns and DAX columns.

### Step 3.17 - Group By and aggregation

*Course topic: Grouping & Aggregating*

Group By changes the grain of a table (for example daily records into monthly, or transactions into a per-product summary). **Fields that are not named in the Group By settings are lost**, so always do it on a duplicate query.

1. Right-click **Sales Data** in the Queries pane > **Duplicate**. Rename the copy `Sales Summary Demo`.
2. `Transform > Group By`. **Group by:** ProductKey. **New column name:** `Total Quantity`. **Operation:** Sum. **Column:** OrderQuantity. OK.
3. Click the gear icon on the Grouped Rows step, choose **Advanced**, click **Add grouping** and add **CustomerKey** as a second grouping column. This is like a PivotTable with Product and Customer as row labels and Sum of Order Quantity as the value.
4. Right-click the query > UNTICK **Enable load** and move it to the Demo group.

> **CHECKPOINT:** Sales Summary Demo has three columns: ProductKey, CustomerKey, Total Quantity. Sales Data itself still has all its rows and columns.

### Step 3.18 - Pivoting and unpivoting

*Course topic: Pivoting & Unpivoting*

Pivoting turns distinct row values into columns; unpivoting turns columns into rows (imagine the table on a hinge). **Transpose** is different: it flips the whole table (every row becomes a column) without recognizing unique values.

1. `Home > Get data > Text/CSV` > `Product Category Sales (Unpivot Demo).csv` > Transform Data. The columns are Date, Product Category, North Region, Central Region, South Region (20 rows).
2. Select the three region columns (**North Region, Central Region, South Region**).
3. `Transform > Unpivot Columns`. The three columns become rows.
4. Rename **Attribute** to `Region` and **Value** to `Sales`.
5. To see the reverse: select **Region**, `Transform > Pivot Column`, **Values Column = Sales**, expand Advanced options and choose **Don't Aggregate**. Then delete the Pivot step so the table is unpivoted again.
6. Right-click the query > UNTICK **Enable load** and move it to the Demo group.

> **CHECKPOINT:** After unpivoting the table has 60 rows (20 x 3) and the columns Date, Product Category, Region, Sales.

### Step 3.19 - Merging and appending queries

*Course topic: Merging Queries; Appending Queries*

#### Merge (demo, then undo)

1. Select **Sales Data**. `Home > Merge Queries`. In the dialog select ProductKey in Sales Data, choose **Product Lookup** as the second table and select ProductKey there, then OK.
2. Click the expand icon on the new column to see the Product fields added to every sales row.
3. Then undo it: delete the merge steps in Applied Steps so Sales Data returns to its original shape.

> **WATCH OUT:** Just because you can merge tables does not mean you should. A merged table repeats product attributes in every sales row (redundant data, more memory). Relationships in the data model (Part 4) are lighter and faster.

#### Append (explained)

**Append Queries** (`Home > Append Queries`) stacks tables that have identical column structure and data types. Merging adds COLUMNS to a table; appending adds ROWS. For example, appending the 2020 sales file to the 2021 file is valid because both have identical structures. Your Folder connection in Step 3.15 already appends all three years at once.

### Step 3.20 - Data source settings, parameters, refresh control and Excel model import

*Course topic: Data Source Settings; PRO TIP: Data Source Parameters; Refreshing Queries; PRO TIP: Importing Excel Models*

#### Data source settings

`Home > Data source settings` lets you manage existing connections, file paths and permissions. Local files use the exact path, so if a file name or location changes, update it here (select the source > Change Source).

#### Parameters (pro tip)

1. `Home > Manage Parameters > New Parameter`. Create `Server` (Type Text, Current Value 127.0.0.1) and `Database` (Type Text, Current Value mavenfuzzyfactory_development).
2. In a MySQL query's Source step, replace the typed server and database text with the parameter names.
3. Now a single change to the parameter switches between development and production servers.

#### Refresh control

1. By default every query refreshes when you click Refresh on the Home tab.
2. Right-click each lookup query and the Rolling Calendar and UNTICK **Include in report refresh**. Keep it ticked only for Sales Data and Returns Data, the tables that change.

#### Import Excel models

`File > Import > Power Query, Power Pivot, Power View` (older versions: Excel Workbook Contents) brings in a finished Excel model: data connections, applied steps, relationships, hierarchies, field settings, calculated columns and DAX measures.

#### Power Query best practices

- Get organized before connecting: clear table and query names, and a stable folder structure.
- Disable report refresh for static sources (lookups).
- When working with large tables, load only the data you need (do not include hourly data when you need daily).

### Step 3.21 - Load Returns Data and run the final Power Query check

*Course topic: Finishing the query layer*

1. `Home > Get data > Text/CSV` > `AdventureWorks Returns Data.csv` > Transform Data. Rename to `Returns Data`.
2. Check types: ReturnDate (Date, use Using Locale if needed), TerritoryKey, ProductKey, ReturnQuantity (Whole number).
3. Go through the Queries pane and compare it with the table below. Anything marked No must have **Enable load** unticked (right-click > Enable load).
4. `Home > Close & Apply`. Save the file.

| Query | Loaded to model | Key work done |
|---|---|---|
| Calendar Lookup | Yes | Date columns incl. Start of Week/Month/Quarter/Year, Year, Month Number, Month Name |
| Customer Lookup | Yes | Errors/empties removed; Full Name, Domain Name; capitalized names |
| Product Lookup | Yes | Currency types, ProductSize removed, SKU Type, ProductStyle zeros replaced with NA |
| Product Categories Lookup | Yes | - |
| Product Subcategories Lookup | Yes | - |
| Territory Lookup | Yes | - |
| Sales Data | Yes | Folder combine; Quantity Type |
| Returns Data | Yes | - |
| Rolling Calendar, unpivot demo | Loaded for practice, then HIDDEN in Model view (Step 4.9) | Demonstrations only |
| MySQL tables, web table, Sales Summary Demo | No (Enable load off) | Demonstrations only |

> **CHECKPOINT:** Eight working tables are loaded: Calendar Lookup 912, Customer Lookup 18,148, Product Lookup 293, Product Categories Lookup 4, Product Subcategories Lookup 37, Territory Lookup 10, Sales Data 56,046, Returns Data 1,809 rows.

## Part 4: Creating a Data Model (Udemy Section 4)

This part has 26 lectures (about 1 hour 44 minutes). A data model is a set of tables connected by relationships, so that a filter on one table (for example Product Color) correctly filters the others (Sales and Returns). Without relationships you only have a pile of separate tables.

### Step 4.1 - Data modeling 101: normalization, facts, dimensions and keys

*Course topic: What Is a Data Model?; Database Normalization; Fact & Dimension Tables; Primary & Foreign Keys; Relationships vs. Merged Tables*

| Idea | Meaning in this project |
|---|---|
| Normalization | Organizing tables so each has one clear purpose (product details in one table, transactions in another). It removes redundant data, shrinks tables, reduces errors and simplifies queries. |
| Fact table | Holds the numbers to add up: **Sales Data** and **Returns Data**. |
| Dimension (lookup) table | Holds descriptions used to filter or group: Calendar, Customer, Product, Territory, Categories, Subcategories. |
| Primary key (PK) | A column with ONE unique value per row in a lookup table, for example Product Lookup[ProductKey]. |
| Foreign key (FK) | A column in a fact table that repeats those keys, for example Sales Data[ProductKey]. |
| Cardinality | Ideally one-to-many: one instance of each key in the lookup, many in the fact table. |
| Star schema | One fact table surrounded by dimension tables (simplest and most common). |
| Snowflake schema | A star plus relationships between dimension tables and sub-dimension tables (Product, Subcategory, Category). |

Can you not just merge everything into one big table? You can, but it is very inefficient: merging creates redundancy and usually needs far more memory and processing than a relational model of several small tables.

### Step 4.2 - Open Model view and arrange the tables

*Course topic: The Model View*

1. Click the **Model view** icon (left edge). Parts of the screen: ribbon (Home, Help), the Data/Field list, the model canvas, the model layout tabs at the bottom, the Properties pane (name, synonyms, format) and View options (zoom, reset layout, fit to page).
2. Drag the dimension tables (Calendar, Customer, Product, Territory, Categories, Subcategories) to the TOP and the fact tables (Sales Data, Returns Data) to the BOTTOM. This is a visual reminder that filters flow downward, from the one side to the many side.
3. Click `Home > Manage relationships` and confirm there are none yet (auto-detect was switched off in Step 2.3).

### Step 4.3 - Create the table relationships

*Course topic: Creating Table Relationships; Managing & Editing Relationships*

**Option 1:** drag the primary key column from the dimension table onto the matching foreign key column in the fact table. **Option 2:** `Home > Manage relationships > New`, choose the two tables and columns. Double-click any relationship line to edit it.

Create these ten relationships. Every one must show **Many to one (\*:1)** and **Single** cross-filter direction.

| # | Many side (foreign key) | One side (primary key) | Status |
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

> **WATCH OUT:** Fact tables connect only through shared dimension tables, never directly to each other. There is NO CustomerKey in Returns Data, so you can analyze returns by product, territory or date, but not by customer.

> **WATCH OUT:** If a relationship will not create, a key column probably has a different data type on each side (for example text vs whole number). Fix the type in Power Query, then retry.

### Step 4.4 - Active and inactive relationships

*Course topic: PRO TIP: Active & Inactive Relationships*

Sales Data has two date fields (OrderDate and StockDate), but only ONE relationship from the Calendar can be active at a time.

1. Create the OrderDate relationship first (it becomes active).
2. Create the StockDate relationship. Power BI creates it as inactive (a dashed line) because an active one already exists.
3. If you ever need to change which is active, double-click the line, or use the Properties pane, and untick/tick **Make this relationship active**. You must deactivate one before you can activate the other.

> **TIP:** An inactive relationship can still be used inside one measure with the DAX function USERELATIONSHIP, for example to analyze sales by stock date.

### Step 4.5 - Star and snowflake schemas: Assignment 5 (rebuild the model)

*Course topic: Star & Snowflake Schemas; ASSIGNMENT: Table Relationships*

**Objectives:** delete all existing relationships; create a star schema between Sales, Calendar, Customer, Product and Territory; connect the three product tables in a snowflake; use a matrix visual to confirm that you can filter Order Quantity using fields from each dimension table.

1. Optional practice: in Manage relationships delete all relationships (select all and Delete), then rebuild them from the table in Step 4.3 without looking.
2. Go to **Report view**. Insert a **Matrix** visual (Visualizations pane). Put **OrderQuantity** (Sales Data) in **Values**.
3. Drop one field from each dimension into **Rows**, one at a time: Calendar Lookup[Year], Customer Lookup[Full Name], Product Lookup[ProductName], Territory Lookup[Country], Product Categories Lookup[CategoryName].
4. Each should give different numbers per row, never the same total repeated.

> **CHECKPOINT:** The Model view looks like a star: dimensions above, Sales Data and Returns Data below, and a chain Categories > Subcategories > Product. The matrix shows different Order Quantity numbers for every dimension. With nothing in Rows, the Order Quantity total is 84,174.

> **WATCH OUT:** If a column shows the same number on every row, the field comes from the fact table or the relationship is missing. Always filter with fields from the dimension tables.

### Step 4.6 - Relationship cardinality

*Course topic: Relationship Cardinality; One-to-One; Many-to-Many*

- **One-to-many** (the ideal): one instance of each primary key (marked 1) and many instances of each foreign key (marked \*). Each product appears once in Product Lookup but many times in Sales Data.
- **One-to-one:** each key appears once in both tables (for example Product Lookup and a Price Lookup). Not wrong, but you can simplify the model by merging them into one valid dimension table.
- **Many-to-many:** the key repeats in both tables. Power BI warns you. Even if you force it, you cannot tell which product was really sold. Avoid it.

### Step 4.7 - Connecting multiple fact tables

*Course topic: Connecting Multiple Fact Tables*

This model has two fact tables, Sales Data and Returns Data. They share no primary/foreign key, so they cannot connect directly. But both connect to the same dimension tables (Calendar, Product, Territory), so you can filter both with fields from those lookups. You can view orders and returns by product, but not returns by customer.

### Step 4.8 - Filter context, filter flow and bi-directional filters

*Course topic: Filter Context & Flow; Example: Filter Flow; Bi-Directional Filters; Ambiguity*

Filter context flows from the ONE side to the MANY side (downstream, the direction of the arrow on the relationship line). A filter on Territory Lookup reaches both Sales Data and Returns Data. Filter context can NOT flow upstream: a filter on Sales Data cannot reach Territory Lookup or Returns Data.

| Field you filter with | Result |
|---|---|
| Territory Lookup[SalesTerritoryKey] (dimension) | CORRECT for both Sales and Returns: the key is upstream of both fact tables. |
| Sales Data[TerritoryKey] | Sales is right, but Returns is wrong: the filter cannot flow to any other table. |
| Returns Data[TerritoryKey] | Returns is right, but Sales is wrong, and only territories that exist in Returns appear. |

#### Bi-directional filters

Changing a relationship's **Cross-filter direction** from Single to **Both** lets filter context flow in both directions. Use two-way filters carefully and only when necessary: several two-way filters create **ambiguity** (multiple possible filter paths from one table to another, which can give conflicting results). The setting "Apply security filter in both directions" relates to row-level security.

> **TIP:** Design models with one-way filters and one-to-many cardinality unless something more complex is absolutely necessary. Place lookups above fact tables as a visual reminder that filters flow downstream.

### Step 4.9 - Hide fields and Assignment 6 (the "rogue" matrix, product 338)

*Course topic: Hiding Fields; ASSIGNMENT: Filter Flow*

**Objectives:** replicate a colleague's matrix to diagnose what he must have done to the model (which product is #338, and why did his matrix show no orders?), then hide the remaining foreign keys so nobody can make the same mistake.

#### Part A - Replicate and diagnose

1. In Report view insert a **Matrix**. Put **Product Lookup[ProductKey]** in **Rows**. Put **Sales Data[OrderQuantity]** and **Returns Data[ReturnQuantity]** in **Values**. Scroll to product 338: it has an OrderQuantity but a blank ReturnQuantity (it was never returned).
2. In Model view double-click the relationship between **Returns Data** and **Product Lookup** and temporarily set **Cross-filter direction = Both**.
3. Go back to the matrix. Product 338 (and every product that has no returns) now shows NO orders.
4. Answer: product 338 is the **Road-650 Black, 44** road bike. It does not exist in Returns Data, so with a two-way filter the empty set of returns for that product flowed back up to Product Lookup and on down to Sales, wiping out its orders.
5. Set the relationship back to **Single** immediately.

> **CHECKPOINT:** Diagnosis: the Returns Data to Product Lookup relationship was set to bi-directional. Product 338 (Road-650 Black, 44) has sales but no returns, so with a two-way filter it lost its orders.

#### Part B - Hide the foreign keys

1. In Model view select (Ctrl+click) these fact-table foreign keys: Sales Data: ProductKey, CustomerKey, TerritoryKey, OrderDate, StockDate. Returns Data: ProductKey, TerritoryKey, ReturnDate.
2. Right-click > **Hide in report view** (or tick **Is hidden** in the Properties pane). Hidden fields remain available in Data and Model views, but not in Report view.
3. Recommended: also hide Product Lookup[ProductSubcategoryKey] and Product Subcategories Lookup[ProductCategoryKey].
4. Hide the demo tables: right-click **Rolling Calendar** and the unpivot demo table > Hide in report view (or the whole table).

> **TIP:** Hide the foreign keys in fact tables to force users to filter using primary keys in dimension tables. This prevents invalid filter context.

> **WATCH OUT:** Keep OrderDate unhidden only if a visual needs it; in this project every date visual uses Calendar Lookup, so hiding it is correct.

### Step 4.10 - Model layouts

*Course topic: PRO TIP: Model Layouts*

1. At the bottom of Model view click **+** to add a new layout and name it `Sales View`.
2. Drag only the sales-related tables into it (Sales Data, Calendar, Customer, Product, Territory, Categories, Subcategories). Add another layout `Returns View` with the returns-related tables.
3. Layouts are only views of the model; they do not duplicate tables.

### Step 4.11 - Data formats and data categories

*Course topic: Data Formats & Categories*

1. In Data view (or in Model view with a column selected) use the **Column tools** tab (or the Properties pane) to set formats: ProductCost and ProductPrice as **Currency** ($ English (United States)) with 2 decimals; OrderQuantity and ReturnQuantity as **Whole number** with the **thousands separator** on; date columns in a clear short-date format.
2. In **Territory Lookup** select **Continent** and set **Data category = Continent**. Select **Country** and set **Data category = Country/Region**. This helps map visuals place the data.
3. Recommended: for key columns and numeric columns that are used as labels (ProductKey, CustomerKey, Year, Month Number), set **Summarization = Don't summarize**, so Power BI does not show them with a sigma and add them up by mistake.

> **NOTE:** Region values such as Northwest or Canada are sales regions, not true geographic names, so leave Region without a data category. Data categories are also used for URLs (Web URL) and barcodes.

> **TIP:** Sort Month Name by Month Number so months appear January to December instead of alphabetically: select Month Name > Column tools > Sort by column > Month Number.

### Step 4.12 - Hierarchies: Territory Hierarchy and Date Hierarchy (Assignment 7)

*Course topic: Hierarchies; ASSIGNMENT: Hierarchies*

A hierarchy groups columns that reflect several levels of granularity (for example Country, State, City). A hierarchy is treated as ONE item in tables and reports, so users can drill up and down through its levels.

#### Territory Hierarchy

1. In the Data pane (Report, Data or Model view) expand **Territory Lookup**. Right-click **Continent** > **Create hierarchy**.
2. Rename the hierarchy `Territory Hierarchy` (right-click > Rename).
3. Right-click **Country** > **Add to hierarchy** > Territory Hierarchy. Do the same for **Region**. (You can also drag the field onto the hierarchy.)

Final order: Continent, Country, Region.

#### Date Hierarchy (Assignment 7)

1. In **Calendar Lookup** right-click **Start of Year** > **Create hierarchy**. Rename it `Date Hierarchy`.
2. Add fields in this order: **Start of Month**, **Start of Week**, **Date**. Final order: Start of Year, Start of Month, Start of Week, Date.
3. Test it: in Report view add a Matrix (rows = Date Hierarchy, values = OrderQuantity) and practise drilling up and down between each level.

> **TIP:** You can add Start of Quarter between Start of Year and Start of Month if you want a quarter level. The Product Detail and Customer Detail charts in Part 6 work with either.

### Step 4.13 - Data model best practices and Part 4 checkpoint

*Course topic: Data Model Best Practices*

- Build a **normalized** model from the start: each table has one clear, distinct purpose.
- Organize **dimension tables above data tables**.
- Avoid complex relationships; prefer 1-to-many and one-way filters.
- Hide fields from report view to prevent invalid filter context.

> **CHECKPOINT:** Save the file. The model has 8 working tables, 10 relationships (9 active and 1 inactive, the StockDate one), 2 hierarchies (Territory Hierarchy, Date Hierarchy), all fact-table foreign keys hidden, demo tables hidden.

## Part 5: Calculated Fields with DAX (Udemy Section 5)

This part has 44 lectures (about 3 hours 56 minutes). DAX (Data Analysis Expressions) is the formula language of the Power BI front-end. Do not confuse it with M, which is used only in the Power Query Editor. With DAX you add **calculated columns** (for filtering) and **measures** (for aggregation) to the model.

|  | M (Power Query) | DAX (front-end) |
|---|---|---|
| Where | Power Query Editor | Report, Data and Model views |
| Designed for | Extracting, transforming, loading data | Analyzing a relational data model |

### Step 5.1 - Calculated columns vs. measures

*Course topic: Meet DAX; Calculated Columns; DAX Measures; Implicit vs. Explicit Measures; Quick Measures; Recap*

|  | Calculated column | Measure |
|---|---|---|
| Calculated for | Each row (row context) | The current filters in a visual (filter context) |
| Stored | In the table; increases file size; recalculated on data refresh | Not stored; calculated on the fly; no extra file size |
| Best for | Filtering and grouping (e.g. Income Level) | Aggregating (sum, count, rate) in the Values of a visual |
| Where you see it | In the table (Data view) | Only inside visuals (like a PivotTable calculated field) |

- **Implicit measure:** you drag a numeric field into a visual and choose Sum, Average, etc. It exists only inside that visual.
- **Explicit measure:** you write a DAX formula and save it as a measure. It can be used anywhere and referenced by other measures (measure trees). **Always use explicit measures.**
- **Quick measures** (`Home > Quick measure`) build formulas from templates or natural-language prompts. Useful for learning, but use with caution.

> **WATCH OUT:** Never use an aggregation function (SUM, COUNT) in a calculated column. It stamps the same grand total on every row and cannot be filtered or sliced. Use a measure instead.

#### Demo: your first calculated column (Parent)

1. Go to **Table view** (Data view) and select the **Customer Lookup** table.
2. Click `Table tools > New column`. In the formula bar type the formula below and press Enter.

```
Parent =
IF ( 'Customer Lookup'[TotalChildren] > 0, "Yes", "No" )
```

> **CHECKPOINT:** Parent shows Yes for 13,068 customers (TotalChildren above 0) and No for the other 5,080.

> **NOTE:** The Parent column is needed later (Customer Priority and the Key influencers page). A conditional column in Power Query gives the identical result; either method is fine.

### Step 5.2 - Create a dedicated Measures Table

*Course topic: PRO TIP: Measure Tables*

It is a best practice to keep all measures in one dedicated table. It keeps you organized, helps you find measures quickly and lets you group them in folders.

#### Option 1 (course method): Enter Data

1. In Report view click `Home > Enter data`.
2. Leave the single empty column as is. At the bottom set the table **Name** to `Measures Table` and click **Load**. (This table is also visible in Power Query.)
3. In the Data pane right-click the empty *Column1* and choose **Hide in report view**. Do not delete it.

#### Option 2: a calculated table

```
Measures Table = { "" }
```

(From Table view: `Table tools > New table`. The curly braces create a one-column table. It is not visible in Power Query.)

#### Creating every measure from now on

1. Click the **Measures Table** in the Data pane so it is selected.
2. Click `Home > New measure`.
3. Type the formula in the formula bar. Press **Shift+Enter** for a new line and **Enter** to finish.
4. Set the format for each measure in `Measure tools > Format` as stated in the steps below.

> **TIP:** Optional: select several measures > Properties pane > Display folder to group them (for example Core, Returns, Time Intelligence).

### Step 5.3 - Filter context (understand this before writing measures)

*Course topic: Filter Context; Example: Filter Context; Step-by-Step Measure Calculation*

A measure is calculated using the **filter context**: the filters currently applied by row and column labels, slicers, page/report filters, and filters on the visual. The same measure gives a different value in every cell because every cell has a different filter context. Example: in a matrix with Product Name in Rows, the Orders cell for "Mountain Tire Tube" is calculated under the context ProductName = "Mountain Tire Tube".

#### Three steps behind every value

1. The filter context is detected and applied (for example Product Lookup[ProductColor] = "Black").
2. The filters flow downstream, from the one side to the many side, to the related tables (Sales Data and Returns Data).
3. The measure is evaluated against the filtered table (for example the sum of OrderQuantity over the rows of Sales Data that belong to black products).

> **WATCH OUT:** Every value in a report (including a Grand Total) is evaluated independently, like an island. A total is NOT the sum of the rows above it; it is the same measure with no row filter applied. Tip: select a visual and click the filter icon to see the filters applied to it.

### Step 5.4 - DAX syntax, operators and function categories

*Course topic: DAX Syntax; DAX Operators; Common Function Categories*

```
Total Quantity = SUM ( Transactions[quantity] )
  ^measure name    ^function  ^table  ^column
```

- A **fully qualified column** reference has the table name first: `'Sales Data'[OrderQuantity]`. A table name with a space needs single quotes.
- A **measure** reference is only its name in square brackets: `[Total Orders]`. Type `[` to get the list of measures.
- In a calculated column, `Sales[Qty]` returns the value in that row. In a measure it causes an error: a measure needs an aggregation to return a single value.

| Operator | Meaning | Example |
|---|---|---|
| + - \* / ^ | Arithmetic (add, subtract, multiply, divide, exponent) | 2 + 7; 2 ^ 5 |
| = > \< >= \<= \<> | Comparison (equal, greater, less, ..., not equal) | [City] = "Boston" |
| & | Joins (concatenates) text | [City] & " " & [State] |
| && | AND between two logical tests | ([State]="MA") && ([Quantity]>10) |
| \|\| | OR between two logical tests | ([State]="MA") \|\| ([State]="CT") |
| IN { } | OR against a list | [State] IN { "MA", "CT", "NY" } |

| Function family | Common examples |
|---|---|
| Math and stats | SUM, AVERAGE, MAX, MIN, DIVIDE, COUNT, COUNTA, COUNTROWS, DISTINCTCOUNT |
| Logical | IF, IFERROR, AND, OR, NOT, SWITCH, TRUE, FALSE |
| Text | CONCATENATE, COMBINEVALUES, FORMAT, LEFT, MID, RIGHT, UPPER, LOWER, LEN, SEARCH, FIND, REPLACE, SUBSTITUTE, TRIM |
| Filter | CALCULATE, FILTER, ALL, ALLEXCEPT, ALLSELECTED, KEEPFILTERS, REMOVEFILTERS, SELECTEDVALUE |
| Table | SUMMARIZE, ADDCOLUMNS, GENERATESERIES, DISTINCT, VALUES, UNION, INTERSECT, TOPN |
| Date and time | DATE, DATEDIFF, YEARFRAC, YEAR, MONTH, DAY, HOUR, TODAY, NOW, WEEKDAY, WEEKNUM, NETWORKDAYS, EOMONTH |
| Time intelligence | DATESYTD, DATESQTD, DATESMTD, DATEADD, DATESBETWEEN, DATESINPERIOD |
| Relationship | RELATED, RELATEDTABLE, CROSSFILTER, USERELATIONSHIP |
| Iterators (X functions) | SUMX, AVERAGEX, COUNTX, MAXX, MINX, RANKX |

### Step 5.5 - Math and statistical measures (Assignment 8)

*Course topic: Basic Math & Stats Functions; Counting Functions; ASSIGNMENT: Math & Stats*

**Objectives:** create **Total Customers** (number of distinct customers who made a transaction) and **Return Rate** (quantity returned divided by quantity sold). Create the building blocks first. Select the Measures Table, then `Home > New measure` for each:

```
Quantity Sold =
SUM ( 'Sales Data'[OrderQuantity] )
```

```
Quantity Returned =
SUM ( 'Returns Data'[ReturnQuantity] )
```

```
Total Returns =
[Quantity Returned]
```

```
Total Orders =
DISTINCTCOUNT ( 'Sales Data'[OrderNumber] )
```

```
Total Customers =
DISTINCTCOUNT ( 'Sales Data'[CustomerKey] )
```

```
Return Rate =
DIVIDE ( [Quantity Returned], [Quantity Sold] )
```

1. Format: Quantity Sold, Quantity Returned, Total Returns, Total Orders, Total Customers = **Whole number** with thousands separator. Return Rate = **Percentage** with 2 decimals.
2. Check them in a card or matrix (see the checkpoint). Use **DIVIDE** instead of the / operator: it returns blank (or an alternate result) instead of a divide-by-zero error.

> **CHECKPOINT:** With no filters: Quantity Sold = 84,174; Quantity Returned = 1,828; Total Orders = 25,164; Total Customers = 17,416; Return Rate = 2.17%.

> **NOTE:** Total Customers (17,416) is smaller than the 18,148 rows in Customer Lookup because it counts only customers who actually bought something. Total Returns is defined as the quantity returned, so it always agrees with the Return Rate numerator.

#### Counting functions reference

| Function | What it does |
|---|---|
| COUNT(column) | Counts non-empty cells in a column (excluding Boolean values). |
| COUNTA(column) | Counts non-empty cells in a column (including Boolean values). |
| DISTINCTCOUNT(column) | Counts the number of distinct values in a column. |
| COUNTROWS(table) | Counts the rows in a table or in a table defined by an expression. |

### Step 5.6 - Logical functions (Assignment 9)

*Course topic: Basic Logical Functions; SWITCH; ASSIGNMENT: Logical Functions*

**IF** checks a condition and returns one value if TRUE and another if FALSE. **IFERROR** returns a fallback if an expression errors. **SWITCH** compares an expression with a list of values and returns the matching result. **AND / OR** take two conditions; use `&&` and `||` for more than two. `SWITCH(TRUE(), ...)` is the standard replacement for nested IF statements.

**Objectives:** in Customer Lookup create Customer Priority, Income Level, and (bonus) Education Category. Select **Customer Lookup** in Table view, then `Table tools > New column` for each:

```
Customer Priority =
IF (
    'Customer Lookup'[Parent] = "Yes"
        && 'Customer Lookup'[AnnualIncome] > 100000,
    "Priority",
    "Standard"
)
```

```
Income Level =
SWITCH (
    TRUE (),
    'Customer Lookup'[AnnualIncome] >= 150000, "Very High",
    'Customer Lookup'[AnnualIncome] >= 100000, "High",
    'Customer Lookup'[AnnualIncome] >= 50000, "Average",
    "Low"
)
```

```
Education Category =
SWITCH (
    'Customer Lookup'[EducationLevel],
    "High School", "High School",
    "Partial High School", "High School",
    "Bachelors", "Undergrad",
    "Partial College", "Undergrad",
    "Graduate Degree", "Graduate",
    "Other"
)
```

> **CHECKPOINT:** Customer Priority: 1,269 customers are Priority (parents with income above $100,000), the rest Standard. Income Level: Very High 300, High 1,843, Average 8,201, Low 7,804 (total 18,148). Education Category: Undergrad 10,227 (Bachelors 5,261 + Partial College 4,966), High School 4,796 (3,241 + 1,555), Graduate 3,125.

> **TIP:** Spell the labels exactly ("Very High", "High", "Average", "Low") with capital letters. They appear on the donut chart legend and in the Income Level filter later (the Customer Detail donut excludes "Very High").

> **NOTE:** The "data groups" tool (right-click a field > New group) can do the Education grouping without DAX.

### Step 5.7 - Text functions (Assignment 10)

*Course topic: Text Functions; ASSIGNMENT: Text*

Text functions: LEN, CONCATENATE (or the & operator for more than two strings), UPPER / LOWER, LEFT / RIGHT / MID, SUBSTITUTE and SEARCH (position of a character, read left to right).

**Objectives:** (1) in Calendar Lookup, make a Month Short column holding the first three characters of the month name in capitals; (2) in Product Lookup create SKU Category, the characters before the FIRST hyphen of ProductSKU.

```
Month Short =
UPPER ( LEFT ( 'Calendar Lookup'[Month Name], 3 ) )
```

```
SKU Category =
LEFT (
    'Product Lookup'[ProductSKU],
    SEARCH ( "-", 'Product Lookup'[ProductSKU] ) - 1
)
```

> **CHECKPOINT:** Month Short shows JAN, FEB, ... DEC. SKU Category shows FR for FR-R38B-58 and HL for HL-U509. (SKU Type from Power Query, by contrast, shows FR-R38B.) Most common SKU categories: BK 97 products, FR 77.

> **NOTE:** Month Short must be built from Month Name (a month), not from Day Name (a weekday), otherwise it shows MON, TUE, WED instead of JAN, FEB, MAR.

### Step 5.8 - Date and time functions (Assignment 11)

*Course topic: Basic Date & Time Functions; ASSIGNMENT: Date & Time*

TODAY / NOW (current date / exact time), DAY / MONTH / YEAR, HOUR / MINUTE / SECOND, WEEKDAY (1 = Sunday to 7 = Saturday) / WEEKNUM, EOMONTH (last day of month, plus or minus months) and DATEDIFF (difference between two dates in a chosen interval).

**Objective:** in Customer Lookup create Birth Year, the year only from BirthDate.

```
Birth Year =
YEAR ( 'Customer Lookup'[BirthDate] )
```

1. Select the new column. In `Column tools` set **Data type = Whole number** and **Format = General** (turn the thousands separator OFF), so a year shows as 1966 and not 1,966.
2. Set Summarization to **Don't summarize**.

> **CHECKPOINT:** Birth Year shows four-digit years such as 1966 with no comma.

### Step 5.9 - RELATED

*Course topic: RELATED*

**RELATED(column)** returns a value from the ONE side of a relationship into each row of the MANY side. It works like Excel's VLOOKUP, but uses the model relationship. It needs row context, so it only works in a calculated column or inside an iterator (FILTER, SUMX, MAXX ...).

Demo (optional): in Sales Data create a column and look at it:

```
Retail Price =
RELATED ( 'Product Lookup'[ProductPrice] )
```

It shows the product price on every sales row. Then **delete this demo column**.

> **TIP:** Course pro tip: instead of using RELATED to create extra columns (which increases file size), nest it inside measures with iterators such as SUMX. That is exactly what Step 5.14 does.

### Step 5.10 - CALCULATE (demo and Assignment 12: bike returns)

*Course topic: CALCULATE; Example: CALCULATE; Measure Totals; ASSIGNMENT: CALCULATE*

**CALCULATE(expression, filter1, filter2, ...)** evaluates an expression in a filter context that you modify. Think of it as a filter modifier: it overrules competing report filters and forces new filter context. Filters must be fixed values or aggregations that return a scalar (you cannot filter by a measure directly).

#### Demo: Red Sales

```
Red Sales =
CALCULATE (
    [Quantity Sold],
    'Product Lookup'[ProductColor] = "Red"
)
```

Put ProductColor in Rows of a matrix with Quantity Sold and Red Sales. On the Black row, Red Sales still shows the red value, and so does every other row and the total. The row says Color = Black, the measure says Color = Red; both cannot be true at once, so the CALCULATE filter takes priority.

> **CHECKPOINT:** Red Sales = 4,011 on every row and in the total.

#### Why a measure total is not the sum of its rows

Put CategoryName in the matrix rows with Total Orders: Accessories 16,983, Bikes 13,929, Clothing 6,976 add up to 37,888, but the Total row says 25,164. Total Orders counts DISTINCT orders. Order SO74144, for example, contained a bike and a helmet, so it counts once in the total but once in EACH of Bikes and Accessories. Understand exactly what your measures calculate.

#### Assignment 12: Bike returns

**Objectives:** create Bike Returns, a matrix by Start of Month, Bike Sales, Bike Return Rate, and decide how to answer the Product VP's concern about rising returns.

```
Bike Returns =
CALCULATE (
    [Quantity Returned],
    'Product Categories Lookup'[CategoryName] = "Bikes"
)
```

```
Bike Sales =
CALCULATE (
    [Quantity Sold],
    'Product Categories Lookup'[CategoryName] = "Bikes"
)
```

```
Bike Return Rate =
DIVIDE ( [Bike Returns], [Bike Sales] )
```

1. Report view: insert a **Matrix**. Rows = Calendar Lookup[Start of Month]. Values = Bike Returns.
2. Add Bike Sales to Values, then Bike Return Rate (format as Percentage, 2 decimals).
3. Look at the three together over time.

> **CHECKPOINT:** Totals: Bike Returns = 429, Bike Sales = 13,929, Bike Return Rate = 3.08%.

**Your answer to the VP:** the volume of bike returns has risen over time, but so has the number of bikes sold. When you look at returns as a percent of sales (the rate), there is no concerning trend. Volume alone is misleading; the return rate is the right measure.

### Step 5.11 - ALL (Assignment 13: percent of all returns)

*Course topic: ALL; ASSIGNMENT: CALCULATE & ALL*

**ALL(table or column, ...)** returns all rows of a table (or all values of a column) and IGNORES any filters on them. Instead of adding filter context it removes it, which is how you build a "% of total" denominator that stays fixed. If the first argument is a table you cannot list columns; with columns, all must come from the same table.

**Objectives:** create All Returns (total returns regardless of filter context), % of All Returns, and a matrix by category name showing which category has the largest and smallest share.

```
All Returns =
CALCULATE ( [Quantity Returned], ALL ( 'Returns Data' ) )
```

```
% of All Returns =
DIVIDE ( [Quantity Returned], [All Returns] )
```

1. Format % of All Returns as Percentage with 2 decimals.
2. Matrix: Rows = Product Categories Lookup[CategoryName]; Values = % of All Returns.

> **CHECKPOINT:** Accessories 61.82% (largest share), Bikes 23.47%, Clothing 14.72% (smallest share); the shares add to 100%.

> **NOTE:** The same pattern works for orders: All Orders = CALCULATE([Total Orders], ALL('Sales Data')) and % of All Orders = DIVIDE([Total Orders], [All Orders]).

### Step 5.12 - FILTER

*Course topic: FILTER*

**FILTER(table, condition)** returns a table that is a subset of another table. It adds new filter context and, unlike CALCULATE's simple filters, can reference measures. Because it returns a whole table it is usually nested inside CALCULATE or SUMX. It iterates row by row, so it can be slow: use it only if a simple CALCULATE cannot do the job.

Demo: count orders of products priced above the overall average price.

```
Average Retail Price =
AVERAGE ( 'Product Lookup'[ProductPrice] )
```

```
Overall Average Price =
CALCULATE (
    [Average Retail Price],
    ALL ( 'Product Lookup' )
)
```

```
High Ticket Orders =
CALCULATE (
    [Total Orders],
    FILTER (
        'Product Lookup',
        'Product Lookup'[ProductPrice] > [Overall Average Price]
    )
)
```

> **CHECKPOINT:** Overall Average Price = $714.44; High Ticket Orders = 11,312.

### Step 5.13 - Iterators and Assignment 14: revenue, cost and profit

*Course topic: Iterator Functions; ASSIGNMENT: Iterators*

Iterator (X) functions loop through the same expression on each row of a table and then aggregate the results: `SUMX(Table, Expression)`. Imagine a temporary new column being added to the table, calculated row by row, and then summed (like SUMPRODUCT in Excel). Other iterators: COUNTX, AVERAGEX, MAXX, MINX, RANKX.

**Objectives:** create Total Cost (order quantity times product cost), Total Profit (revenue minus cost) without adding redundant columns to Sales Data; matrix of Total Profit by Year; how much profit has AdventureWorks earned so far in 2022?

```
Total Revenue =
SUMX (
    'Sales Data',
    'Sales Data'[OrderQuantity]
        * RELATED ( 'Product Lookup'[ProductPrice] )
)
```

```
Total Cost =
SUMX (
    'Sales Data',
    'Sales Data'[OrderQuantity]
        * RELATED ( 'Product Lookup'[ProductCost] )
)
```

```
Total Profit =
[Total Revenue] - [Total Cost]
```

```
Average Revenue per Customer =
DIVIDE ( [Total Revenue], [Total Customers] )
```

1. Format Total Revenue, Total Cost, Total Profit and Average Revenue per Customer as **Currency** ($) with 2 decimals.
2. Matrix: Rows = Calendar Lookup[Year]; Values = Total Profit.

> **CHECKPOINT:** Totals: Total Revenue = $24,914,567.18; Total Cost = $14,456,871.39; Total Profit = $10,457,695.79; Average Revenue per Customer = $1,430.56. Total Profit by year: 2020 = $2,601,602.73, 2021 = $3,967,075.69, 2022 = $3,889,017.38. The answer to the assignment: **$3,889,017.38 earned so far in 2022** (the data ends on June 30, 2022).

### Step 5.14 - Time intelligence (Assignment 15)

*Course topic: Time Intelligence; ASSIGNMENT: Time Intelligence*

> **WATCH OUT:** Time intelligence needs a proper Calendar table with continuous dates, related to the fact table by a date column. That is why Calendar Lookup and the OrderDate relationship matter.

| Pattern | Formula template |
|---|---|
| Performance to date | CALCULATE([Measure], DATESYTD(Calendar[Date])) (DATESQTD for quarters, DATESMTD for months) |
| Previous period | CALCULATE([Measure], DATEADD(Calendar[Date], -1, MONTH)) (interval DAY, MONTH, QUARTER or YEAR) |
| Running total | CALCULATE([Measure], DATESINPERIOD(Calendar[Date], MAX(Calendar[Date]), -10, DAY)) |
| Moving average | Running total divided by the number of intervals |

**Objectives:** add Previous Month Returns, Previous Month Orders, Previous Month Profit, Order Target and Profit Target (each 10% above the previous month), and 90-day Rolling Profit.

```
Previous Month Returns =
CALCULATE (
    [Total Returns],
    DATEADD ( 'Calendar Lookup'[Date], -1, MONTH )
)
```

```
Previous Month Orders =
CALCULATE (
    [Total Orders],
    DATEADD ( 'Calendar Lookup'[Date], -1, MONTH )
)
```

```
Previous Month Profit =
CALCULATE (
    [Total Profit],
    DATEADD ( 'Calendar Lookup'[Date], -1, MONTH )
)
```

```
Previous Month Revenue =
CALCULATE (
    [Total Revenue],
    DATEADD ( 'Calendar Lookup'[Date], -1, MONTH )
)
```

```
Order Target =
[Previous Month Orders] * 1.1
```

```
Profit Target =
[Previous Month Profit] * 1.1
```

```
Revenue Target =
[Previous Month Revenue] * 1.1
```

```
90-day Rolling Profit =
CALCULATE (
    [Total Profit],
    DATESINPERIOD (
        'Calendar Lookup'[Date],
        MAX ( 'Calendar Lookup'[Date] ),
        -90, DAY
    )
)
```

#### Lecture demos (optional, from the time-intelligence lecture)

```
YTD Revenue =
CALCULATE ( [Total Revenue], DATESYTD ( 'Calendar Lookup'[Date] ) )
```

```
10 Day Rolling Revenue =
CALCULATE (
    [Total Revenue],
    DATESINPERIOD ( 'Calendar Lookup'[Date],
        MAX ( 'Calendar Lookup'[Date] ), -10, DAY )
)
```

1. Format Previous Month Orders, Previous Month Returns, Order Target as **Whole number**. Format the profit and revenue measures and targets as **Currency**.
2. Test in a matrix with Calendar Lookup[Start of Month] in Rows and Total Orders, Previous Month Orders and Order Target in Values.

> **CHECKPOINT:** For June 2022: Total Orders = 2,146; Previous Month Orders (May) = 2,165; Order Target = 2,381.5. Total Profit June = $771,575.07; Profit Target = $825,827.70 (May profit $750,752.46 x 1.1); Revenue Target = $1,945,273.69. With the date filtered to the end of the data (6/30/2022) the 90-day Rolling Profit is $2,142,657.15, and YTD Revenue for 2022 is $9,185,437.85.

### Step 5.15 - Target gap measures (used by the gauges and KPI formatting)

*Course topic: Supporting measures for the dashboard*

```
Order Target Gap =
[Total Orders] - [Order Target]
```

```
Revenue Target Gap =
[Total Revenue] - [Revenue Target]
```

```
Profit Target Gap =
[Total Profit] - [Profit Target]
```

A gap below 0 means the month is under target. In Part 6 conditional formatting uses these gaps to colour numbers.

### Step 5.16 - Customer Detail measures (accurate "top customer" cards)

*Course topic: Measures for the Top N text cards (Assignment: Top N Text Cards)*

The Customer Detail page will have text cards for the top customer. When the page is filtered, several customers can share the same name, so a plain Full Name card can show the wrong person or an unrelated total. Use the HASONEVALUE pattern: return the value only when exactly ONE customer is in the filter, otherwise a dash.

```
Top Customer Name =
IF (
    HASONEVALUE ( 'Customer Lookup'[CustomerKey] ),
    MAX ( 'Customer Lookup'[Full Name] ),
    "-"
)
```

```
Top Customer Orders =
IF (
    HASONEVALUE ( 'Customer Lookup'[CustomerKey] ),
    [Total Orders],
    "-"
)
```

```
Top Customer Revenue =
IF (
    HASONEVALUE ( 'Customer Lookup'[CustomerKey] ),
    [Total Revenue],
    "-"
)
```

> **NOTE:** DAX does not care about upper and lower case in names, so 'Customer Lookup'[full name] and [Full Name] are the same column.

### Step 5.17 - What-if numeric range parameter (Price Adjustment)

*Course topic: Parameters; Example: Numeric Range Parameter*

Parameters create variables that you can reference in measures and control with a slicer. A **numeric range** parameter is typically used for scenario testing: the user adjusts a number and sees its effect on an output.

1. In Report view click `Modeling > New parameter > Numeric range` (in some versions the button is under Home or Modeling > What-if).
2. **Name:** `Price Adjustment (%)`. **Data type:** Decimal number. **Minimum:** -1. **Maximum:** 1. **Increment:** 0.1. **Default:** 0. Tick **Add slicer to this page** and click OK.
3. Power BI creates a table named *Price Adjustment (%)* (created with GENERATESERIES(-1, 1, 0.1)) and a measure that returns the selected value. Format the parameter column as Percentage with 0 decimals.
4. If the generated measure was not created, create it yourself (below), then create the two scenario measures.

```
Price Adjustment (%) Value =
SELECTEDVALUE (
    'Price Adjustment (%)'[Price Adjustment (%)], 0
)
```

```
Adjusted Revenue =
[Total Revenue] * ( 1 + [Price Adjustment (%) Value] )
```

```
Adjusted Profit =
[Adjusted Revenue] - [Total Cost]
```

> **CHECKPOINT:** With the slicer at 0%, Adjusted Profit equals Total Profit ($10,457,695.79 in total). Move the slicer to +10% and Adjusted Revenue becomes $27,406,023.90 and Adjusted Profit $12,949,152.51.

> **NOTE:** The Price Adjustment slicer is used on the Product Detail page in Part 6. A numeric-range slicer set to Between lets you pick a range; for a single adjustment value drag the handle to one value.

### Step 5.18 - DAX best practices and Part 5 checkpoint

*Course topic: DAX Best Practices*

- Know when to use calculated columns (for filtering) vs. measures (for aggregating values).
- Use explicit measures, even for simple calculations: they can be referenced anywhere and nested in other measures.
- Use fully qualified column references ('Table'[Column]): more readable and distinguishes columns from measures.
- Move column calculations upstream (data source or Power Query) when possible.
- Minimize "expensive" iterator functions (FILTER, SUMX over large tables), especially with big or complex models.

| Created in | Items |
|---|---|
| Customer Lookup (columns) | Parent, Customer Priority, Income Level, Education Category, Birth Year |
| Calendar Lookup (column) | Month Short |
| Product Lookup (column) | SKU Category |
| Measures Table: core | Quantity Sold, Quantity Returned, Total Returns, Total Orders, Total Customers, Return Rate |
| Measures Table: returns | Bike Returns, Bike Sales, Bike Return Rate, All Returns, % of All Returns |
| Measures Table: demos | Red Sales, Average Retail Price, Overall Average Price, High Ticket Orders |
| Measures Table: money | Total Revenue, Total Cost, Total Profit, Average Revenue per Customer |
| Measures Table: time | Previous Month Returns / Orders / Profit / Revenue, Order / Profit / Revenue Target, Order / Revenue / Profit Target Gap, 90-day Rolling Profit, YTD Revenue, 10 Day Rolling Revenue |
| Measures Table: customer cards | Top Customer Name, Top Customer Orders, Top Customer Revenue |
| Parameter table and measures | Price Adjustment (%), Price Adjustment (%) Value, Adjusted Revenue, Adjusted Profit |

> **CHECKPOINT:** Every measure returns a value in a matrix, and Total Profit by Year matches the Step 5.13 checkpoint. Save the file.

## Part 6: Visualizing Data with Reports (Udemy Section 6)

This part has 58 lectures (about 4 hours 12 minutes). The canvas is **1280 x 720 pixels**. Every position is given as **x** (pixels from the left edge) and **y** (pixels from the top), every size as **width x height**. To type exact values select a visual and use `Format > General > Properties > Size` (Width, Height) and `Position` (Horizontal, Vertical).

> **NOTE:** Positions, sizes, fonts, titles, filters and field names are taken from a finished reference dashboard. Colours are design choices: the dashboard uses a black navigation bar and black rounded panels behind the KPI cards, white text on those panels, and a light accent colour (a light teal or light blue) for the large numbers. Any colour that reads well on black is fine.

Build order: pages and navigation bar, then the Exec Dashboard (cards, charts, KPIs, matrix, text cards, slicer panel, interactions), the Category Tooltip page, the Map page, Product Detail, Customer Detail, and finally the optional extras. Your page tabs finish in this order: Exec Dashboard, Map, Product Detail, Customer Detail, Category Tooltip, Q & A, Decomposition tree, Key influencer.

### Step 6.1 - Plan the dashboard: the three key questions and the design framework

*Course topic: Data Visualization Overview; Report Design Framework; Sketching the Dashboard Layout*

| Key question | Answer for AdventureWorks |
|---|---|
| What type of data do I have? | Time series (sales by date), categorical (products, customers), geospatial (territories), hierarchical (category, subcategory, product). |
| What do I want to communicate? | Comparison (products, regions), composition (orders by category or income level), trend (revenue over time), top performers (customers, products), relationships. |
| Who is the end user? | Executives and managers: clear KPIs first, detail only where it supports an insight. Avoid noise and clutter. |

**The six-step design framework:** (1) define the purpose, (2) choose the right metrics, (3) present the data effectively, (4) eliminate clutter and noise, (5) use layout to focus attention, (6) tell a clear story. Sketch each page on paper before you build it.

| Goal | Typical visual |
|---|---|
| Compare categories | Bar / column chart, matrix |
| Show a trend over time | Line chart, area chart, KPI |
| Show composition | Donut chart, area chart, stacked bars |
| Show a single number | Card, KPI, gauge |
| Show location | Map, filled map |
| Show detail | Table, matrix |
| Find the "why" | Decomposition tree, key influencers, anomaly detection |

### Step 6.2 - Report view tour and formatting basics

*Course topic: Report View Overview; Formatting; Selection Pane; Alignment*

- **Canvas:** the page you design on. **Page tabs** sit along the bottom; click + to add a page.
- **Visualizations pane:** three tabs: **Build visual** (field wells), **Format visual** (Visual and General sub-tabs), and **Analytics** (trend line, forecast, anomalies). The Format page tab appears when no visual is selected.
- **Data pane:** all tables, columns, measures and hierarchies. **Filters pane:** filters on the selected visual, the page and all pages.
- **Insert tab:** new visuals, text boxes, shapes, images, buttons. **View tab:** Selection pane, Bookmarks pane, gridlines, snap to grid, page view (Fit to page), mobile layout.
- **Format Painter** (Home tab) copies formatting from one visual to another. **Format > Align / Distribute** aligns selected objects (hold Ctrl or Shift to select several).
- **Selection pane** (`View > Selection pane`): lists every object on the page, lets you rename, group, hide (eye icon) and reorder (layer) them. Always give objects clear names.
- To rename a field inside one visual only, double-click it in the field well and type the display name.

### Step 6.3 - Create the report pages

*Course topic: Creating Report Pages*

| # | Page name | Type | Size |
|---|---|---|---|
| 1 | Exec Dashboard | Normal | 1280 x 720 |
| 2 | Map | Normal | 1280 x 720 |
| 3 | Product Detail | Drillthrough (ProductName) | 1280 x 720 |
| 4 | Customer Detail | Normal | 1280 x 720 |
| 5 | Category Tooltip | Tooltip (hidden) | 425 x 225 |
| 6 | Q & A | Normal (AI, Part 7) | 1280 x 720 |
| 7 | Decomposition tree | Normal (AI, Part 7) | 1280 x 720 |
| 8 | Key influencer | Normal (AI, Part 7) | 1280 x 720 |

1. Right-click the first page tab > **Rename page** > `Exec Dashboard`.
2. Click **+** and add pages named `Map`, `Product Detail` and `Customer Detail`.
3. For each page click an empty part of the canvas, open `Format page > Canvas settings` and set **Type = 16:9** (1280 x 720). In the View tab set **Page view = Fit to page**.
4. Create the tooltip page and the three AI pages when you reach them.

### Step 6.4 - Create the two Fields parameters (used by Product Detail and Customer Detail)

*Course topic: Parameters; Example: Fields Parameter*

A **Fields parameter** lets the user switch which measure (or field) a visual shows, using a slicer. Create both now so they are ready.

#### Customer Metric selection

1. On the **Customer Detail** page: `Modeling > New parameter > Fields`.
2. **Name:** `Customer Metric selection`. In the field list tick **Total Customers** and **Average Revenue per Customer** (in that order). Keep **Add slicer to this page** ticked. Click **Create**.
3. Power BI creates a table with this DAX. Click the table in the Data pane and edit the label text so the second item reads "Revenue per Customer":

```
Customer Metric selection = {
    ("Total Customers", NAMEOF('Measures Table'[Total Customers]), 0),
    ("Revenue per Customer",
        NAMEOF('Measures Table'[Average Revenue per Customer]), 1)
}
```

#### Product Metric selection

1. On the **Product Detail** page: `Modeling > New parameter > Fields`. **Name:** `Product Metric selection`. Tick Total Orders, Total Revenue, Total Profit, Total Returns and Return Rate. Keep the slicer ticked. Create.
2. Edit the labels to Orders, Revenue, Profit, Returns, Return Rate:

```
Product Metric selection = {
    ("Orders", NAMEOF('Measures Table'[Total Orders]), 0),
    ("Revenue", NAMEOF('Measures Table'[Total Revenue]), 1),
    ("Profit", NAMEOF('Measures Table'[Total Profit]), 2),
    ("Returns", NAMEOF('Measures Table'[Total Returns]), 3),
    ("Return Rate", NAMEOF('Measures Table'[Return Rate]), 4)
}
```

> **TIP:** The same method creates a metric-switch slicer on the Exec Dashboard if you want one. The generated slicers are placed on the page; you will move and format them in Steps 6.17 and 6.18.

### Step 6.5 - Left navigation bar, logo and page buttons (repeat on every main page)

*Course topic: Building the Dashboard: Navigation Pane, Images, Shapes, Buttons*

Build it once on the Exec Dashboard, then copy it to Map, Product Detail and Customer Detail so it is identical everywhere.

1. `Insert > Shapes > Rectangle`. Set Position x 0, y 0 and Size 59 x 720. Fill: black (dark theme colour), outline off. In the Selection pane rename it `Left Nav Background`.
2. `Insert > Image` and add the AdventureWorks logo from your Images folder. Name it `AW Logo`. Position x 59, y 0, size 210 x 210, scaling type Normal. (Send it to the back so the slicer panel can cover it.)
3. `Insert > Buttons > Blank` four times. For each button open `Format > Button > Style > Icon`, set the icon Shape to **Custom** and upload one course icon: Dashboard_Icon, Map_Icon, Product_Icon, Customer_Icon.
4. Set each button's size to **59 x 49** at x 0 and y: Dashboard 494, Map 549, Product 605, Customer 660.
5. For each button set icon states: **Default** = the white icon; **On hover** and **On press / Selected** = the \_Blue version of the same icon.
6. For each button open `Format > Button > Action`: turn Action On, **Type = Page navigation**, **Destination** = Exec Dashboard, Map, Product Detail, Customer Detail respectively.
7. Insert a fifth blank button with the Filter icon (59 x 50, x 0, y 55). Its action is set in Step 6.13.
8. Insert a Reset button at x 0, y 0 (79 x 55), fill off. Its action is set in Step 6.13.
9. Select the rectangle, logo and buttons, right-click > **Group**, name the group `Navigation`. Copy it (Ctrl+C) and paste (Ctrl+V) onto Map, Product Detail and Customer Detail so the positions stay identical.

> **TIP:** Only the Dashboard button on the Exec Dashboard needs to look "selected". Setting the same icon states on every page keeps the bar consistent when you paste it.

### Step 6.6 - Exec Dashboard: KPI cards

*Course topic: Cards; Formatting Cards*

Four cards in a row at the top, each over a rounded-rectangle background. Group the cards as **KPI values**, the backgrounds as **KPI Background**, and both under a group named **KPIs** (the finished group is at about x 298, y 18, width 938, height 147).

#### Card 1: Revenue

| Setting | Value |
|---|---|
| Visual / field | Card; field Total Revenue (rename it Revenue: double-click the field in the well) |
| Position / size | x 298, y 18; 210 x 147 |
| Callout value | Font Segoe UI, size 38, Bold, display units Auto, 1 decimal place, light accent colour |
| Category label | On; size 9, Bold, white |
| Title / background | Title off; background off |
| Background shape | Rounded rectangle 186 x 108 at x 310, y 46, black fill, no outline, behind the card |

1. Insert a **Card** visual and drag **Total Revenue** into Fields. Rename the field to Revenue.
2. `Format visual > Visual > Callout value`: font Segoe UI, size 38, Bold, display units Auto, decimal places 1, set the colour.
3. `Category label`: On, size 9, Bold, white. In `General` turn Title off and Background off.
4. Insert a rounded rectangle (`Insert > Shapes > Rectangle: Rounded`), size 186 x 108, fill black, outline off. **Send to back** (Format > Arrange > Send backward) so the card sits on top.
5. Copy and paste the card three times. Place them at x 541, 783 and 1026 (all y 18, 210 x 147). Replace the field with **Total Profit** (name Profit), **Total Orders** (name Orders) and **Return Rate** (name Return rate).
6. Copy the rounded rectangle three times and place the four backgrounds at x 310, 553, 795 and 1038 (all y 46). Name the shapes Revenue, Profit, Orders and Return rate.
7. Select the four cards and group them as `KPI values`; select the four shapes and group them as `KPI Background`; select both groups and group again as `KPIs`.

> **CHECKPOINT:** The four numbers read (no filters): Revenue $24.9M, Profit $10.5M, Orders 25K, Return rate 2.17%.

> **TIP:** Course tip: use the Multi-row card when you need several measures in one visual. Cards are for one clear number executives need at a glance.

### Step 6.7 - Exec Dashboard: Revenue Trending line chart (trend line, zoom, forecast)

*Course topic: Line Charts; Trend Lines & Forecasting; Zoom Slider*

#### Line chart: Revenue Trending

| Setting | Value |
|---|---|
| Position / size | x 79, y 176; 635 x 315 |
| X-axis | Calendar Lookup[Start of Month] |
| Y-axis | Total Revenue |
| Axis titles | Off (both axes) |
| Title | Revenue Trending; centred, Segoe UI, Bold, Heading 2 |
| Zoom slider | On (Format > Visual > X-axis / Zoom slider) |
| Trend line | On (Analytics pane) |
| Labels / legend | Data labels off; legend off (single series) |

1. Insert a **Line chart**. X-axis = Start of Month (not the hierarchy; a single date field keeps anomaly detection available). Y-axis = Total Revenue.
2. `Format visual > Visual > X axis` and `Y axis`: turn the axis titles off. Turn the **Zoom slider** on.
3. `General > Title`: text `Revenue Trending`, alignment centre, font Segoe UI, Bold.
4. Open the **Analytics** pane (magnifying glass). **Trend line > Add**; adjust colour and transparency.
5. Optional practice: **Forecast > Add**; choose a forecast length in points or units, "Ignore last" periods if the last period is incomplete, and the confidence interval. **Remove the forecast again** before Step 7.1: anomaly detection cannot run with a forecast.
6. Format the tooltips: `General > Tooltips` (type Default) so hovering shows the date and revenue; format fonts and colours to match the dashboard.

> **NOTE:** The chart finishes with a trend line and, after Part 7, an anomaly-detection band. The weekly view (Start of Week) with drill is used on the Customer Detail page instead.

### Step 6.8 - Exec Dashboard: Orders by Category bar chart

*Course topic: Bar & Column Charts*

#### Clustered bar chart: Orders by Category

| Setting | Value |
|---|---|
| Position / size | x 728, y 176; 496 x 166 |
| Axis (Y) | Product Categories Lookup[CategoryName] |
| Values (X) | Total Orders; sort descending (Format > ... > Sort axis > Total Orders, Sort descending) |
| Data labels | On, position Outside end |
| Axis titles | Off |
| Title | Orders by Category |
| Tooltip | Type Report page; Page Category Tooltip (set after Step 6.15) |

1. Insert a **Clustered bar chart**. Axis = CategoryName. Values = Total Orders.
2. Sort high to low using the "..." menu on the visual > **Sort axis** > Total Orders, then **Sort descending**.
3. Turn data labels on (position Outside end) and axis titles off. Title: Orders by Category.

> **CHECKPOINT:** Bars: Accessories 16,983, Bikes 13,929, Clothing 6,976.

### Step 6.9 - Exec Dashboard: three KPI visuals

*Course topic: KPI Visuals*

KPI visuals compare the current month with the previous month, so they give the context a plain card cannot.

| KPI visual | Position / size | Value (indicator) | Trend axis | Target (goal) | Display units |
|---|---|---|---|---|---|
| Monthly Revenue | x 124, y 524; 175 x 169 | Total Revenue | Start of Month | Previous Month Revenue | Millions |
| Monthly Orders | x 322, y 524; 175 x 169 | Total Orders | Start of Month | Previous Month Orders | Thousands |
| Monthly Returns | x 540, y 524; 175 x 169 | Total Returns | Start of Month | Previous Month Returns | None |

1. Insert the **KPI** visual. Drag the measures into **Value**, **Trend axis** and **Target** as in the table.
2. `Format > Visual > Callout value`: set the Display units from the table. `Goals`: set the **Goal text** to `Prev Month` for all three.
3. For Monthly Returns: `Visual > Status` (or Indicator): **Direction = Low is good**, so a fall in returns shows green, and set the **Bad colour** to `#AB1818`.
4. `General > Title`: type the title (Monthly Revenue / Monthly Orders / Monthly Returns), turn on **title wrapping**, turn the background on and set the border width to 1.

> **WATCH OUT:** Give each KPI its own title. It is easy to copy a visual and forget to rename it, leaving three KPIs that all say Monthly Revenue.

### Step 6.10 - The Filters pane: visual, page and report level, and Top N

*Course topic: Filters; Filter Types; Top N Filters*

| Filter level | Applies to |
|---|---|
| Filters on this visual | Only the selected visual. |
| Filters on this page | Every visual on the current page. |
| Filters on all pages | Every visual on every page of the report. |
| Drillthrough filters | Set on the drillthrough page itself (Step 6.17). |

| Filter type | How it works |
|---|---|
| Basic filtering | Tick the values to keep (or "Select all"). |
| Advanced filtering | Conditions such as "is not", "contains", "is not blank", combined with And / Or. |
| Top N | Pick Top or Bottom, the number of items, and a **By value** field (usually a measure), then click **Apply filter**. |
| Relative date / Relative time | Last N days, weeks, months, years relative to today. |

1. Select a visual. In the Filters pane find the field (or drag a field into **Add data fields here** under "Filters on this visual").
2. Change **Filter type** to Top N, set **Show items: Top** and the number.
3. Drag the measure into **By value** and click **Apply filter**.

> **TIP:** A visual-level filter can use a field that is not shown in the visual. The Customer Detail "top customer" cards in Step 6.18 rely on this.

### Step 6.11 - Exec Dashboard: Top 10 Products matrix with conditional formatting

*Course topic: Matrix & Table Visuals; Conditional Formatting*

#### Matrix: Top 10 Products

| Setting | Value |
|---|---|
| Position / size | x 783, y 342; 469 x 239 |
| Rows | Product Lookup[ProductName] (display name Top 10 Products) |
| Values | Total Orders (Orders), Total Revenue (Revenue), Return Rate (Return%) |
| Subtotals | Row and column subtotals off |
| Header alignment | Centre |
| Orders column | Data bars; positive colour #CCCCCC, negative white |
| Return% column | Background colour, Gradient: minimum white, maximum a light accent colour (colour-blind friendly) |
| Filter | ProductName: Top N = Top 10 by Total Orders |
| Sort | Total Orders, descending |

1. Insert a **Matrix**. Rows = ProductName (rename it Top 10 Products). Values = Total Orders, Total Revenue and Return Rate; rename them to the short names above.
2. `Format > Visual > Cell elements`: choose the **Orders** series; turn **Data bars** on; positive bar colour #CCCCCC.
3. Choose the **Return%** series; turn **Background colour** on; click **fx**; Format style = **Gradient**; minimum white; maximum a light accent colour.
4. Filters pane > ProductName > Filter type **Top N** > Show items Top **10** > By value **Total Orders** > **Apply filter**.
5. `Format > Visual > Row subtotals` and `Column subtotals`: Off. Sort by Total Orders descending (click the Orders header).

> **TIP:** Use subtle, colour-blind-friendly colours for conditional formatting. Right-clicking any product in this matrix later opens the Product Detail drillthrough page.

### Step 6.12 - Exec Dashboard: Most Ordered / Most Returned Product Type cards

*Course topic: Top N Text Cards*

1. Insert two **text boxes** (`Insert > Text box`) with the exact text `Most Ordered Product Type` (x 778, y 586, 176 x 46) and `Most Returned Product Type` (x 1026, y 586, 185 x 46). Background off.
2. Insert a **Card** at x 780, y 622, 229 x 45. Field = **SubcategoryName** (Product Subcategories Lookup), summarised as First (or Min). Category label off. Font Segoe UI Bold, size 14, white. Background dark.
3. Filters pane > this visual > SubcategoryName > **Top N = Top 1** by **Total Orders** > Apply filter.
4. Copy the card and place it at x 1026, y 621, 226 x 46. Change the Top N **By value** measure to **Total Returns** (Quantity Returned) and apply.

> **CHECKPOINT:** Most ordered product type: Tires and Tubes (9,084 orders). Most returned product type: Tires and Tubes (534 returned).

### Step 6.13 - Exec Dashboard: slicer panel with bookmarks and buttons

*Course topic: Slicers; Slicer Panels; Bookmarks; Buttons*

**Goal:** a hidden panel with Year and Continent slicers that slides in when the Filter icon is clicked, plus a Reset button.

#### Part A - Build the panel

1. Insert a rectangle at x 0, y 0, 311 x 720, fill black, outline off. This is the panel background.
2. Insert slicer 1: field **Start of Year** (Calendar Lookup). Position x 16, y 72, 278 x 126. Style: List. Header text `Year`, Segoe UI Bold, white. Items size 10, white. Background off. Filter the slicer to exclude (Blank).
3. Insert slicer 2: field **Continent** (the Continent level of Territory Hierarchy). Position x 16, y 234, 278 x 126. Header text `Continent`, same formatting as slicer 1.
4. Insert a left-arrow button (`Insert > Buttons > Left arrow`): 55 x 40 at x 243, y 6, white arrow.
5. Select the rectangle, both slicers and the arrow, group them and name the group `Slicer panel`.

#### Part B - Bookmarks (View > Bookmarks pane)

| Bookmark | State when you capture it | Options | Used by |
|---|---|---|---|
| Hide slicer panel | Slicer panel group hidden (eye icon off in the Selection pane) | Data OFF; applies to all visuals | The left-arrow button inside the panel |
| Show slicer panel | Slicer panel group visible (eye icon on) | Data OFF; applies to the panel group and its slicers | The Filter icon button on the left bar |
| Clear Exec Filters | Page with all slicers and visual selections cleared | Data ON | The Reset button |

1. In the Selection pane switch the Slicer panel group **off** (hidden). Open the Bookmarks pane, click **Add**, rename the bookmark `Hide slicer panel`, click its "..." > untick **Data**.
2. Switch the group **on**. Click **Add**, rename it `Show slicer panel`, untick **Data**.
3. Clear every slicer and visual selection. Click **Add**, rename it `Clear Exec Filters`. Leave Data ticked.
4. Select the left-arrow button > `Format > Button > Action` > Type Bookmark > Bookmark = Hide slicer panel.
5. Select the Filter icon button (x 0, y 55) > Action > Bookmark = Show slicer panel.
6. Select the Reset button (x 0, y 0, 79 x 55) > Action > Bookmark = Clear Exec Filters; Tooltip text `Click to clear all the filters`.
7. Finally hide the Slicer panel group in the Selection pane and set the page as you want it to open.
8. Test in Desktop with Ctrl + click on each button.

> **WATCH OUT:** Capture each bookmark in the correct visual state FIRST (show or hide the group), THEN click Add, then rename. Untick Data on the show and hide bookmarks so they do not reset the slicer choices the user already made.

### Step 6.14 - Exec Dashboard: report interactions

*Course topic: Edit Interactions*

1. Select the **Revenue Trending** line chart > `Format > Edit interactions`. On the Orders by Category bar chart choose **Filter**; on the three KPI visuals choose **None**.
2. Select the **Top 10 Products** matrix. On the line chart choose **Filter**; on the Orders by Category bar chart and on both Most Ordered / Most Returned cards choose **None**.
3. Turn Edit interactions off.

> **TIP:** Each other visual shows three icons: Filter, Highlight and None. Cross-filtering is the default; use None for any visual that should stay fixed.

### Step 6.15 - Category Tooltip page

*Course topic: Custom Tooltips*

1. Add a page and name it `Category Tooltip`.
2. `Format page > Canvas settings > Type = Tooltip`. The size becomes 425 x 225. Right-click the page tab > **Hide page** (or tick Allow use as tooltip and hide it from view mode).
3. Insert a **Multi-row card** at x 10, y 0, 140 x 225 with Total Revenue, Total Profit, Total Orders, Total Returns, Return Rate. Data labels size 10; category labels size 8, Bold, white.
4. Insert an **Area chart** at x 150, y 0, 248 x 225: Axis = Date Hierarchy (Start of Week level active), Values = Total Orders. Title `Weekly Orders`, size 8, centred. Axis fonts size 8.
5. Go back to the Exec Dashboard, select the Orders by Category bar chart > `Format > General > Tooltips` > Type **Report page**, Page **Category Tooltip**. Hover a bar to test.

> **CHECKPOINT:** Hovering over the Bikes bar shows the multi-row card for the Bikes category and a weekly orders area chart.

### Step 6.16 - Map page

*Course topic: Maps; Filled Maps; Geospatial Visuals*

#### Map page objects

| Setting | Value |
|---|---|
| Navigation | Paste the Navigation group from the Exec Dashboard |
| Slicer | Territory Lookup[Continent]; x 72, y 6; 1208 x 94; orientation Horizontal; header off; items bold with background |
| Map visual | x 93, y 100; 1187 x 593; Location: Territory Lookup[Country]; Bubble size: Total Orders |
| Map settings | Style: Dark canvas; category labels on with a semi-transparent background (about 85%); lasso button on; title off |

1. Paste the Navigation group. Insert a **Slicer** with Continent. `Format > Slicer settings > Orientation = Horizontal` (older versions: Format > General > Orientation), Header off, items Bold. Size 1208 x 94 at x 72, y 6.
2. Insert a **Map** at x 93, y 100, 1187 x 593. **Location** = Country. **Bubble size** = Total Orders.
3. `Format > Map settings`: Style = **Dark canvas**. `Category labels`: On; background on with transparency about 85%. `Bubbles`: adjust the size.
4. Optional: add a Country filter and a Total Orders filter in the Filters pane to limit the bubbles.

> **TIP:** For a drillable map, use **Territory Hierarchy** (Continent, Country, Region) as the Location and turn on drill mode. Maps use Bing/Azure Maps; Country must have the Country/Region data category (Step 4.11). Maps may need to be allowed in your organisation's tenant settings if you publish.

### Step 6.17 - Product Detail page (drillthrough)

*Course topic: Drillthrough; Gauges; Area Charts*

**Goal:** a page for ONE product, reached by right-clicking a product anywhere in the report.

1. Select the Product Detail page and paste the Navigation group.
2. Click an empty part of the canvas. In the Build pane drag **Product Lookup[ProductName]** into the **Drill through** well. (The page type becomes Drillthrough and a page-level filter on ProductName is created.) Turn on **Keep all filters** if you want other filters carried over. Power BI adds a back button automatically.

#### Card: Selected Product

| Setting | Value |
|---|---|
| Position / size | x 78, y 46; 237 x 135 |
| Field | ProductName, summarised as First (or Min); category label off |
| Format | Segoe UI Bold, size 25, white; background black |
| Extra | A text box above it reading `Selected Product` |

| Gauge | Position / size | Value | Maximum / target | Title |
|---|---|---|---|---|
| Orders | x 350, y 29; 256 x 252 | Total Orders | Order Target | Monthly orders vs target |
| Revenue | x 666, y 29; 256 x 252 | Total Revenue | Revenue Target | Monthly Revenue vs target |
| Profit | x 982, y 29; 256 x 252 | Total Profit | Profit Target | Monthly Profit vs target |

1. Insert three **Gauge** visuals as in the table. Put the target measure in **Maximum value** (and also in **Target value**). Titles centred, Segoe UI size 12.
2. For each gauge add a visual filter on **Start of Month**: Top N = **Top 1** by Start of Month (Latest). This shows only the latest month.
3. Callout value: Segoe UI Bold. `Format > Callout value > Colour > fx > Format style Rules`: red when the matching gap measure (Order Target Gap, Revenue Target Gap, Profit Target Gap) is below 0, otherwise grey. Gauge fill black, labels size 10.

#### Line chart: Profit Trending

| Setting | Value |
|---|---|
| Position / size | x 331, y 251; 949 x 220 |
| Axis | Calendar Lookup Date Hierarchy |
| Values | Total Profit and Adjusted Profit |
| Format | Zoom slider on; data labels on; markers size 3; legend on; title centred, Bold, size 13 |

#### Slicer: Price Adjustment (%)

| Setting | Value |
|---|---|
| Position / size | x 78, y 315; 237 x 155 |
| Field | Price Adjustment (%) (drives Adjusted Profit) |
| Start value | The reference report starts at -30%; any range works |

#### Area chart: Returns Trending

| Setting | Value |
|---|---|
| Position / size | x 349, y 462; 571 x 238 |
| Axis | Date Hierarchy (Start of Quarter level active) |
| Values | Product Metric selection (field parameter) |
| Format | Zoom slider on |

#### Slicer: Product Metric selection

| Setting | Value |
|---|---|
| Position / size | x 78, y 470; 213 x 204 |
| Format | Header Segoe UI Bold, size 10; Selection: Single select with "Select all" off (one metric is always required); white background |

1. Insert the Smart narrative at x 971, y 518, 309 x 181 (see Step 7.2).
2. **Test:** go to the Exec Dashboard, right-click any product in the Top 10 Products matrix > **Drill through > Product Detail**. The page opens filtered to that product.

> **NOTE:** The "Maximum" of each gauge uses the same Target measure that feeds the gap used for the red/grey callout colour, so the gauge and the colour always agree. A product with no sales in the latest month shows a blank gauge, because the Top 1 month filter keeps only that month.

### Step 6.18 - Customer Detail page (Assignments: cards, line chart, donuts, table, top customer)

*Course topic: ASSIGNMENT: Cards; Line Charts; Donut Charts; Tables; Top N Text Cards; Slicers*

Paste the Navigation group on the Customer Detail page. Then build, in this order:

#### A. Two cards

#### Card: Unique customers

| Setting | Value |
|---|---|
| Field | Total Customers (display name Unique customers) |
| Position / size | x 105, y 0; 150 x 151 |
| Callout value | Segoe UI, 38, Bold, 1 decimal |
| Category label | Size 9, Bold, white |
| Background | Rounded rectangle 196 x 102 at x 82, y 27 behind it |

#### Card: Revenue per customer

| Setting | Value |
|---|---|
| Field | Average Revenue per Customer (display name Revenue per customer) |
| Position / size | x 105, y 114; 150 x 151 |
| Formatting | Copy and paste the first card and change the field (or use Format Painter) |
| Background | Rounded rectangle 196 x 102 at x 82, y 151 |

#### B. Metric tiles and the customer line chart

#### Tile slicer: Customer Metric selection

| Setting | Value |
|---|---|
| Field | Customer Metric selection (created in Step 6.4) |
| Position / size | x 312, y 0; 949 x 65 |
| Style | Tile; orientation Horizontal; header off |
| Selection | Single select (one value always selected) |
| Items | Bold, white text, dark background, outline off |

#### Line chart: Total customers

| Setting | Value |
|---|---|
| Position / size | x 312, y 79; 949 x 221 |
| X-axis | Date Hierarchy (Year, Month, Quarter, Week levels); Start of Week active so it opens weekly |
| Y-axis | Customer Metric selection (field parameter) |
| Zoom slider | On |
| Trend line | On, transparency 75% |
| Axis titles / title | Axis titles off; title `Total customers`, centred, Segoe UI, Bold, size 13 |

1. Insert the two cards and their backgrounds.
2. Insert the **Customer Metric selection** slicer: `Format > Slicer settings > Style = Tile`, Orientation Horizontal, Header off, `Selection > Single select` on, Select all off.
3. Insert a **Line chart**. First test with X-axis = Start of Week and Y-axis = Total Customers. Then drag the **Customer Metric selection** field into the Y-axis, replacing Total Customers.
4. Replace the X-axis with the whole **Date Hierarchy**.
5. **Drill up and down:** use the arrows in the chart header: the up arrow (Drill up), the single down arrow (turns drill mode on, then clicking a point drills), and the forked arrow (Expand all down one level). Test every level: Year, Month, Week, Date. Why do some weeks look low? The first and last week of the data are partial weeks. Turn drill mode off and drill back to Week so the chart opens weekly by default.
6. Add the **Trend line** in the Analytics pane and turn on the **Zoom slider**. Format the tooltips like the Exec Dashboard line chart.
7. Click each tile of the slicer to confirm the chart switches between Total Customers and Revenue per Customer.

#### C. Two donut charts

#### Donut: Orders by Income level

| Setting | Value |
|---|---|
| Position / size | x 63, y 266; 260 x 212 |
| Legend / Values | Customer Lookup[Income Level] / Total Orders |
| Labels | Detail labels: Category, value; size 8; 1 decimal; legend off |
| Filter | Visual-level: Income Level is not Very High |
| Title | Orders by Income level |

#### Donut: Orders by Occupation

| Setting | Value |
|---|---|
| Position / size | x 64, y 488; 269 x 232 |
| Legend / Values | Customer Lookup[Occupation] / Total Orders |
| Filter | Occupation: Top N = Top 3 by Total Orders (remove the Income filter) |
| Title | Orders by Occupation |

1. Insert a **Donut chart**. Legend = Income Level; Values = Total Orders. Add a title; turn the legend off. `Format > Detail labels`: Label contents Category, value; size 8; decimal places 1. Recolour the slices. Add the visual filter Income Level **is not** Very High (Advanced filtering).
2. Copy and paste the donut. Change the Legend to **Occupation**. Remove the Income filter and add **Top N = Top 3** by Total Orders. Retitle it `Orders by Occupation`.

> **CHECKPOINT:** Top 3 occupations by orders: Professional, Skilled Manual, Management. Income levels with orders: Average, Low, High (Very High excluded).

#### D. Top 100 customers table

#### Table: Top 100 customers

| Setting | Value |
|---|---|
| Position / size | x 323, y 300; 446 x 396 |
| Columns | CustomerKey (named Top 100 customers), Full Name, Total Orders (Orders), Total Revenue (Revenue) |
| Filter | Full Name: Top N = Top 100 by Total Orders |
| Totals row | Off |
| Orders column | Data bars, colour #70BBFF (light blue) |
| Revenue column | Background colour gradient, white to blue |
| Sort | Orders descending |

1. Insert a **Table** with the four fields. Rename the columns by double-clicking the fields in the Values well.
2. Filters pane > this visual > Full Name > Top N > Top **100** by **Total Orders** > Apply.
3. `Format > Cell elements`: Orders > Data bars on. Revenue > Background colour > fx > Gradient, white to blue. Turn the totals row off. Sort by Orders descending. Title: Top 100 customers.

#### E. Year slicer and the Top Customer cards

#### Slicer: year range

| Setting | Value |
|---|---|
| Field | Calendar Lookup Date Hierarchy: Start of Year |
| Position / size | x 827, y 300; 300 x 73 |
| Style | Between; horizontal; header off; start date 1/1/2020 |
| Filter | Exclude blanks |

| Object | Position / size | Content |
|---|---|---|
| Text box | x 785, y 372; 191 x 38 | Top Customer (by Revenue): |
| Card 1 | x 785, y 410; 476 x 67 | Top Customer Name (Segoe UI Bold 30, white) |
| Text box | x 785, y 496; 191 x 38 | Orders: |
| Card 2 | x 786, y 520; 164 x 94 | Top Customer Orders (Segoe UI Bold 30) |
| Text box | x 1049, y 496; 191 x 38 | Revenue: |
| Card 3 | x 1054, y 520; 181 x 94 | Top Customer Revenue (Segoe UI Bold 30) |

1. Insert the year slicer: `Format > Slicer settings > Style = Between`, Orientation Horizontal, Header off. Filter it to exclude (Blank). Set the start to 1/1/2020.
2. Insert the three text boxes and three cards from the table. All three cards use a dark background.
3. On **each of the three cards** add a visual-level filter **Top N = Top 1 on CustomerKey by Total Revenue** (drag CustomerKey into the filters of the visual; it need not be shown). Using CustomerKey, a unique value, means two customers with the same name cannot tie and show a wrong total.
4. The three HASONEVALUE measures return a dash if more than one customer remains in the filter, so a card can never show a misleading total.

> **WATCH OUT:** The trap in this assignment: filter the page to low-income customers and several customers can have the same Full Name. A card filtered Top 1 on Full Name can show the wrong person or an unrelated total. Always put CustomerKey in the Top N filter.

> **CHECKPOINT:** With no filters the top customer by revenue is Mr. Maurice Shan: 6 orders, $12,407.95. With the Year slicer and the Occupation donut set to 2022 and Skilled Manual, the top customer is Ruben Suarez with $4,682.67 (about $4,683).

### Step 6.19 - Customer Detail: report interactions, bookmarks and buttons

*Course topic: Edit Interactions; Bookmarks; Buttons; Page Navigation*

#### Edit interactions

1. Select the Year slicer > `Format > Edit interactions`. Make sure it is set to **Filter** on every visual on the page.
2. Select the customer line chart. On both donuts choose **Filter** (not Highlight).
3. Select the Top 100 customers table. Set the line chart and both donuts to **None**.
4. Turn Edit interactions off.

#### Bookmarks and buttons

1. Filter the page to find an insight. The course example: Skilled Manual customers in 2022; **Ruben Suarez** generated the most revenue, $4,683. You may use any insight you find.
2. View > Bookmarks pane > **Add**. Name it `Customer insights`.
3. Insert > Buttons > **Information** (x 815, y 634; 358 x 85). In `Format > Button > Style > Text` set the **Default** state text to `Customer Insights from 2020 - 2022`. Switch the state to **Selected** and type a longer sentence describing your insight (for example: Among Skilled Manual customers in 2022, Ruben Suarez generated the most revenue at $4,683). Add Tooltip text as well.
4. Action: Type **Bookmark**, Bookmark **Customer insights**.
5. Clear every filter (slicer back to all years, donut selections cleared). Add a second bookmark named `Clear all customer Filters`.
6. Insert a **Reset** button (100 x 40, x 0, y 0), fill off. Action: Bookmark **Clear all customer Filters**. Tooltip: Clear all customers filters click here.
7. Test both buttons with **Ctrl + click** in Desktop.

> **TIP:** Page navigation buttons were created in Step 6.5. Alternatively insert a Navigator (`Insert > Buttons > Navigator > Page navigator`) to generate buttons for every page automatically.

### Step 6.20 - Optional: custom visuals, row-level security, mobile layout and publishing

*Course topic: Custom Visuals; Row-Level Security; Mobile Layouts; Publishing*

#### Custom visuals

`Home > Get more visuals` opens AppSource. A Power BI account is needed to browse and import them. Optional for this project.

#### Row-level security (RLS)

1. `Modeling > Manage roles > New` (Create). Name the role `Europe`.
2. Select the **Territory Lookup** table and enter the DAX filter below. Create `North America` and `Pacific` the same way.
3. `Modeling > View as`, tick a role, and confirm every visual shows only that continent. Click Stop viewing.

```
[Continent] = "Europe"
```

> **NOTE:** Roles are defined in Desktop but only enforced after publishing to Power BI Service.

#### Mobile layout and publishing

`View > Mobile layout`: drag existing visuals onto the phone canvas and resize them. Used by the Power BI mobile app after publishing. The **Publish** button is only previewed in the course; Power BI Service is outside its scope.

### Step 6.21 - Visualization best practices and Part 6 checkpoint

*Course topic: Visualization Best Practices*

- Answer the three key questions before you build; sketch on paper first.
- Put the most important KPIs top-left; use size, position and colour to direct attention.
- Remove clutter: turn off axis titles, gridlines and legends that add nothing.
- Use consistent fonts, colours and alignment; name and group objects in the Selection pane.
- Use conditional formatting sparingly and with colour-blind-friendly colours.
- Label everything clearly: titles, units, and the date range the numbers cover.

> **CHECKPOINT:** All four main pages and the tooltip page are built and named. The Exec Dashboard shows four cards, a trend line chart, a bar chart with a hover tooltip, three KPI visuals, the Top 10 matrix, two Top N text cards, a slicer panel that opens and closes, and a Reset button. Map has a continent slicer and a bubble map. Product Detail opens by drillthrough with three gauges. Customer Detail has two cards, metric tiles, a drillable weekly line chart, two donuts, a Top 100 table, three top-customer cards, a year slicer, an insight bookmark and a Reset button.

## Part 7: Artificial Intelligence Visuals (Udemy Section 7)

Section 7 has 6 lectures (about 47 minutes). Power BI includes AI tools that explain data automatically. In the finished report each one lives on the page named below.

### Step 7.1 - Anomaly detection (Exec Dashboard line chart)

*Course topic: Anomaly Detection*

1. On the Exec Dashboard select the **Revenue Trending** line chart. Make sure the forecast from Step 6.7 has been removed.
2. Open the **Analytics** pane > **Find anomalies** > **Add**.
3. Set the **Sensitivity** to about 79% (the reference report value; higher sensitivity flags more points). The confidence band colour is #FBD111.
4. Click an anomaly flag on the chart. The side panel shows an AI explanation, and you can choose **Explain by** fields such as subcategory and country for root cause.

> **WATCH OUT:** Anomaly detection needs a date on the X-axis, at least four data points, ONE value on the Y-axis, no legend or secondary axis, no forecast at the same time, and it does not work together with drill up/down. That is why this chart uses the single field Start of Month and no hierarchy.

### Step 7.2 - Smart narrative (Product Detail page)

*Course topic: Smart Narratives*

1. Go to the Product Detail page. Click `Insert > Smart narrative` (this summarises the whole page), or right-click a single visual > **Summarize**.
2. Position and size: x 971, y 518; 309 x 181.
3. Edit the text like a text box. To insert a dynamic value, click **+ Value** in the narrative toolbar (or type a forward slash) and choose a field or measure, for example Total Orders for the selected product. Format values as a number or percentage; for dates use the format `dddd, MMMM d, yyyy`. Make key numbers bold.
4. Change the drillthrough product or a slicer: the sentence updates automatically.

### Step 7.3 - Q&A visual (page: Q & A)

*Course topic: Q&A Visuals*

1. Add a page and name it `Q & A`. Insert the **Q&A** visual (`Insert > Q&A`) at x 92, y 92; 697 x 462.
2. Type the question `return rate by SKU category`. Power BI builds the visual from your model.
3. Train it: `Modeling > Q&A setup` to add **synonyms** for tables, columns and measures (you can also set Synonyms in the Model view Properties pane), and use **Teach Q&A** for words it does not understand. Review questions and suggested questions need Power BI Service.
4. You can convert the answer into a standard visual with the button next to the answer.
5. Optional: add a Matrix beside it (x 890, y 190) with CategoryName in Rows and Total Orders in Values.

### Step 7.4 - Decomposition tree (page: Decomposition tree)

*Course topic: Decomposition Trees*

1. Add a page named `Decomposition tree`. Insert a **Decomposition tree** at x 56, y 98; 994 x 485.
2. **Analyze:** Return Rate. **Explain by:** CategoryName, SubcategoryName, ProductName.
3. Insert a card (x 1036, y 142; 153 x 150) with Total Orders.
4. Click the **+** next to a node to split by a dimension you choose, or pick the AI splits (**High value** / **Low value**) to let Power BI find the field that most increases or decreases the return rate.

### Step 7.5 - Key influencers (page: Key influencer)

*Course topic: Key Influencers*

1. Add a page named `Key influencer`. Insert a **Key influencers** visual at x 10, y 0; 710 x 704.
2. **Analyze:** Customer Lookup[HomeOwner]. The values are Y and N; choose the target value **Y** to learn what makes a customer more likely to own a home. **Explain by:** AnnualIncome, EducationLevel, Parent, MaritalStatus, Occupation (the Parent field you built in Step 5.1).
3. Insert a second Key influencers visual (x 730, y 0; 550 x 704): **Analyze** ProductPrice, **Explain by** Sum of ProductCost (continuous analysis; counting set to Absolute).
4. Read the **Key influencers** tab (factors that raise the chance of the outcome) and the **Top segments** tab (combinations of factors).

> **NOTE:** The course illustration reads: "parents may be about 1.59 times more likely to be homeowners, all else equal" and a top segment where 93% of married customers with children and a Bachelors degree own a home versus 67.6% overall. Your exact numbers depend on the Explain by fields you choose.

> **CHECKPOINT:** Part 7 done: four extra pages (Q & A, Decomposition tree, Key influencer) plus anomaly detection on the Exec Dashboard and the smart narrative on Product Detail.

## Part 8: Power BI Optimization Tools (Udemy Section 8)

Section 8 has 7 lectures (about 30 minutes). The Optimize tab on the ribbon speeds up report building and helps you find slow visuals.

### Step 8.1 - Optimize ribbon and pause visuals

*Course topic: The Optimize Ribbon; Pause Visuals*

1. Open the **Optimize** tab on the ribbon.
2. Click **Pause visuals**. Changes are held and each visual shows "visual has pending changes". You can add, move and remove fields without waiting; formatting is blocked while paused.
3. Click **Refresh visuals** (or the refresh icon on one visual) when ready, then resume.

### Step 8.2 - Optimization presets

*Course topic: Optimization Presets*

| Preset | Best for |
|---|---|
| Interactivity (default) | Import mode; cross-highlighting, cross-filtering and live slicers are all allowed. |
| Query reduction | DirectQuery; turns off cross-highlighting and cross-filtering and adds an Apply button to the filter pane and slicers. |
| Customize | You choose which query-reduction options to use. |

### Step 8.3 - Apply all slicers button

*Course topic: Apply All Slicers*

1. On the Optimize tab click **Add apply all slicers button** (and the clear all slicers button).
2. Choose several slicer values, then click **Apply** once: all slicers apply at the same time, so fewer queries run.
3. The buttons affect every slicer on the page. Format them like any other button.

### Step 8.4 - Performance Analyzer

*Course topic: Performance Analyzer*

1. `Optimize > Performance analyzer > Start recording`.
2. Click **Refresh visuals**, or interact with the report (change a slicer, switch pages).
3. Expand each visual to read the timings in milliseconds: **DAX query** (time to run the query), **Visual display** (time to draw), and **Other** (waiting and preparation).
4. A visual with a long DAX query time points to a heavy measure. Use **Copy query** or export the results as JSON for deeper analysis.

### Step 8.5 - External tools

*Course topic: External Tools*

Installed external tools appear on the External Tools tab: **DAX Studio** (measure performance), **Tabular Editor** and **ALM Toolkit** (modelling), **Bravo**, Excel, Python and Power BI Report Builder. The course only introduces them.

> **CHECKPOINT:** Performance Analyzer has been run once on the Exec Dashboard and no visual has an unusually long DAX query time.

## Part 9: Final Delivery and Reference

### Step 9.1 - Bonus project: Maven Market (outline)

*Course topic: Bonus Project*

The course ends with a bonus project for a new client, Maven Market. Repeat the same four-part workflow on its data; this guide doubles as a template.

| Part | What to do |
|---|---|
| 1 Connect and shape | Load every table, set the locale, clean text and dates. |
| 2 Create the data model | Relationships, hidden keys, hierarchies. |
| 3 Add DAX measures | The core measures first, then targets and time intelligence. |
| 4 Build the report | KPI cards, trend lines, a map, a matrix and slicers. |

### Step 9.2 - Newer features (optional extras from the course update section)

*Course topic: UPDATE lectures*

- Calculation groups, the new Card visual, the Button slicer, the List slicer, Visual calculations.
- DAX query view and DAX INFO.VIEW functions (a dynamic data dictionary).
- AI documentation with TMDL view.

These are not needed for the AdventureWorks report.

### Step 9.3 - Final project checklist

| # | Item | Done |
|---|---|---|
| 1 | Global Preview features on; Current File options set (no auto relationships, no auto date/time, English (United States)) |  |
| 2 | Eight tables loaded with the row counts in the verification table; demo queries not loaded |  |
| 3 | Product Lookup: currency types, ProductSize removed, SKU Type added, ProductStyle zeros replaced with NA |  |
| 4 | Customer Lookup: errors removed; Full Name and Domain Name created |  |
| 5 | Calendar Lookup: Month Name, Month Number, Start of Year, Year plus week, month and quarter columns |  |
| 6 | Sales Data from the folder (56,046 rows) with Quantity Type; Returns Data loaded (1,809 rows) |  |
| 7 | 10 relationships created, StockDate relationship inactive, fact-table keys hidden |  |
| 8 | Territory Hierarchy and Date Hierarchy created; data categories set |  |
| 9 | Measures Table with all measures; calculated columns in the lookup tables |  |
| 10 | Price Adjustment (%) parameter and the two Fields parameters created |  |
| 11 | Exec Dashboard, Map, Product Detail, Customer Detail complete; Category Tooltip page hidden |  |
| 12 | Bookmarks, page navigation, drillthrough and slicer panel all work (Ctrl + click) |  |
| 13 | AI pages added (Q & A, Decomposition tree, Key influencer); Performance Analyzer run once |  |
| 14 | File saved as AdventureWorks.pbix; a screenshot of every page captured for your submission |  |

### Step 9.4 - Verification table: numbers you should see

Every value below was calculated directly from the project data (no filters unless stated).

| What | Expected value |
|---|---|
| Rows: Calendar / Customer / Product / Categories / Subcategories / Territory | 912 / 18,148 / 293 / 4 / 37 / 10 |
| Rows: Sales Data (2020 + 2021 + 2022) / Returns Data | 56,046 (2,630 + 23,935 + 29,481) / 1,809 |
| Average product cost; colours; distinct customers; maximum annual income | $413.66; 10; 18,148; $170,000 |
| Quantity Sold / Quantity Returned | 84,174 / 1,828 |
| Total Orders / Total Customers | 25,164 / 17,416 |
| Return Rate | 2.17% |
| Total Revenue / Total Cost / Total Profit | $24,914,567.18 / $14,456,871.39 / $10,457,695.79 |
| Average Revenue per Customer | $1,430.56 |
| Total Profit by year: 2020 / 2021 / 2022 (to June 30) | $2,601,602.73 / $3,967,075.69 / $3,889,017.38 |
| Orders by category: Accessories / Bikes / Clothing (sum 37,888; total 25,164) | 16,983 / 13,929 / 6,976 |
| Bike Returns / Bike Sales / Bike Return Rate | 429 / 13,929 / 3.08% |
| % of All Returns: Accessories / Bikes / Clothing | 61.82% / 23.47% / 14.72% |
| Red Sales (quantity) | 4,011 |
| Overall Average Price / High Ticket Orders | $714.44 / 11,312 |
| June 2022: Total Orders / Previous Month Orders / Order Target | 2,146 / 2,165 / 2,381.5 |
| June 2022: Total Profit / Profit Target / Revenue Target | $771,575.07 / $825,827.70 / $1,945,273.69 |
| 90-day Rolling Profit at 6/30/2022; YTD Revenue 2022 | $2,142,657.15; $9,185,437.85 |
| Adjusted Revenue / Adjusted Profit at +10% | $27,406,023.90 / $12,949,152.51 |
| Income Level: Very High / High / Average / Low | 300 / 1,843 / 8,201 / 7,804 |
| Parents (Yes / No); Priority customers | 13,068 / 5,080; 1,269 |
| Top customer by revenue (no filters) | Mr. Maurice Shan: 6 orders, $12,407.95 |
| Top customer, Skilled Manual, 2022 | Ruben Suarez, $4,682.67 (about $4,683) |
| Most ordered / most returned product type | Tires and Tubes (9,084 orders) / Tires and Tubes (534 returned) |
| Product 338 | Road-650 Black, 44; has sales, no returns |

### Step 9.5 - Common problems and fixes

| Problem | Fix |
|---|---|
| A date column shows errors | Change type using locale: Date, English (United States) (Step 3.12). Check Regional Settings (Step 2.3). |
| The same number repeats on every row | No relationship, or the field comes from the fact table. Use the dimension table field; check Model view. |
| A product shows no sales | A bi-directional filter from Returns Data. Set the relationship back to Single (Step 4.9). |
| A measure total does not equal the sum of its rows | Normal for DISTINCTCOUNT: an order can sit in several categories (Step 5.10). |
| Time intelligence returns blanks | The calendar must be continuous and related to the fact date column through Calendar Lookup[Date]. |
| Cannot create a second active date relationship | Deactivate the first. USERELATIONSHIP can use an inactive one inside a measure. |
| File path error after moving a CSV | `Home > Data source settings > Change source`, or use a parameter. |
| Settings reset in a new file | Current File options do not carry over; redo Step 2.3 Part B. |
| A relationship will not create | The key columns have different data types; fix the type in Power Query. |
| Anomaly detection button missing | Remove the forecast, legend and drill hierarchy; the X-axis must be a date field with at least four points. |
| A bookmark resets the slicers | Untick Data in that bookmark's options (Step 6.13). |
| The top-customer card shows the wrong name or total | Put CustomerKey (not Full Name) in the Top N filter and use the HASONEVALUE measures. |
| Month Short shows MON / TUE instead of JAN / FEB | It was built from Day Name; rebuild it from Month Name (Step 5.7). |

## Appendix A: DAX Quick Reference

| Name | Where | Formula (short) |
|---|---|---|
| Parent | Customer Lookup (column) | IF(TotalChildren > 0, "Yes", "No") |
| Customer Priority | Customer Lookup (column) | IF(Parent = "Yes" && AnnualIncome > 100000, "Priority", "Standard") |
| Income Level | Customer Lookup (column) | SWITCH(TRUE(), >=150000 Very High, >=100000 High, >=50000 Average, Low) |
| Education Category | Customer Lookup (column) | SWITCH on EducationLevel: High School / Undergrad / Graduate / Other |
| Birth Year | Customer Lookup (column) | YEAR(BirthDate) |
| Month Short | Calendar Lookup (column) | UPPER(LEFT(Month Name, 3)) |
| SKU Category | Product Lookup (column) | LEFT(ProductSKU, SEARCH("-", ProductSKU) - 1) |
| Quantity Sold | Measures Table | SUM(Sales Data[OrderQuantity]) |
| Quantity Returned / Total Returns | Measures Table | SUM(Returns Data[ReturnQuantity]) / [Quantity Returned] |
| Total Orders | Measures Table | DISTINCTCOUNT(Sales Data[OrderNumber]) |
| Total Customers | Measures Table | DISTINCTCOUNT(Sales Data[CustomerKey]) |
| Return Rate | Measures Table | DIVIDE([Quantity Returned], [Quantity Sold]) |
| Bike Returns / Bike Sales | Measures Table | CALCULATE(..., CategoryName = "Bikes") |
| Bike Return Rate | Measures Table | DIVIDE([Bike Returns], [Bike Sales]) |
| All Returns / % of All Returns | Measures Table | CALCULATE([Quantity Returned], ALL(Returns Data)) / DIVIDE(...) |
| Overall Average Price / High Ticket Orders | Measures Table | CALCULATE([Average Retail Price], ALL(Product Lookup)) / CALCULATE([Total Orders], FILTER(...)) |
| Total Revenue / Total Cost | Measures Table | SUMX(Sales Data, qty \* RELATED(price or cost)) |
| Total Profit | Measures Table | [Total Revenue] - [Total Cost] |
| Average Revenue per Customer | Measures Table | DIVIDE([Total Revenue], [Total Customers]) |
| Previous Month ... (Returns, Orders, Profit, Revenue) | Measures Table | CALCULATE(..., DATEADD(Date, -1, MONTH)) |
| Order / Profit / Revenue Target | Measures Table | [Previous Month ...] \* 1.1 |
| ... Target Gap | Measures Table | Actual - Target |
| 90-day Rolling Profit | Measures Table | CALCULATE([Total Profit], DATESINPERIOD(Date, MAX(Date), -90, DAY)) |
| Top Customer Name / Orders / Revenue | Measures Table | IF(HASONEVALUE(CustomerKey), value, "-") |
| Price Adjustment (%) Value | Parameter measure | SELECTEDVALUE(parameter column, 0) |
| Adjusted Revenue / Adjusted Profit | Measures Table | [Total Revenue] \* (1 + value) / [Adjusted Revenue] - [Total Cost] |

## Appendix B: Power Query Applied Steps Summary

| Query | Applied steps in order |
|---|---|
| Territory Lookup | Source, Promoted Headers, Changed Type |
| Product Lookup | Source, Promoted Headers, Changed Type, Change to currency (ProductCost, ProductPrice), Removed ProductSize, Inserted Text Before Delimiter (SKU Type, delimiter "-", number of delimiters 1), Replaced Value (ProductStyle 0 to NA) |
| Product Categories Lookup / Product Subcategories Lookup | Source, Promoted Headers, Changed Type |
| Customer Lookup | Source, Promoted Headers, Changed Type, Removed Errors, Removed empty CustomerKey rows, Duplicated EmailAddress (Domain Name), Text After Delimiter "@", Text Before Delimiter ".", Replaced "-" with space, Capitalize Each Word, Capitalized Prefix/FirstName/LastName, Merged Columns (Full Name) |
| Calendar Lookup | Source, Promoted Headers, Changed Type with Locale (Date, English United States), Day Name, Start of Week, End of Week, Start of Month, Start of Quarter, Start of Year, Year, Month Number, Month Name, types set |
| Sales Data | Source (Folder), Combine files, Changed Type (dates with locale if needed), Quantity Type (conditional column) |
| Returns Data | Source, Promoted Headers, Changed Type (ReturnDate as Date) |
| Rolling Calendar (demo) | Source (#date(2023,1,1)), Custom1 (List.Dates), Converted to Table, Renamed Columns, Changed Type, Month Name, Month Number, Start of Year, Year |
| Product Category Sales (Unpivot Demo) | Source, Promoted Headers, Changed Type, Unpivoted Columns, Renamed Columns (Region, Sales) |
| Sales Summary Demo | Duplicate of Sales Data, Grouped Rows (ProductKey, CustomerKey; Total Quantity = Sum of OrderQuantity); load off |

## Appendix C: Page Layout Reference (1280 x 720 canvas)

All values are x, y, width, height in pixels. Use `Format > General > Properties` to type them in.

#### Navigation bar (every main page)

| Object | x | y | Width | Height |
|---|---|---|---|---|
| Left Nav Background | 0 | 0 | 59 | 720 |
| AW Logo | 59 | 0 | 210 | 210 |
| Reset button (Exec Dashboard) | 0 | 0 | 79 | 55 |
| Filter icon button | 0 | 55 | 59 | 50 |
| Dashboard button | 0 | 494 | 59 | 49 |
| Map button | 0 | 549 | 59 | 49 |
| Product button | 0 | 605 | 59 | 49 |
| Customer button | 0 | 660 | 59 | 49 |

#### Exec Dashboard

| Object | x | y | Width | Height |
|---|---|---|---|---|
| KPI cards: Revenue / Profit / Orders / Return rate | 298 / 541 / 783 / 1026 | 18 | 210 | 147 |
| KPI backgrounds (rounded rectangles) | 310 / 553 / 795 / 1038 | 46 | 186 | 108 |
| Revenue Trending line chart | 79 | 176 | 635 | 315 |
| Orders by Category bar chart | 728 | 176 | 496 | 166 |
| KPI: Monthly Revenue | 124 | 524 | 175 | 169 |
| KPI: Monthly Orders | 322 | 524 | 175 | 169 |
| KPI: Monthly Returns | 540 | 524 | 175 | 169 |
| Top 10 Products matrix | 783 | 342 | 469 | 239 |
| Text box: Most Ordered Product Type | 778 | 586 | 176 | 46 |
| Text box: Most Returned Product Type | 1026 | 586 | 185 | 46 |
| Card: most ordered | 780 | 622 | 229 | 45 |
| Card: most returned | 1026 | 621 | 226 | 46 |
| Slicer panel: background | 0 | 0 | 311 | 720 |
| Slicer panel: Year slicer | 16 | 72 | 278 | 126 |
| Slicer panel: Continent slicer | 16 | 234 | 278 | 126 |
| Slicer panel: back arrow | 243 | 6 | 55 | 40 |

#### Map page

| Object | x | y | Width | Height |
|---|---|---|---|---|
| Continent slicer (horizontal) | 72 | 6 | 1208 | 94 |
| Map | 93 | 100 | 1187 | 593 |

#### Product Detail

| Object | x | y | Width | Height |
|---|---|---|---|---|
| Card: Selected Product | 78 | 46 | 237 | 135 |
| Gauge: Orders | 350 | 29 | 256 | 252 |
| Gauge: Revenue | 666 | 29 | 256 | 252 |
| Gauge: Profit | 982 | 29 | 256 | 252 |
| Slicer: Price Adjustment (%) | 78 | 315 | 237 | 155 |
| Line chart: Profit Trending | 331 | 251 | 949 | 220 |
| Slicer: Product Metric selection | 78 | 470 | 213 | 204 |
| Area chart: Returns Trending | 349 | 462 | 571 | 238 |
| Smart narrative | 971 | 518 | 309 | 181 |

#### Customer Detail

| Object | x | y | Width | Height |
|---|---|---|---|---|
| Card: Unique customers | 105 | 0 | 150 | 151 |
| Card: Revenue per customer | 105 | 114 | 150 | 151 |
| Tile slicer: Customer Metric selection | 312 | 0 | 949 | 65 |
| Line chart: Total customers | 312 | 79 | 949 | 221 |
| Donut: Orders by Income level | 63 | 266 | 260 | 212 |
| Donut: Orders by Occupation | 64 | 488 | 269 | 232 |
| Table: Top 100 customers | 323 | 300 | 446 | 396 |
| Year slicer (Between) | 827 | 300 | 300 | 73 |
| Top Customer text box / card | 785 / 785 | 372 / 410 | 191 / 476 | 38 / 67 |
| Orders text box / card | 785 / 786 | 496 / 520 | 191 / 164 | 38 / 94 |
| Revenue text box / card | 1049 / 1054 | 496 / 520 | 191 / 181 | 38 / 94 |
| Information button (insight bookmark) | 815 | 634 | 358 | 85 |
| Reset button | 0 | 0 | 100 | 40 |

#### Category Tooltip (425 x 225) and AI pages

| Object | x | y | Width | Height |
|---|---|---|---|---|
| Tooltip: Multi-row card | 10 | 0 | 140 | 225 |
| Tooltip: Area chart (Weekly Orders) | 150 | 0 | 248 | 225 |
| Q&A visual | 92 | 92 | 697 | 462 |
| Q&A page matrix | 890 | 190 | - | - |
| Decomposition tree | 56 | 98 | 994 | 485 |
| Decomposition tree card (Total Orders) | 1036 | 142 | 153 | 150 |
| Key influencers visual 1 (HomeOwner) | 10 | 0 | 710 | 704 |
| Key influencers visual 2 (ProductPrice) | 730 | 0 | 550 | 704 |

Course material belongs to Maven Analytics. This guide is an independent step-by-step walkthrough; it does not reproduce the course slides or videos.
