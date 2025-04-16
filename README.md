# 📊 Corporate Financial Dashboard & FP&A Automation (Power BI)

This project aims to automate financial reporting and develop a comprehensive **Financial Dashboard** that provides insights into Sales, Profitability, and Cash Flow performance across time and geography. Built using Power BI, Excel, and SQL-backed data modeling.

---

## 🧾 Table of Contents

- [📁 Project Overview](#project-overview)
- [📊 Dashboard Pages](#dashboard-pages)
- [🛠️ Tools & Technologies Used](#tools--technologies-used)
- [🧱 Data Model Structure](#data-model-structure)
- [📈 Step-by-Step Development Process](#step-by-step-development-process)
- [📌 Key DAX Measures](#key-dax-measures)
- [📉 Insights & Visualizations](#insights--visualizations)
- [🚀 Future Enhancements](#future-enhancements)
- [📚 References](#references)

---

## 📁 Project Overview

**Goal:**  
To build a real-time, interactive, and visually intuitive Power BI Dashboard for financial performance analysis across different dimensions (time, accounts, regions).

**Objectives:**

- Automate Profit & Loss Reporting
- Visualize Sales & Gross Profit by Country
- Create a dynamic Cash Flow Statement
- Enable Time and Territory-based performance comparison

---

## 📊 Dashboard Pages

| Page         | Description                                                                 |
|--------------|-----------------------------------------------------------------------------|
| **Sales**        | Tracks sales trends year-wise and across subclasses                     |
| **Profit & Loss**| Full P&L statement with dynamic KPIs like Gross Profit, EBITDA, Net Profit |
| **CrossCountry** | Sales, Gross Profit & Net Profit by Country/Region                      |
| **Cash Flow**    | Statement of Cash Flows from Operating Activities (optional extension)  |
| **Balance Sheet**| Structured by Assets, Liabilities, Equity (optional)                    |

---

## 🛠️ Tools & Technologies Used

- **Power BI Desktop** – Dashboard creation & visualization
- **Microsoft Excel** – Data preprocessing
- **SQL** – Data extraction, cleansing, and aggregation
- **DAX (Data Analysis Expressions)** – Calculations & KPIs
- **Star Schema Modeling** – For optimized report performance

---

## 🧱 Data Model Structure

Star Schema includes:

### 🔸 Fact Table:
- `tbl_GL` – General Ledger (Date, Account_key, Amount, Details, Territory_key)

### 🔹 Dimension Tables:
- `tbl_Calendar` – Full Date Dimension (Date, Year, Quarter, Month, Day)
- `tbl_ChartofAccounts` – Account Mapping (Account, SubAccount, Report Type, etc.)
- `tbl_Territory` – Country and Region Data
- `tbl_CashFlowMapping` – For Cash Flow Statement structure
- `tbl_OpeningBalance` – For opening balances of cash and equity

---

## 📈 Step-by-Step Development Process

### ✅ Step 1: Prepare the Data
- Clean the journal entries (`tbl_GL`)
- Load mapping tables for:
  - Chart of Accounts
  - Territories
  - Calendar (Date dimension)
  - Cash flow/Equity structures

### ✅ Step 2: Create the Data Model in Power BI
- Import all tables
- Set relationships:
  - `tbl_GL[Date]` → `tbl_Calendar[Date]`
  - `tbl_GL[Account_key]` → `tbl_ChartofAccounts[Account_key]`
  - `tbl_GL[Territory_key]` → `tbl_Territory[Territory_key]`

### ✅ Step 3: Create DAX Measures
Examples:
DAX
Total Sales = 
CALCULATE(SUM(tbl_GL[Amount]), tbl_ChartofAccounts[Account] = "Sales")

Gross Profit = 
[Total Sales] - [Cost of Sales]

EBITDA = 
[Gross Profit] - [Operating Expenses]

Net Profit = 
[EBITDA] + [Other Income] - [Taxes] 

### ✅ Step 4: Build Visuals
Use Matrix for P&L and Cash Flow statements

Use Line Charts for sales/profit trends

Use Slicers for Year, Month, and Country

Use KPI cards for Total Revenue, EBITDA, Net Profit

### ✅ Step 5: Create Interactive Filters
Sync Year and Country slicers across pages

Enable drill-down in matrix and charts for detail-level analysis

### ✅ Step 6: Final Touches
Apply proper formatting, themes, tooltips

Rename fields for clarity

Add page navigation or bookmarks if required


📉 Insights & Visualizations
📄 Profit and Loss Page
View changes in profitability across time

Highlight increase in Net Profit and Gross Margin from 2018 to 2020

🌍 Cross-Country Analysis
Identify top-performing countries (e.g., USA, New Zealand)

Compare regions based on Gross Profit and Net Profit

💰 Cash Flow Statement
Cash from operating activities

Cash at beginning vs. end of the period

Net movement in cash
