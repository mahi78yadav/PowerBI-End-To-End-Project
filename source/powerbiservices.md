
# Power BI Service — Step-by-Step Guide

**Purpose:** Learn Power BI Service for practical work and interview preparation.

> **Screen note:** The diagrams in this guide are simplified illustrations, not actual screenshots from your account. Microsoft's interface may change. Official Microsoft Learn links are provided for reference.

---

## 1. What Is Power BI Service?

Power BI Service is Microsoft's cloud platform for publishing, viewing, sharing, refreshing, and managing Power BI reports.

- **Power BI Desktop:** Build data models, write DAX, transform data, and design reports.
- **Power BI Service:** Publish reports, manage workspaces, share content, create dashboards, and configure refresh.
- **Power BI Mobile:** View reports and dashboards on mobile devices.

**Website:** https://app.powerbi.com/

Official documentation: https://learn.microsoft.com/power-bi/fundamentals/power-bi-service-overview

### Typical Power BI workflow

```text
Data Sources
     |
     v
Power BI Desktop
(Power Query + Data Model + DAX + Reports)
     |
     | Publish PBIX
     v
Power BI Service
     |
     +---- Workspace
     |
     +---- Report
     |
     +---- Semantic Model
     |
     +---- Scheduled Refresh
     |
     +---- Dashboard
     |
     +---- App / Report Sharing
```

### Important terms

| Term | Simple meaning |
|---|---|
| Workspace | A place to organize Power BI content |
| Report | One or more pages containing interactive visuals |
| Semantic model | Tables, relationships, measures, and model metadata |
| Dashboard | A single-page canvas containing pinned tiles |
| App | A packaged collection of content for report consumers |
| Gateway | A bridge between the Power BI Service and certain private-network data sources |
| RLS | Row-Level Security, which restricts which rows users can see |

**Note:** Older Power BI documentation often calls a semantic model a *dataset*.

---

## 2. Sign In to Power BI Service

### Steps

1. Open https://app.powerbi.com/.
2. Sign in using your work or school Microsoft account.
3. Select your organization or tenant if prompted.
4. Review the navigation and workspaces available to you.

### Screen illustration

```text
+---------------------------------------------------------+
| Power BI                                Search    Help  |
+----------------------+----------------------------------+
| Home                 |                                  |
| Create               |  Home                            |
| Browse               |                                  |
| Workspaces           |  Recent reports and content      |
| Apps                 |  may appear here                 |
+----------------------+----------------------------------+
```

*Illustration only. Menu names and positions can vary.*

**Practice:** Sign in and identify the Workspaces and Apps sections.

---

## 3. Create a Workspace

A workspace is where you organize and manage reports, semantic models, and dashboards.

### Steps

1. Open **Workspaces**.
2. Select **New workspace**.
3. Enter the name `ADW-SalesAnalytics`.
4. Add a description, for example:

   `AdventureWorks sales analytics learning project`

5. Configure any available workspace settings.
6. Select **Apply** or **Create**.

### Screen illustration

```text
+----------------------------------------------+
| Create a workspace                           |
+----------------------------------------------+
| Name:        ADW-SalesAnalytics              |
| Description: AdventureWorks learning project  |
|                                              |
| Advanced settings may appear here             |
|                                              |
|                         [Cancel] [Apply]     |
+----------------------------------------------+
```

**Remember:** Workspace creation and some advanced settings depend on your permissions and organization's configuration.

Official documentation:

https://learn.microsoft.com/power-bi/collaborate-share/service-create-the-new-workspaces

---

## 4. Publish a Report from Power BI Desktop

This is an important step for your `ADW-SalesAnalytics` project.

### Before publishing

1. Open your `.pbix` file in Power BI Desktop.
2. Select **Refresh** to check that the data loads successfully.
3. Verify relationships and DAX measures.
4. Check your report pages and visuals.
5. Save the `.pbix` file.

### Publishing steps

1. In Power BI Desktop, select **Home > Publish**.
2. Sign in if prompted.
3. Select the `ADW-SalesAnalytics` workspace.
4. Wait for the publishing confirmation.
5. Open the report in Power BI Service.

### Screen illustration

