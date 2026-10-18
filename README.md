# PowerBI-End-To-End-Project


# ADW-SalesAnalytics — Power BI Implementation Guide

## 1. Application Creation Module

### 1.1 Create Power BI Project

1. Open Power BI Desktop.
2. Select **File → New**.
3. Save the project as `ADW-SalesAnalytics.pbix`.

### 1.2 Configure Global Options

1. Navigate to **File → Options and settings → Options**.
2. Select **Global → Preview features**.
3. Enable all preview features as required by the project.
4. Click **OK** and restart Power BI Desktop if prompted.

### 1.3 Configure Current File Options

1. Navigate to **File → Options and settings → Options → Current File → Data Load**.
2. Under Relationships, disable automatic relationship detection and creation options where available.
3. Under Time Intelligence, disable automatic date/time options as required.
4. Navigate to **Current File → Regional Settings**.
5. Set Locale for import to **English (United States)**.
6. Click **OK** and save the project.

---

## 2. Data Transformation Module

### 2.1 Source Files

Source repository:

https://github.com/mahi78yadav/PowerBI-End-To-End-Project/tree/main/source

Download the required CSV files from the `source` folder.

In Power BI Desktop:

1. Select **Home → Get Data → Text/CSV**.
2. Select the required file.
3. Click **Transform Data**.
4. Perform the transformations below in Power Query Editor.

### 2.2 Territory Lookup

Source: `AdventureWorks Territory Lookup.csv`

1. Rename the query to `Territory Lookup`.
2. Set the appropriate data types:
   - Sales Territory Key: Whole Number.
   - Continent: Text.
   - Country: Text.
   - Region: Text, if available.
3. Validate the territory key for nulls and duplicates.
4. Select **Home → Close & Apply**.

### 2.3 Product Lookup

Source: `AdventureWorks Product Lookup.csv`

1. Rename the query to `Product Lookup`.
2. Set Product Cost and Product Price to Currency.
3. Remove the `Product Size` column.
4. Create SKU Type:
   1. Right-click `Product SKU`.
   2. Select **Duplicate Column**.
   3. Rename the duplicate to `SKU Type`.
   4. Select the new column.
   5. Navigate to **Transform → Extract → Text Before Delimiter**.
   6. Configure the delimiter according to the source SKU format.
   7. Open the applied step settings and configure the number of delimiters to `1` under Advanced, if supported by the selected operation.
   8. Validate the result against sample SKU values.
5. Replace Product Style:
   1. Select `Product Style`.
   2. Navigate to **Transform → Replace Values**.
   3. Replace the exact value `0` with `NA`.
   4. Verify that unrelated values are not modified.
6. Validate data types:
   - Product Key: Whole Number.
   - Product Subcategory Key: Whole Number.
   - Product SKU: Text.
   - Product Name: Text.
   - Product Cost: Currency.
   - Product Price: Currency.
   - Product Style: Text.
7. Confirm Product Key is unique.
8. Select **Close & Apply**.

### 2.4 Product Categories Lookup

Source: `AdventureWorks Product Categories Lookup.csv`

1. Rename the query to `Product Categories Lookup`.
2. Set Product Category Key to Whole Number.
3. Set category names and descriptions to Text.
4. Validate that the category key is unique.
5. Select **Close & Apply**.

### 2.5 Product Subcategories Lookup

Source: `AdventureWorks Product Subcategories Lookup.csv`

1. Rename the query to `Product Subcategories Lookup`.
2. Set Product Subcategory Key and Product Category Key to Whole Number.
3. Set subcategory names and descriptions to Text.
4. Validate that Product Subcategory Key is unique.
5. Select **Close & Apply**.

### 2.6 Customer Lookup

Source: `AdventureWorks Customer Lookup.csv`

1. Rename the query to `Customer Lookup`.
2. Enable data profiling:
   - Select **View → Column quality**.
   - Select **View → Column distribution**.
   - Select **View → Column profile**.
   - Change profiling from the default sample to **Entire dataset**.
