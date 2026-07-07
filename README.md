**INTERN ID : CITS4956
FULL NAME : TANVI SUDESH LAD
NO. OF WEEKS : 04
PROJECT NAME : MARKET BASKET ANALYSIS**
**PROJECT SCOPE : Perform Market Basket Analysis to find frequently bought products and present insights via Power BI dashboard.**

# Project Title: Market Basket Analysis for Online Retail using Power BI & Python

## Brief Summary
Analyzed the "Online Retail II" dataset to generate association rules and built an interactive Power BI dashboard to drive cross-selling and increase AOV.

## Overview
This project performs Market Basket Analysis on the Online Retail II dataset. 
Using the Apriori algorithm in Python, we generated association rules and visualized the top product associations in Power BI.
The goal is to help e-commerce businesses identify products that are frequently bought together.

## Problem Statement
E-commerce companies need to understand buying patterns to recommend products effectively. 
Without knowing which products are associated, they lose revenue on missed cross-sell and bundle opportunities.
This project solves that by identifying strong product associations from transaction data.

## Dataset
- **Dataset 1 - Raw Data**: `online_retail_ii.xlsx`
    - Source: UCI Machine Learning Repository - Online Retail II
    - Description: 2 years of transactions from a UK-based online retail store
    - Columns: `InvoiceNo`, `StockCode`, `Description`, `Quantity`, `InvoiceDate`, `UnitPrice`, `CustomerID`, `Country`
- **Dataset 2 - Processed**: `mba_rules.csv`
    - Description: Association rules generated using Apriori
    - Columns: `antecedents`, `consequents`, `support`, `confidence`, `lift`

## Tools and Technologies
- **Programming**: Python 3.10, Pandas, NumPy
- **ML Library**: mlxtend - Apriori Algorithm
- **Visualization**: Power BI Desktop, DAX, Power Query
- **IDE**: Jupyter Notebook

## Methods
1.  **Data Cleaning**: Removed nulls, cancelled invoices, and filtered for UK transactions
2.  **Basket Creation**: Grouped items by `InvoiceNo` to create transaction baskets
3.  **Rule Generation**: Applied Apriori with min_support=0.01 to generate frequent itemsets
4.  **Metric Calculation**: Calculated Support, Confidence, and Lift for 2910 rules
5.  **Dashboard**: Loaded `mba_rules.csv` into Power BI and built interactive visuals with Lift slicer

## Key Insights
1.  **POPPY'S PLAYHOUSE** product line has 100% Confidence and 53.86 Lift.
    Customers buying 2 rooms always buy the 3rd room.
2.  **BAKING CASES** show strong association: 
    SET OF 12 MINI LOAF BAKING CASES → SET OF 6 TEA TIME BAKING CASES has 30.75 Lift.
3.  After filtering Lift > 40, we identified 50 high-impact rules for bundling.
4.  All top associations have 100% Confidence, showing deterministic buying behavior.

## Dashboard/Model/Output
The Power BI dashboard includes:
- **KPI Cards**: Total Rules: 50, Avg Lift: 42.18, Avg Confidence: 100%
- **Scatter Plot**: Support vs Confidence to identify quality rules
- **Bar Chart**: Top Consequents by Avg Confidence
- **Rules Table**: Searchable table with all metrics
- **Slicer**: Filter by Lift to focus on strongest associations

## How to Run this project?
1.  **Clone the repository**
    ```bash
    git clone https://github.com/ladtanvi12-lab/Market-Basket-AnalysisPowerBI.git
    
Install dependencies 
bash    
pip install -r requirements.txt
Generate Rules: Run Notebooks/MBA_Apriori.ipynb on Dataset/online_retail_ii.xlsx
This will create Dataset/mba_rules.csv
View Dashboard: Open PowerBI_Dashboard/MarketBasketAnalysis.pbix in Power BI

Results & Conclusion
The Apriori model on Online Retail II data revealed clear product associations. 
Focusing on high-lift rules > 40 gives actionable bundling opportunities. 
Recommendation: Create "Complete Playhouse" and "Baking Kit" bundles to increase AOV by an estimated 20-25%.

Future Work
Add customer segmentation to find associations per country/customer type.
Build a real-time recommendation engine using these rules.
Test A/B testing of bundles on website to measure actual revenue lift