```text
Power BI Desktop
+------------------------------------------------------+
| Home  Insert  Modeling  View  Help                   |
|                                                      |
| [Get data] [Transform data] [Refresh] [Publish]      |
+------------------------------------------------------+
                         |
                         v
              Select a destination
              +-----------------------------+
              | My workspace                |
              | ADW-SalesAnalytics          |
              | Other available workspaces  |
              +-----------------------------+
```

### What gets published?

Publishing a PBIX generally publishes its report and semantic model to the selected workspace.

**Common mistake:** Publishing to My workspace when you intended to publish to your project workspace.

Official documentation:

https://learn.microsoft.com/power-bi/create-reports/desktop-upload-desktop-files

---

## 5. Find and Open Your Report

### Steps

1. Open Power BI Service.
2. Select **Workspaces**.
3. Open `ADW-SalesAnalytics`.
4. Find your report in the content list.
5. Select the report name.
6. Test its slicers, filters, and visuals.

### Screen illustration

```text
Workspace: ADW-SalesAnalytics

+-----------------------------------------------+
| Name                       | Type             |
+----------------------------+------------------+
| Sales Overview             | Report           |
| ADW-SalesAnalytics model    | Semantic model   |
+----------------------------+------------------+
```

The names above are examples. Your actual content names depend on your PBIX file.

**Practice:** Change a slicer and verify that the report visuals respond correctly.

---

## 6. Understand Reports and Semantic Models

A report and a semantic model are related but different.

| Item | Purpose |
|---|---|
| Report | Contains visuals, pages, slicers, and report interactions |
| Semantic model | Contains tables, columns, relationships, measures, and model logic |
| Dashboard | Contains pinned tiles on a single-page canvas |
| Workspace | Organizes content and manages access |

### Example for your project

Your report may contain:

- Sales Overview
- Product Analysis
- Customer Analysis
- Returns Analysis

Your semantic model may contain:

- Sales Data
- Returns Data
- Customer Lookup
- Product Lookup
- Product Categories Lookup
- Product Subcategories Lookup
- Territory Lookup
- Calendar Lookup

It also contains the relationships and DAX measures used by your report.

Official documentation:

https://learn.microsoft.com/power-bi/connect-data/service-datasets-understand

---

## 7. Refresh Data Manually

Use manual refresh when the source data has changed and you want the published semantic model to load the latest data.

### Steps

1. Open your workspace.
2. Find the semantic model.
3. Open its **More options (`...`)** menu.
4. Select **Refresh now**. The location of this option may vary.
5. Wait for the refresh to complete.
6. Open the report and check the updated values.

### Screen illustration

```text
Workspace content

ADW-SalesAnalytics model       [...]

                               +-------------------+
                               | Refresh now       |
                               | Settings          |
                               | Refresh history   |
                               +-------------------+
```

**Important difference:**

- Refresh in Power BI Desktop updates the local PBIX model.
- Refresh in Power BI Service updates the published semantic model.

The Service needs valid credentials and access to the configured source.

Official documentation:

https://learn.microsoft.com/power-bi/connect-data/refresh-data

---

## 8. Configure Scheduled Refresh

Scheduled refresh automatically updates an Import-mode semantic model at configured times.

### Steps

1. Open your workspace.
2. Find the semantic model.
3. Open **Settings**.
4. Review **Gateway and cloud connections**, if shown.
5. Configure **Data source credentials** and sign in if required.
6. Find **Refresh** or **Schedule refresh**.
7. Turn scheduled refresh on.
8. Select the available frequency and time slots.
9. Configure failure notifications if available.
10. Save the settings.
11. Test with **Refresh now** and inspect refresh history.

### Screen illustration

```text
Semantic model settings

+-----------------------------------------------+
| Gateway and cloud connections                 |
|   Status: Configured / Not ready              |
|                                               |
| Data source credentials                       |
|   Status: Signed in / Sign in required        |
|                                               |
| Refresh                                       |
|   Scheduled refresh: [ On ]                   |
|   Frequency:        [ Daily       v ]         |
|   Time zone:        [ Select      v ]         |
|   Time slots:       [ Add time ]              |
|                                               |
|                              [Apply]          |
+-----------------------------------------------+
```