3. Review errors, nulls, distinct values, and unique values.
4. Create Domain name:
   1. Right-click `Email Address` and select **Duplicate Column**.
   2. Rename the duplicate to `Domain name`.
   3. Select **Transform → Extract → Text After Delimiter**.
   4. Set the delimiter to `@`.
   5. Select **Transform → Extract → Text Before Delimiter**.
   6. Set the delimiter to `.`.
   7. Replace `-` with a space using **Transform → Replace Values**.
   8. Select **Transform → Format → Capitalize Each Word**.
   9. Validate the output.

   **Note:** Text Before Delimiter extracts only the first segment before a period. For example, `mail.example.com` becomes `mail`. Omit this step if the requirement is to retain the full email domain.

5. Create Full Name:
   1. Select `Prefix`, `FirstName`, and `LastName` in that order.
   2. Use Ctrl-click to select multiple columns.
   3. Select **Transform → Merge Columns**.
   4. Choose a space as the separator.
   5. Name the result `Full Name`.
   6. Verify that the original columns are retained if needed.
6. Validate data types:
   - Customer Key: Whole Number.
   - Prefix: Text.
   - FirstName: Text.
   - LastName: Text.
   - Email Address: Text.
   - Domain name: Text.
   - Full Name: Text.
7. Confirm Customer Key is unique.
8. Select **Close & Apply**.

### 2.7 Calendar Lookup

Source: `AdventureWorks Calendar Lookup.csv`

1. Rename the query to `Calendar Lookup`.
2. Locate the source date column and set its data type to Date.
3. Select the date column before each transformation.
4. Create the following columns using **Add Column → Date**:

| Operation | Power Query option | New column name | Data type |
|---|---|---|---|
| Day | Day → Name of Day | Day Name | Text |
| Week | Week → Start of Week | Start of week | Date |
| Week | Week → End of Week | End of week | Date |
| Month | Month → Start of Month | Start of month | Date |
| Quarter | Quarter → Start of Quarter | Start of Quarter | Date |
| Year | Year → Start of Year | Start of Year | Date |
| Month | Month → Month | Month Number | Whole Number |
| Month | Month → Name of Month | Month Name | Text |

5. Validate all generated column data types.
6. Confirm that Date contains unique dates and covers the required reporting period.
7. Select **Close & Apply**.

### 2.8 Combine Sales Data

Source files:

- `AdventureWorks Sales Data 2020.csv`
- `AdventureWorks Sales Data 2021.csv`
- `AdventureWorks Sales Data 2022.csv`

1. Place all three CSV files in a dedicated folder.
2. Select **Home → Get Data → Folder**.
3. Select the folder containing the three files.
4. Filter the file list to include only the required sales files.
5. Select **Combine → Combine & Transform Data**.
6. Confirm the delimiter and sample file.
7. Rename the resulting query to `Sales Data`.
8. Validate the data types:

| Column | Expected data type |
|---|---|
| Order Date | Date |
| Stock Date | Date |
| Customer Key | Whole Number |
| Product Key | Whole Number |
| Territory Key | Whole Number |
| Quantity | Whole Number |
| Sales amount | Currency |
| Cost and price columns | Currency |
| Order Number | Text, if used as an identifier |

9. Create Quantity Type:
   1. Select **Add Column → Conditional Column**.
   2. Set the column name to `Quantity Type`.
   3. Configure these rules:

| Condition | Output |
|---|---|
| Quantity equals 1 | Single item |
| Otherwise, Quantity is greater than 1 | Multiple |
| Else | Other |

4. Confirm the rules are in the correct order.
5. Validate quantities of zero, one, and greater than one.
6. Confirm that data from all three years is included without unintended duplication.
7. Select **Close & Apply**.

### 2.9 Returns Data

Source: `AdventureWorks Returns Data.csv`

1. Select **Home → Get Data → Text/CSV**.
2. Select the returns file and click **Transform Data**.
3. Rename the query to `Returns Data`.
4. Set the returns date column to Date.
5. Set Product Key and Territory Key to Whole Number.
6. Set return quantity to Whole Number.
7. Set descriptive columns to Text.
8. Validate the product and territory keys against their lookup tables.
9. Select **Close & Apply**.

### 2.10 Create Rolling Calendar

1. Open **Home → Transform Data**.
2. Select **Home → New Source → Blank Query**.
3. Rename the query to `Rolling calendar`.
4. Open **Home → Advanced Editor**.
5. Enter the following Power Query M code:

