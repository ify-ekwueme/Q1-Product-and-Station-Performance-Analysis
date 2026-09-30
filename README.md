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
- Product was standardized to resolve l

3. **Transformation:**
- Reshaped wide dataset (500 rows) into normalized long format (2500 rows) by unpivoting product columns (PMS, AGO, LPG, Lubricant, DPK) to enable station-by-product analysis in Power BI.
- Defined calculated measures for KPI (Total revenue, Daily average revenue, Volume dispensed etc) 
  
4. **Analysis:**
- Performed EDA to identify revenue trends, best selling products etc. 

5. **Output:**
- A one page dashboard with KPI data and charts across the 3 station. 

- - - 