*Illustration only. Options vary by source, storage mode, capacity, and tenant settings.*

### Interview points

- **Import mode:** Data is loaded into the semantic model and must be refreshed to bring in new source data.
- **DirectQuery:** Visual queries generally go to the source; it does not refresh imported data in the same way.
- **Cloud sources:** May connect directly, depending on the source and configuration.
- **On-premises sources:** May require a gateway.
- **Refresh limits:** Depend on license, capacity, and current Microsoft service rules. Confirm the current limits in Microsoft Learn rather than memorizing a number without context.

Official documentation:

https://learn.microsoft.com/power-bi/connect-data/refresh-scheduled-refresh

---

## 9. Understand the Data Gateway

A gateway allows Power BI Service to reach supported data sources that are not directly accessible from the cloud.

### Simple architecture

```text
Power BI Service
      |
      | Secure connection
      v
On-premises Data Gateway
      |
      v
Private Network Data Source
(SQL Server / supported source)
```

### Basic setup

1. Install the on-premises data gateway on a supported, always-on computer or server.
2. Sign in using the appropriate organizational account.
3. Register the gateway.
4. Configure the data source and credentials.
5. Map the semantic model's connection to the gateway.
6. Confirm that the gateway is online.
7. Test a refresh.

### Important for your CSV project

If your CSV files are stored only on your local computer, Power BI Service cannot reliably access a local path such as:

`C:\Users\YourName\Documents\Sales.csv`

after publishing.

Possible solutions include moving the files to a supported cloud location or configuring a gateway for a supported local/network source.

Official documentation:

https://learn.microsoft.com/data-integration/gateway/service-gateway-onprem

---

## 10. View Refresh History and Troubleshoot Errors

### Steps

1. Open the workspace.
2. Find the semantic model.
3. Open **More options (`...`)** or the model's details page.
4. Select **Refresh history**.
5. Check the status, duration, and error details.
6. Resolve the cause and try again.

### Screen illustration

```text
Refresh history

+-------------------------------------------------------+
| Start time      | Status  | Duration | Details        |
+-----------------+---------+----------+----------------+
| 18-Oct 06:00    | Success | 00:02:10 | Completed      |
| 17-Oct 06:00    | Failed  | 00:00:18 | Check error    |
+-----------------+---------+----------+----------------+
```

The rows above are examples, not real refresh records.

### Common causes of failure

- Incorrect or expired credentials
- Gateway offline
- Source file moved or renamed
- Source column names or data types changed
- Source unavailable
- Required permissions removed

**Interview tip:** Explain how you would check refresh history, inspect the error, validate credentials and gateway status, verify the source, and retry.

Official documentation:

https://learn.microsoft.com/power-bi/connect-data/refresh-data

---

## 11. Share a Report

Share reports only with people who should have access to the data.

### Steps

1. Open the report in Power BI Service.
2. Select **Share**.
3. Enter the recipient's name or email address.
4. Review the permission options.
5. Grant only the access required.
6. Select **Send**.

### Screen illustration

```text
Share report

+-----------------------------------------------+
| Add people or groups                          |
| [ person@company.com                       ]  |
|                                               |
| Permission options may include:               |
| [ ] Allow recipients to reshare               |
| [ ] Allow recipients to build content         |
|                                               |
|                                 [Send]        |
+-----------------------------------------------+
```

The available options depend on your organization's configuration, license, and permissions.

### Important points

- Users may need access to both the report and its underlying semantic model.
- Sharing a report is not a replacement for Row-Level Security.
- Licensing or capacity requirements can apply to report viewers.

Official documentation:

https://learn.microsoft.com/power-bi/collaborate-share/service-share-dashboards

---

## 12. Create a Dashboard by Pinning a Visual

A dashboard is a single-page canvas in Power BI Service. You can pin supported visuals from reports to it.

### Steps

1. Open a report in Power BI Service.
2. Hover over a visual.
3. Select **Pin visual**, if available.
4. Choose **New dashboard** or an existing dashboard.
5. Enter a name, such as `ADW Sales Executive Dashboard`.
6. Select **Pin**.
7. Open the dashboard and arrange the tiles.

