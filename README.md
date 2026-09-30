# Q1-Product-and-Station-Performance-Analysis
Data analysis of petroleum station operation. Analyzes product sales, and station efficiency for PMS, AGO, Diesel, Lubricants, and LPG.

## ⚙️ Project Type 
- [x] Exploratory Data Analysis
- [x] Data Manipulation
- [x] Data cleaning
- [x] Data Visualization

- - - 

## Table of contents 
1. [Project Overview](#1-project-overview)
2. [Objectives](#2-objective)
3. [Project Scope & Tools](#3-project-scope--tools)
4. [Repository Structure](#4-repository-structure)
5. [Data Workflow](#5-data-workflow)
6. [Data Model & Schema](#6-data-model--schema)
7. [Analysis & Metrics](#7-analysis--metrics)
8. [Key Insights](#8-key-insights)
9. [Recommendations](#9-recommendations)
10. [Assumptions & Limitations](#10-assumptions--limitations)
11. [Future Enhancements](#11-future-enhancements)
12. [Dashboard](#12-dashboard)
13. [Author](#13-author)

- - - 

## 1. Project Overview 

  This is an Analysis of Q1 2025 sales data across three fuel retail stations, Iwaya, Idimu and Maryland. Each station covers five products (PMS, AGO, Diesel, Lubricants, Cooking Gas). I built an interactive Power Bi dashboard to give commercial management visibility into revenue trends, product mix, staffing demand and supervisor performance.

### Problem Statement 
  Commercial leadership had raw transactional data but no consolidated view to answer basic operating questions:
- Is revenue growing or shrinking?
-  Which products and stations drive the business?
-  Is staffing aligned with actual demand patterns?
-  Are shifts run consistently across supervisors?

 Without a dashboard, these questions required manual spreadsheet digging on an ad-hoc basis.

### Outcome 
  The Analysis surfaced a previously invisible finding : Revenue dropped 16.9% from January to February and has since plateaued, rather than declining gradually, reframing the business question from "why are we shrinking" to "what changed in February." Also identified automotive fuel's 89% revenue dominance across all stations as a consistent cross-sell gap in lubricants and cooking gas.

- - - 

## 2. Objectives 
- - -
The objective was to track overall revenue performance and momentum across the quarter.
- To identify top-performing products and stations
- Understand demand patterns by day and shift for staffing decisions.
- To evaluate supervisor performance consistency.

- - - 

## 3. Project Scope & Tools 

### Scope 

| Dimension | Details |
|-----------|---------|
| **In Scope** | The product and station performance analysis data was downloaded from kaggle. Analysis covers revenue trends, volume of products sold, average daily revenue etc.|
| **Out of Scope** | Unit prices are constant across months, it was impossible to know if the decline in revenue was as a result of price fluctuation. |
| **Time Period** | 2025 (January - March) |

- - - 
### Tools and Technology 
| Purpose | Tool(s) Used |
|----------|-------------|
| Data Storage | CSV files |
| Data Processing | Excel |
| Analysis | Power Query, Power Bi (Dax) |
| Visualization | Power BI |
| Version Control | GitHub |

- - - 

## 4. Repository Structure 

```
Q1 Product and Station Performance Analysis/
│
├── data/
│   ├── raw/
│        └──Data external/timac_fuel_data_500_enhanced.xlsx
│   ├── processed/
│        └── Q1_Fuel_Sales_Data.csv
│
│── docs/
│        └── Q1_Fuel_Sales_Documentation.xlsx
│
├── reports/              
│   ├── Q1_Product_and_Station_Performance.pdf
│
├── visuals/        
│   ├── Dashboard_Screenshot.jpeg
│    
│
└── README.md                
```

- - - 

## 5. Data Workflow 

1. **Source:**
- The CSV file contains fuel sales record from three stations, covering the first quarter of 2025. It was downloaded from Kaggle.  

2. **Cleaning:**
- Data was cleaned in Power Query
- Fixed mismatch between Product and Product Category after reshaping using IF mapping (=IF(Product="PMS","Automotive Fuel",...)) and pasted as values to standardize.
- Cleaned currency field.
- Parsed date.

3. **Transformation:**
- Reshaped wide dataset (500 rows) into normalized long format (2500 rows) by unpivoting product columns (PMS, AGO, LPG, Lubricant, DPK) to enable station-by-product analysis in Power BI.
- Defined calculated measures for KPI (Total revenue, Daily average revenue, Volume dispensed etc) 
  
4. **Analysis:**
- Performed EDA to identify revenue trends, best selling products, supervisor performance etc.
- Built Dax measures for Revenue, Volume, Performance etc. 

5. **Output:**
- A one page dashboard with KPI data and charts across the 3 station. 

- - - 

## 6. Data Model & Schema

### Dataset
Table 1: `FuelSales`

| Field Name | Data Type | Description | Example Value |
|------------|-----------|--------------|----------------|
| Date | date | date of the sales transaction | 15/02/2025 |
| Station_Name | text | fuel station where the sale occurred | Idimu |
| Product Category | text | broader category of product sold | Automotive Fuel |
| Product | text | specific product sold | PMS |
| Shift | text | shift during which the sale occurred | Morning |
| Supervisor | text | supervisor on duty for the shift | Mr Tunde |
| Weekday | text | day of the week | Monday |
| Quantity | decimal | volume sold, in litres or kg | 1250 |
| Unit_Price | decimal | price per unit, in Naira | 650.00 |
| Revenue | decimal | total revenue generated, in Naira | 812500.00 |
| Month_Name | text | name of the month | February |
| Month_Number | int | numeric month | 2 |
| Quarter | int | quarter of the year | 1 |

- - - 

## 7. Analysis and Metrics
### Analytical Approach
This project followed an exploratory data analysis (EDA) approach to understand fuel retail sales performance across stations in Q1 2025.

### Key Metrics

| Metric | Description | Business Value |
|--------|--------------|------------------|
| `Total Revenue` | Sum of all revenue generated across stations for the period | Measures overall business performance |
| `Total Volume` | Sum of quantity sold (litres/kg) across all products | Tracks throughput and demand |
| `Avg Daily Revenue` | Average revenue generated per day | Benchmarks daily performance |
| `Month over Month %` | Percentage change in revenue from one month to the next | Flags growth or decline trends |
| `Revenue by Product` | Revenue broken down by product type | Identifies top revenue-driving products |
| `Revenue by Station` | Revenue broken down by station location | Compares station performance |


### Methods Used 

- Trend analysis across three months.
- Prepared and reshaped dataset in Excel and power query.
- Developed Dax measures for key business metrics.
- Built a power bi dashboard to help stakeholders visualize the insights easily.

  - - -

## 8. Key Insights

* Revenue fell 16.9% from January to February, then plateaued (+0.5% Feb→Mar), a one-time step-down, not a gradual decline.
  
* PMS drives the most revenue despite the lowest unit price. Therefore, it is a volume driver, not a margin driver.
  
* Automotive fuel makes up 89% of revenue at all three stations; lubricants and cooking gas remain a flat, under-leveraged category.

* Friday mornings and Sunday nights see peak demand; Friday/Saturday nights are consistently the lightest.

* Supervisor performance is consistent (₦7.0M–7.3M avg revenue/shift), no major outliers.

* Miss Chika logged fewer shifts than the rest of the supervisor, although performance per shift shows no red flag.

- - - 

## 9. Recommendations

* Investigate the February revenue step-down, to know if it’s a (pricing, supply, competition) problem.

* Run promotions to grow lubricant and cooking gas attachment rates.

* Reduce night staffing on Fridays and Saturdays; reinforce Friday morning and Sunday night coverage.

* Monitor the shift coverage consistency across supervisors.

- - -

## 10. Limitations
* Unit prices are constant across the quarter,  no pricing/elasticity analysis possible.

* Quantity units are mixed (litres for fuel, kg for gas) and reported as combined volume.

* Data reflects shift-level totals, not individual transactions.

- - - 

## 11. Future Enhancements

* Incorporate cost data to analyze margin, not just revenue.

* Add year-over-year comparison once more historical data is available.

* Track promotions and pricing changes against revenue impact.

- - - 

## 12. Dashboard

## Commercial Overview

![Commercial Overview]

- - - 

## 13. Author 

**Ekwueme Ifeoma**

Data Analyst












