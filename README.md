# Power BI Azure Sales Analytics Dashboard

## Project Overview

This project demonstrates an end-to-end Business Intelligence solution using Microsoft Azure and Power BI.

The objective of the project is to collect sales data, store it in Azure SQL Database, perform data modeling and analysis, and visualize business insights through interactive Power BI dashboards.

The solution simulates a real-world cloud analytics platform where business users can monitor sales performance, customer behavior, product trends, and operational metrics through self-service reporting.

---

## Business Scenario

A retail organization wants to gain better visibility into:

- Revenue performance
- Product sales trends
- Customer purchasing behavior
- Payment status
- Delivery status
- Regional sales distribution

To achieve this, sales data is stored in Azure SQL Database and connected to Power BI for reporting and analytics.

---

## Solution Architecture

```text
Sales Data
    ↓
Azure SQL Database
    ↓
Power BI Desktop
    ↓
Interactive Dashboards
```

---

## Technologies Used

- Microsoft Azure
- Azure Resource Groups
- Azure SQL Database
- Azure SQL Server
- SQL Query Editor
- Power BI Desktop
- Power Query
- DAX
- GitHub

---

## Azure Resources Deployed

### Resource Group

Resource group created to contain all project resources.

**Resource Group Name**

```text
rg-powerbi-sales-project
```

**Screenshot**

```text
screenshots/01-resource-group-created.png
```

---

### Azure SQL Server

Logical SQL server created to host the Azure SQL Database.

**Server Name**

```text
sql-sales-mrigakshi
```

**Region**

```text
West Europe
```

**Screenshot**

```text
screenshots/02-sql-server-created.png
```

---

### Azure SQL Database

Cloud-hosted relational database used for storing sales data.

**Database Name**

```text
sqldb-sales-analytics
```

**Screenshot**

```text
screenshots/03-sql-database-created.png
```

---

### Firewall Configuration

Network access configured to allow Azure services and local machine connectivity.

**Configuration**

- Public Endpoint Enabled
- Azure Services Access Enabled
- Client IP Added

**Screenshot**

```text
screenshots/04-firewall-configuration.png
```

---

## Database Design

A Sales table was created to store transactional sales information.

### Sales Table Structure

| Column | Data Type |
|----------|----------|
| OrderID | INT |
| OrderDate | DATE |
| CustomerName | VARCHAR(100) |
| Country | VARCHAR(50) |
| Product | VARCHAR(100) |
| Category | VARCHAR(50) |
| Quantity | INT |
| UnitPrice | DECIMAL |
| Revenue | DECIMAL |
| PaymentStatus | VARCHAR(50) |
| DeliveryStatus | VARCHAR(50) |

---

### SQL Table Creation

SQL script executed through Azure Query Editor.

**Screenshot**

```text
screenshots/05-sales-table-created.png
```

---

### Sample Data Insertion

Sample sales records were inserted into the Sales table for reporting purposes.

**Screenshot**

```text
screenshots/06-sales-data-inserted.png
```

---

### Data Validation

SQL query executed to verify data integrity.

```sql
SELECT * FROM Sales;
```

**Screenshot**

```text
screenshots/07-sales-data-validation.png
```

---

## Power BI Development

Power BI Desktop was connected directly to Azure SQL Database.

### Azure SQL Connection

Data imported from Azure SQL Database.

**Screenshot**

```text
screenshots/08-powerbi-sql-connection.png
```

---

### Power Query Transformations

Data types and formatting were validated using Power Query.

Activities performed:

- Date formatting
- Numeric validation
- Data cleansing
- Column verification

**Screenshot**

```text
screenshots/09-power-query-transformations.png
```

---

## DAX Measures Created

### Total Revenue

```DAX
Total Revenue = SUM(Sales[Revenue])
```

### Total Orders

```DAX
Total Orders = COUNT(Sales[OrderID])
```

### Average Order Value

```DAX
Average Order Value =
DIVIDE([Total Revenue],[Total Orders])
```

### Total Quantity Sold

```DAX
Total Quantity Sold =
SUM(Sales[Quantity])
```

**Screenshot**

```text
screenshots/10-dax-measures-created.png
```

---

# Dashboard 1 — Sales Overview

## Objective

Provide a high-level summary of business performance.

### Visualizations

- Total Revenue KPI
- Total Orders KPI
- Average Order Value KPI
- Revenue by Product
- Revenue by Country
- Monthly Revenue Trend

### Key Insights

- Monitor business growth
- Identify revenue trends
- Compare sales across countries

**Screenshot**

```text
screenshots/11-sales-overview-dashboard.png
```

---

# Dashboard 2 — Product Performance

## Objective

Analyze product and category performance.

### Visualizations

- Revenue by Category
- Quantity Sold by Product
- Product Revenue Ranking
- Category Contribution

### Key Insights

- Best-selling products
- Top revenue-generating categories
- Product demand patterns

**Screenshot**

```text
screenshots/12-product-performance-dashboard.png
```

---

# Dashboard 3 — Customer & Operations Insights

## Objective

Understand customer activity and operational performance.

### Visualizations

- Revenue by Customer
- Revenue by Country
- Payment Status Distribution
- Delivery Status Distribution

### Key Insights

- Top customers
- Outstanding payments
- Delivery performance monitoring

**Screenshot**

```text
screenshots/13-customer-operations-dashboard.png
```

---

## Business Benefits

This solution provides:

- Centralized reporting
- Cloud-hosted analytics
- Interactive business dashboards
- Data-driven decision-making
- KPI monitoring
- Self-service reporting capabilities

---

## Skills Demonstrated

### Azure

- Azure Resource Groups
- Azure SQL Database
- Azure SQL Server
- Network Security Configuration
- Cloud Resource Management

### SQL

- Table Creation
- Data Validation
- Query Execution
- Data Management

### Power BI

- Data Modeling
- Power Query
- DAX
- Dashboard Development
- KPI Reporting
- Data Visualization

### Business Analysis

- Data Interpretation
- Performance Monitoring
- Trend Analysis
- Operational Reporting

---

## Repository Structure

```text
powerbi-azure-sales-dashboard

│
├── README.md
│
├── sql
│   ├── create-sales-table.sql
│   ├── insert-sales-data.sql
│
├── powerbi
│   └── sales-analytics-dashboard.pbix
│
├── dataset
│   └── sales-data.csv
│
├── screenshots
│   ├── 01-resource-group-created.png
│   ├── 02-sql-server-created.png
│   ├── 03-sql-database-created.png
│   ├── 04-firewall-configuration.png
│   ├── 05-sales-table-created.png
│   ├── 06-sales-data-inserted.png
│   ├── 07-sales-data-validation.png
│   ├── 08-powerbi-sql-connection.png
│   ├── 09-power-query-transformations.png
│   ├── 10-dax-measures-created.png
│   ├── 11-sales-overview-dashboard.png
│   ├── 12-product-performance-dashboard.png
│   └── 13-customer-operations-dashboard.png
│
└── docs
    └── project-summary.md
```

---

## Key Learning Outcomes

- Deploying cloud database solutions in Azure
- Configuring Azure SQL Database networking
- Creating relational database tables
- Executing SQL queries in Azure
- Connecting Azure services to Power BI
- Building interactive business dashboards
- Creating DAX measures and KPIs
- Publishing a complete analytics solution to GitHub