### Screen illustration

```text
ADW Sales Executive Dashboard

+---------------------------------------------------+
| [Total Revenue] [Total Profit] [Total Orders]     |
|                                                   |
| [Monthly Sales Trend]       [Top Products]        |
|                                                   |
| [Returns KPI]               [Customer KPI]        |
+---------------------------------------------------+
```

This is an example layout, not a real dashboard screenshot.

### Report vs dashboard

- **Report:** Can have multiple pages, slicers, filters, and interactive visuals.
- **Dashboard:** A single-page collection of pinned tiles in the Service.

**Tip:** Pin important KPIs and summary visuals instead of every visual.

Official documentation:

https://learn.microsoft.com/power-bi/create-reports/service-dashboard-pin-tile-from-report

---

## 13. Publish a Power BI App

An app is useful when you want to distribute a curated set of reports and dashboards to consumers.

### Steps

1. Open the workspace containing your reports.
2. Select **Create app** or **Update app**, depending on the current interface.
3. Enter the app name and description.
4. Choose the reports and dashboards to include.
5. Configure the audience and access settings.
6. Publish or update the app.
7. Share the app link with the intended audience.

### Screen illustration

```text
Create / update app

+-----------------------------------------------+
| App name: ADW Sales Analytics                 |
| Description: Sales reporting for stakeholders|
|                                               |
| Content                                       |
| [x] Sales Overview                            |
| [x] Product Analysis                          |
| [x] Customer Analysis                         |
|                                               |
| Audience / Access                             |
| [Choose intended users or groups]             |
|                                               |
|                           [Publish app]       |
+-----------------------------------------------+
```

### Workspace vs app

- **Workspace:** Where authors maintain and collaborate on content.
- **App:** The packaged experience that consumers use.

Official documentation:

https://learn.microsoft.com/power-bi/collaborate-share/service-create-distribute-apps

---

## 14. Understand Workspace Roles

Workspace roles control what people can do within a workspace.

| Role | General purpose |
|---|---|
| Admin | Manage the workspace, access, and content |
| Member | Collaborate and publish or update content |
| Contributor | Create and edit content |
| Viewer | View workspace content, subject to permissions and security |

Actual capabilities depend on the current product rules, license, and capacity.

### Manage workspace access

1. Open the workspace.
2. Select **Manage access** or the workspace access settings.
3. Add a person or group.
4. Assign the appropriate role.
5. Confirm the change.

**Best practice:** Give each person only the access they need.

Official documentation:

https://learn.microsoft.com/power-bi/collaborate-share/service-roles-new-workspaces

---

## 15. Understand Row-Level Security (RLS)

RLS restricts which rows a user can see.

**Example:** A regional manager should see only the sales for their own territory.

### Typical workflow

1. In Power BI Desktop, select **Modeling > Manage roles**.
2. Create a role.
3. Add a DAX filter rule to the relevant table.
4. Test the role using **View as**.
5. Publish the model.
6. In Power BI Service, open the semantic model's security settings.
7. Assign users or groups to the appropriate roles.
8. Test with an authorized account where possible.

### Important

Hiding a column or adding a slicer does not provide security. Use RLS when users must be restricted to particular data rows.

The exact DAX rule depends on the data model and how users are mapped to regions or territories.

Official documentation:

https://learn.microsoft.com/power-bi/enterprise/service-admin-rls

---

## 16. Other Useful Power BI Service Features

| Feature | Purpose |
|---|---|
| Lineage view | Shows upstream data sources and downstream content |
| Endorsement | Marks trusted or promoted content, if enabled |
| Usage metrics | Helps understand report usage, where available |
| Sensitivity labels | Applies organizational data-classification labels, if configured |
| Subscriptions | Sends report or dashboard snapshots by email, where supported |
| Alerts | Sets alerts on supported dashboard tiles |
| Comments | Allows discussion of report content, where available |
| Export | Exports data or report content when permitted |

Options depend on the item type, license, tenant settings, and permissions.

---

## 17. Power BI Service Interview Questions

### Q1. What is Power BI Service?

A cloud service used to publish, view, share, refresh, and manage Power BI content.