```powerquery
let
    Source = #date(2023, 1, 1),
    Today = Date.From(DateTime.LocalNow()),
    NumberOfDays = Duration.Days(Today - Source) + 1,
    DateList = List.Dates(
        Source,
        NumberOfDays,
        #duration(1, 0, 0, 0)
    ),
    ToTable = Table.FromList(
        DateList,
        Splitter.SplitByNothing(),
        {"Date"}
    ),
    SetType = Table.TransformColumnTypes(
        ToTable,
        {{"Date", type date}}
    )
in
    SetType
```

6. Click **Done**.
7. Verify that the query returns one row per day from 1 January 2023 through the current local date.
8. Add required calendar attributes if this query will serve as a reporting date dimension.
9. Avoid maintaining competing date dimensions without a clear reporting requirement.
10. Select **Close & Apply**.

---

## 3. Data Modeling Module

### 3.1 Create Relationships

1. Open **Modeling → Manage relationships**.
2. Select **New**.
3. Select the one-side table and its key column.
4. Select the many-side table and its matching key column.
5. Set cardinality to **One-to-many (1:*)** where appropriate.
6. Set cross-filter direction to **Single** by default.
7. Configure the active/inactive status according to the relationship table below.
8. Select **OK**.
9. Repeat for all required relationships.

### 3.2 Entity Relationship Table

| No. | One-side table | One-side column | Many-side table | Many-side column | Cardinality | Status | Filter direction |
|---:|---|---|---|---|---|---|---|
| 1 | Calendar Lookup | Date | Sales Data | Order Date | 1:* | Active | Single |
| 2 | Calendar Lookup | Date | Sales Data | Stock Date | 1:* | Inactive | Single |
| 3 | Calendar Lookup | Date | Returns Data | Returns Date | 1:* | Active | Single |
| 4 | Customer Lookup | Customer Key | Sales Data | Customer Key | 1:* | Active | Single |
| 5 | Product Lookup | Product Key | Sales Data | Product Key | 1:* | Active | Single |
| 6 | Product Lookup | Product Key | Returns Data | Product Key | 1:* | Active | Single |
| 7 | Territory Lookup | Sales Territory Key | Sales Data | Territory Key | 1:* | Active | Single |
| 8 | Territory Lookup | Sales Territory Key | Returns Data | Territory Key | 1:* | Active | Single |
| 9 | Product Subcategories Lookup | Product Subcategory Key | Product Lookup | Product Subcategory Key | 1:* | Active | Single |
| 10 | Product Categories Lookup | Product Category Key | Product Subcategories Lookup | Product Category Key | 1:* | Active | Single |

#### Relationship validation

1. Confirm that keys on the one side are unique.
2. Confirm that related columns have compatible data types.
3. Investigate null and unmatched keys.
4. Use exact source column names when creating relationships.
5. Keep the Stock Date relationship inactive because Order Date is the active relationship between Calendar Lookup and Sales Data.
6. Use `USERELATIONSHIP` in DAX measures when Stock Date analysis is required.
7. Do not change a relationship to many-to-many simply because Power BI rejects a proposed one-to-many relationship.

### 3.3 Relationship Cardinality

#### One-to-Many (1:*)

One lookup record can match multiple records in a fact table.

Example: One customer can make many purchases.

**Customer Lookup**

| Customer Key | Customer Name |
|---:|---|
| 101 | Ravi Kumar |
| 102 | Sita Reddy |

**Sales Data**

| Sales ID | Customer Key | Sales Amount |
|---|---:|---:|
| S001 | 101 | 1000 |
| S002 | 101 | 2500 |
| S003 | 102 | 1200 |
| S004 | 101 | 800 |

Customer 101 has three sales records. Therefore, Customer Lookup to Sales Data is one-to-many.

#### One-to-One (1:1)

Each key occurs at most once in each table.

**Customer Master**

| Customer Key | Customer Name |
|---:|---|
| 101 | Ravi Kumar |
| 102 | Sita Reddy |

**Customer Profile**

| Customer Key | Preferred Language |
|---:|---|
| 101 | Telugu |
| 102 | English |

Both tables contain one record per customer. This is a one-to-one relationship if both keys are unique.

#### Many-to-Many (*:*)

A key can occur multiple times on both sides.

Example: Students can attend multiple courses, and each course can have multiple students.

**Students**

| Student ID | Student Name |
|---|---|
| ST01 | Ravi |
| ST02 | Sita |

**Courses**

