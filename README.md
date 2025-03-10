# Beyond the Checkout: A Data-Driven Comparison of E-Commerce and Retail Financial Health

## Step 1: Define the Business Case

### Objective:
- Compare top 10 e-commerce vs. top 10 retail companies based on profitability, efficiency, growth, and financial health using historical financial data.
- Compare the financial performance of top 10 e-commerce vs. top 10 retail companies in the same industry to identify strengths, weaknesses, and trends.

### Companies Selection:
- Use [CompaniesMarketcap.com](https://companiesmarketcap.com/) to select the companies.
- Pick the **Top 10 publicly traded e-commerce companies by revenue**.
- Pick the **Top 10 publicly traded retail companies by revenue**.
- Enrich with demographic info from [StockViz.com](https://www.stockviz.com/).

### Key Questions:
1. How do profit margins compare between e-commerce & retail?
2. Are e-commerce companies growing faster in revenue & EBITDA?
3. Do retailers have stronger financial stability (Debt-to-Equity, ROA)?
4. Which companies are the best investment opportunities?

### Final Deliverables:
- GitHub repository
- Jupyter Notebook with full analysis and calculation
- Statistical summary (T-tests, correlations)
- CSV with calculated KPIs
- Tableau Dashboard
- [Presentation with insights][(https://www.canva.com/design/DAGg2dYeags/Aiy_cDm7m8JDP3Ya7399iQ/edit?utm_content=DAGg2dYeags&utm_campaign=designshare&utm_medium=link2&utm_source=sharebutton)](https://www.canva.com/design/DAGg2dYeags/Aiy_cDm7m8JDP3Ya7399iQ/edit)

---

## Step 2: Data Extraction
- Using the **Yahoo Finance (YF) API**, extracted financial statements for each company ticker:
  - Income Statement
  - Balance Sheet
  - Cash Flow Statement
- Generated **3 CSV files per company** (60 in total), ensuring currency types were included since not all companies reported values in USD.

---

## Step 3: Data Cleaning & Wrangling
- Converted date columns to datetime format.
- Standardized numerical values.
- Handled missing values (using StockViz data).
- Standardized column names for consistency.
- Selected key columns needed for KPI calculations.
- Added **Company, Currency, & Country** columns for better identification.
- **Merged** financial statements by industry:
  - `df_ecomm_new`
  - `df_retail_new`
- Converted **non-USD values to USD** (currency rate as of 31-12-2023 for JPY, HKD, EUR, and GBP):
  - `df_ecomm_usd`
  - `df_retail_usd`
- Selected fiscal years: `['31-12-2021', '31-12-2022', '31-12-2023']`
- Exported dataframes to CSV for:
  - **KPI calculations**
  - **Tableau visualizations**
- Repeated the process for **retail companies**.

---

## Step 4: Feature Engineering (KPIs)

### 1. **Profitability KPIs – How Profitable Are They?**
- **Gross Profit Margin** = (Gross Profit / Total Revenue) * 100
- **Operating Profit Margin** = (Operating Income / Total Revenue) * 100
- **EBITDA Margin** = (EBITDA / Total Revenue) * 100
- **Net Profit Margin** = (Net Income / Total Revenue) * 100
- **Return on Assets (ROA)** = (Net Income / Total Assets) * 100
- **Return on Equity (ROE)** = (Net Income / Stockholders' Equity) * 100
#### Insight:
- E-commerce might have **higher gross margins** (low inventory costs).
- Retail might have **lower margins** due to logistics & store maintenance.

### 2. **Growth KPIs – Are They Growing?**
- **Revenue Growth Rate** = (Current Revenue - Last Year Revenue) / Last Year Revenue * 100
- **EBITDA Growth Rate** = (Current EBITDA - Last Year EBITDA) / Last Year EBITDA * 100
- **Net Income Growth Rate** = (Current Net Income - Last Year Net Income) / Last Year Net Income * 100
#### Insight:
- E-commerce companies might have **higher revenue growth** due to digital adoption.
- Retailers might have **slower growth** due to store expansion costs.

### 3. **Efficiency KPIs – How Well Do They Use Assets?**
- **Asset Turnover** = Total Revenue / Total Assets
- **Inventory Turnover** = Cost of Revenue / Inventory
- **SG&A Efficiency** = (Selling, General & Admin Expenses / Total Revenue) * 100
#### Insight:
- E-commerce companies might have **higher asset turnover** (less physical inventory).
- Retailers might have **slower inventory turnover** due to stock dependency.

### 4. **Financial Health KPIs – Are They Financially Stable?**
- **Current Ratio** = Current Assets / Current Liabilities
- **Debt-to-Equity Ratio** = Total Debt / Stockholders' Equity
- **Net Debt-to-EBITDA** = (Total Debt - Cash) / EBITDA
- **Free Cash Flow (FCF)** = Operating Cash Flow - Capital Expenditures
#### Insight:
- E-commerce might have **higher debt ratios** (tech investments, expansion).
- Retailers might have **stronger free cash flow** (brick-and-mortar revenue).

### 5. **Investor & Market KPIs – Are They Good Investments?**
- **Earnings Per Share (EPS)** = Net Income / Diluted Average Shares
- **Price-to-Earnings Ratio (P/E)** = Stock Price / EPS
- **Market Capitalization Growth** = External data required (stock growth trends)
#### Insight:
- E-commerce companies often **trade at higher P/E ratios** (growth expectations).
- Retail companies might have **lower but stable EPS**.

---

## Step 5: Statistical Analysis
### Key Insights:
- **T-test** to compare profitability differences between industries.
- **Correlation analysis** between debt levels and profitability.

---

## Step 6: Create a Dashboard (Tableau)

### **Dashboard Sections:**
1. **Comparison of Revenue Growth** (E-Commerce vs. Retail)
2. **Profitability Metrics** - Gross Profit, Net Profit, EBITDA
3. **Liquidity & Debt Analysis** - Current Ratio & Debt-to-Equity
4. **Cash Flow Comparison** - Operating & Free Cash Flow Trends
5. **Valuation Analysis** - P/E Ratio & EPS Trends

### **Insights & Decision Making:**
- **Does E-Commerce have higher profit margins than Retail?**
- **Are Retail companies more stable in terms of cash flow and debt management?**
- **Which sector has higher valuation multiples (P/E Ratio)?**

---