### Q2. What is the difference between Desktop and Service?

Desktop is mainly used to build data models and reports. Service is mainly used for publishing, sharing, refresh, workspaces, apps, and cloud administration.

### Q3. What happens when you publish a PBIX?

The report and semantic model are generally published to the selected workspace, depending on the content and publishing method.

### Q4. What is a workspace?

A collaborative container for Power BI content, with roles controlling what members can do.

### Q5. What is a semantic model?

The data model containing tables, relationships, measures, and metadata used by reports.

### Q6. What is the difference between a report and a dashboard?

A report can contain multiple pages and interactive visuals. A dashboard is a single-page canvas in the Service containing pinned tiles.

### Q7. What is scheduled refresh?

An automatic process that updates an Import-mode semantic model from its source at configured times.

### Q8. When is a gateway needed?

When the Service needs a secure bridge to reach a supported data source it cannot access directly, commonly a private-network or on-premises source.

### Q9. Why can refresh fail?

Common causes include invalid credentials, an offline gateway, missing source files, schema changes, or connectivity issues.

### Q10. What is a Power BI app?

A curated package of reports and dashboards distributed to consumers.

### Q11. What is RLS?

Row-Level Security restricts which rows users can see based on role filters.

### Q12. Does refreshing in Desktop refresh the published report?

No. Desktop refresh updates the local PBIX model. The published semantic model must be refreshed in the Service or through an appropriate automated process.

### Q13. What is the difference between Import and DirectQuery?

- **Import:** Data is loaded into the semantic model; refresh is needed to bring in later source changes.
- **DirectQuery:** Queries generally go to the source when report visuals need data, subject to caching and product behavior.

### Q14. What is the difference between sharing a report and publishing an app?

Sharing grants selected users access to content. An app packages selected workspace content into a curated experience for an audience.

### Q15. How would you troubleshoot a failed refresh?

Check refresh history, read the error, verify credentials and gateway status, confirm source availability and schema, then retry and validate the result.

---

## 18. Practice Exercise — ADW-SalesAnalytics

Complete these tasks after publishing your AdventureWorks report.

- [ ] Sign in to Power BI Service.
- [ ] Create or open the `ADW-SalesAnalytics` workspace.
- [ ] Publish your PBIX file to the workspace.
- [ ] Open the report and test slicers.
- [ ] Locate the semantic model.
- [ ] Run **Refresh now** and inspect the result.
- [ ] Open refresh history.
- [ ] Configure scheduled refresh if your source and license support it.
- [ ] Pin Total Revenue and Total Profit visuals to a dashboard.
- [ ] Review workspace roles and least-privilege access.
- [ ] Learn how to publish an app.
- [ ] Understand how RLS roles are defined and assigned.
- [ ] Explain workspace, report, semantic model, dashboard, app, gateway, and RLS without looking at your notes.

---

## Official Microsoft Learn References

1. Power BI Service overview — https://learn.microsoft.com/power-bi/fundamentals/power-bi-service-overview
2. Create workspaces — https://learn.microsoft.com/power-bi/collaborate-share/service-create-the-new-workspaces
3. Publish from Desktop — https://learn.microsoft.com/power-bi/create-reports/desktop-upload-desktop-files
4. Semantic models — https://learn.microsoft.com/power-bi/connect-data/service-datasets-understand
5. Data refresh — https://learn.microsoft.com/power-bi/connect-data/refresh-data
6. Scheduled refresh — https://learn.microsoft.com/power-bi/connect-data/refresh-scheduled-refresh
7. Gateway — https://learn.microsoft.com/data-integration/gateway/service-gateway-onprem
8. Sharing — https://learn.microsoft.com/power-bi/collaborate-share/service-share-dashboards
9. Pin visuals to dashboards — https://learn.microsoft.com/power-bi/create-reports/service-dashboard-pin-tile-from-report
10. Create and distribute apps — https://learn.microsoft.com/power-bi/collaborate-share/service-create-distribute-apps
11. Workspace roles — https://learn.microsoft.com/power-bi/collaborate-share/service-roles-new-workspaces
12. Row-Level Security — https://learn.microsoft.com/power-bi/enterprise/service-admin-rls