| Course ID | Course Name |
|---|---|
| C01 | Power BI |
| C02 | Azure Data Engineering |

In a Power BI model, use a bridge table such as `Student Course Enrollment` when appropriate to represent the student-course combinations.

**Project rule:** Customer Lookup to Sales Data should be one-to-many because Customer Key should be unique in Customer Lookup and can repeat in Sales Data.

### 3.4 Single-Direction vs Bidirectional Filtering

#### Single-Direction Filtering

- Filters flow from the one-side dimension to the many-side fact table.
- Selecting a customer filters the related Sales Data rows.
- This is the recommended default for the project.
- It helps reduce ambiguous filter paths.

#### Bidirectional Filtering (Both)

- Filters can flow in both directions across a relationship.
- It can be useful for certain bridge-table and analytical scenarios.
- It may cause ambiguous filter paths, unexpected totals, and performance issues.
- Enable it only when required and test the affected visuals and measures.

| Concept | Meaning | Example |
|---|---|---|
| Cardinality | How records match | One-to-many |
| Cross-filter direction | How filters propagate | Single or Both |
| Active status | Which relationship is used by default | Active or Inactive |

Cardinality and cross-filter direction are separate settings.

### 3.5 Validate the Data Model

1. Open Model view.
2. Verify that the relationship diagram matches the relationship table.
3. Confirm that the Stock Date relationship is inactive.
4. Confirm that all lookup keys are unique.
5. Create test visuals:
   - Customer Name with Sales Amount.
   - Product Name with Sales Amount.
   - Continent and Country with Sales Amount.
   - Product Category, Product Subcategory, and Product Name.
   - Calendar Date with Sales Amount.
   - Calendar Date with Return Quantity.
6. Select dimension values and confirm that the correct fact-table data changes.
7. Save the PBIX file.

---

## 4. Data Categories and Hierarchies

### 4.1 Configure Territory Data Categories

1. Open Data view or Model view.
2. Select `Territory Lookup[Continent]`.
3. On the Column tools ribbon, set **Data category → Continent**.
4. Select `Territory Lookup[Country]`.
5. Set **Data category → Country/Region**.
6. Verify that the values are standardized for geographic visuals.

### 4.2 Create Geography Hierarchy

1. Locate `Territory Lookup[Continent]` in the Data/Fields pane.
2. Right-click and select **Create hierarchy**.
3. Rename the hierarchy to `Geography Hierarchy`.
4. Add `Territory Lookup[Country]` below Continent.
5. Add Region or State if available and required.
6. Test the hierarchy in a visual by expanding from Continent to Country.

### 4.3 Create Calendar Hierarchy

1. Locate `Calendar Lookup[Start of Year]`.
2. Right-click and select **Create hierarchy**.
3. Rename it to `Calendar Hierarchy`.
4. Add the following levels in order:

| Level | Column |
|---:|---|
| 1 | Start of Year |
| 2 | Start of month |
| 3 | Start of week |
| 4 | Date |

5. Confirm that all date columns have the Date data type.
6. Test the hierarchy in a matrix or chart.
7. If Month Name is used in another hierarchy, sort it by Month Number.

---

## 5. Final Validation Checklist

- [ ] Project saved as `ADW-SalesAnalytics.pbix`.
- [ ] Global and current-file options configured.
- [ ] All required CSV files imported successfully.
- [ ] Queries renamed correctly.
- [ ] Data types validated.
- [ ] Customer data profiling completed against the entire dataset.
- [ ] Product Cost and Product Price set to Currency.
- [ ] Product Size removed.
- [ ] SKU Type transformation validated.
- [ ] Product Style replacement validated.
- [ ] Domain name and Full Name transformations validated.
- [ ] Calendar Lookup attributes created.
- [ ] Sales files for 2020, 2021, and 2022 combined.
- [ ] Quantity Type column created and validated.
- [ ] Returns Data loaded and validated.
- [ ] Rolling calendar query created.
- [ ] Relationships created according to the relationship table.
- [ ] Stock Date relationship remains inactive.
- [ ] Single-direction filtering used by default.
- [ ] Geographic data categories configured.
- [ ] Geography Hierarchy created.
- [ ] Calendar Hierarchy created.
- [ ] Test visuals confirm expected filter behavior.
- [ ] PBIX file saved after validation.
