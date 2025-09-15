# AMAZON-SALES-ANAYSIS

![Amazon halved corporation tax bill despite UK profits tripling](https://github.com/user-attachments/assets/c1dbda1a-4213-4d22-a309-20954d57776e)

# **Executive Summary: Amazon Sales Analysis**

## Project Overview

This project presents an interactive **Sales Analytics Dashboard** built using real-world-inspired Amazon sales data. It was developed as an educational and portfolio project to demonstrate end-to-end data analysis using Power BI.

The dashboard provides stakeholders with a dynamic, visual summary of key business metrics — including total sales, profit, customer count, discount trends, and regional performance — over a four-year period (2022–2025). It enables deep insights across multiple dimensions such as geography, product line, customer segment, and time.

The project simulates how retail and e-commerce companies like Amazon utilize business intelligence tools to monitor performance, identify opportunities, and support strategic decision-making. It also showcases technical proficiency in:

- **Data preparation** with Power Query  
- **Data modeling** and relationship design  
- **DAX calculations** for dynamic KPIs and metrics  
- **Visual design and storytelling** using Power BI  

⚠️ *Disclaimer: This project was created strictly for educational and non-commercial use. The dataset used is a simulated version based on public patterns and does not represent actual Amazon data.*

##  Key Findings & Strategic Impact

### 🔍 Key Findings:
- 📈 **Steady growth** in sales from 2022 to 2025, with the highest total in 2025 ($734K).
- 🌍 **AMER region** led in profit contribution (51.49%), with **UKIR** and **EU-WEST** as top subregions.
- 🛒 **ContactMatcher**, **FinanceHub**, and **Site Analytics** were top-performing products.
- 👥 **Enterprise customers** drove revenue, while **SMBs** yielded higher margins on select products.
- 💸 **Heavy discounts** in the Finance sector impacted profitability.
- 📅 **Seasonal spikes** observed in Q4 (Nov–Dec), aligning with typical retail trends.

### 🎯 Strategic Impact:
- Helps target **high-performing regions** for sales and marketing efforts.
- Supports **pricing strategy reviews**, especially where discounts reduce margins.
- Informs **product focus** by highlighting consistent top sellers.
- Enables **seasonal campaign planning** to maximize Q4 performance.
- Guides customer segmentation strategies for **high-value accounts**.

<details>
<summary> Table of Contents</summary>
<br>

# Table of Contents

1. [Project Overview](#project-overview)  
2. [Business Context & Research Questions](#business-context--research-questions)  
3. [Dataset Information](#dataset-information)  
4. [Methodology & Technical Approach](#methodology--technical-approach)  
5. [Data Quality & Challenges](#data-quality--challenges)  
6. [Key Findings & Insights](#key-findings--insights)  
7. [Visualizations & Dashboard](#visualizations--dashboard)  
8. [Recommendations & Impact](#recommendations--impact)  
9. [Technical Implementation](#technical-implementation)  
10. [Future Work & Limitations](#future-work--limitations)  
11. [How to Use This Repository](#how-to-use-this-repository)  
12. [Contributors & Acknowledgments](#contributors--acknowledgments)  

 </details>


## Business Context & Research Questions

In today's fast-paced e-commerce landscape, companies like Amazon rely heavily on data-driven insights to drive strategic decisions. With millions of transactions happening across countries, regions, and product categories, it becomes essential for business leaders to have a clear view of performance metrics such as sales, profit, customer behavior, and product trends.

This project simulates how a data analyst can support executive decision-making by building an interactive Amazon sales dashboard using Power BI. The dashboard enables stakeholders to filter data by time, region, segment, and product to monitor trends, identify opportunities, and manage performance.

**Tools Used:** Power BI, Power Query, DAX  
**Disclaimer:** This dashboard was built strictly for educational purposes using simulated real-world data. It does not represent actual Amazon operations or proprietary data.

---

##  Research Questions

1. What are our total sales, profit, and profit margin over the years?  
2. Which regions and subregions are the most profitable?  
3. Which products and licenses contribute most to revenue and profit?  
4. How do different customer segments (SMB, Enterprise, Strategic) perform?  
5. How do discount patterns affect profitability across industries?  
6. What seasonal trends can be observed in monthly and yearly sales?  
7. Which cities and countries have the strongest market presence?  
8. How do sales compare between Finance and Energy industries?  
9. Are we seeing growth or retention in the customer base year over year?  
10. How can users interact with the dashboard to gain deeper insights using slicers like year, city, segment, or license?


##  [Dataset Information](#dataset-information)

### 🧾 Raw Dataset Sample (First 10 Rows)

```csv
Row ID,Order ID,Order Date,Date Key,Contact Name,Country,City,Region,Subregion,Customer,Customer ID,Industry,Segment,Product,License,Sales,Quantity,Discount,Profit
1,EMEA-2024-152156,11/9/2024,20241109,Nathan Bell,Ireland,Dublin,EMEA,UKIR,AnyCompany Energy,1017,Energy,Enterprise,Marketing Suite,16GRM07R1K,261.96,2,0,41.9136
2,EMEA-2024-152156,11/9/2024,20241109,Nathan Bell,Ireland,Dublin,EMEA,UKIR,AnyCompany Energy,1017,Energy,Enterprise,FinanceHub,QLIW57KZUV,731.94,3,0,219.582
3,AMER-2024-138688,6/13/2024,20240613,Deirdre Bailey,United States,New York City,AMER,NAMER,AnyCompany Oil,1056,Energy,Strategic,FinanceHub,JI6BVL70HQ,14.62,2,0,6.8714
4,EMEA-2023-108966,10/11/2023,20231011,Zoe Hodges,Germany,Stuttgart,EMEA,EU-WEST,Example Corp Power,1031,Energy,Enterprise,ContactMatcher,DE9GJKGD44,957.5775,5,0.45,-383.031
5,EMEA-2023-108966,10/11/2023,20231011,Zoe Hodges,Germany,Stuttgart,EMEA,EU-WEST,Example Corp Power,1031,Energy,Enterprise,Marketing Suite - Gold,OIF7NY23WD,22.368,2,0.2,2.5164
6,AMER-2022-115812,6/9/2022,20220609,Thomas Hodges,United States,New York City,AMER,NAMER,AnyCompany Money Group,1065,Finance,SMB,SaaS Connector Pack,8RM88WFOAE,48.86,7,0,14.1694
7,AMER-2022-115812,6/9/2022,20220609,Thomas Hodges,United States,New York City,AMER,NAMER,AnyCompany Money Group,1065,Finance,SMB,ChatBot Plugin,4SYTVM0746,7.28,4,0,1.9656
8,AMER-2022-115812,6/9/2022,20220609,Thomas Hodges,United States,New York City,AMER,NAMER,AnyCompany Money Group,1065,Finance,SMB,Site Analytics,07842ES7DY,907.152,6,0.2,90.7152
9,AMER-2022-115812,6/9/2022,20220609,Thomas Hodges,United States,New York City,AMER,NAMER,AnyCompany Money Group,1065,Finance,SMB,ContactMatcher,XPBOBXWXA3,18.504,3,0.2,5.7825
10,AMER-2022-115812,6/9/2022,20220609,Thomas Hodges,United States,New York City,AMER,NAMER,AnyCompany Money Group,1065,Finance,SMB,OneView,71J8P9Z1P0,114.9,5,0,34.47
```

### 🔑 Key Fields

* **Row ID** – Sequential row identifier
* **Order ID** – Unique transaction reference
* **Order Date** – Actual transaction date
* **Date Key** – Numeric format of the order date for data modeling
* **Contact Name** – Sales or account contact
* **Country / City / Region / Subregion** – Geographic data
* **Customer / Customer ID** – Business entity and identifier
* **Industry / Segment** – Market sector and customer tier
* **Product / License** – Product purchased and corresponding ID
* **Sales** – Transaction value in USD
* **Quantity** – Number of items purchased
* **Discount** – Discount applied per item
* **Profit** – Net earnings from the sale

> 📌 **Disclaimer:** Data is simulated and used solely for learning and portfolio demonstration.



## 📊 Methodology & Technical Approach

### 🔧 Data Preparation

* **Data Cleaning:** Used Power Query to remove duplicates, handle missing values, and ensure consistent date formatting.
* **Data Transformation:** Created new calculated columns (e.g., Profit Margin, Year, Month) for analysis.
* **Data Modeling:** Established relationships between fact tables and dimension tables for accurate filtering and drill-down analysis.

### 📈 Analytical Approach

* **KPIs Defined:** Total Sales, Total Profit, Profit Margin %, Quantity Sold, and Discount Impact.
* **DAX Measures:** Used DAX formulas to calculate dynamic metrics such as Year-to-Date (YTD) Sales, Profit Margin, and Region-wise contributions.
* **Filters & Slicers:** Added interactive filters for Year, Region, Segment, and Product to enable stakeholders to explore data.

### 📊 Dashboard Development

* **Visualization:** Used bar charts, line charts, and cards to highlight key metrics.
* **User Experience:** Applied consistent colors, clean layout, and slicers for interactivity.
* **Validation:** Cross-checked totals and calculations against raw data to ensure accuracy.



## <span style="color:black">Data Quality & Challenges</span>

### 🔍 Data Quality Assessment

* **Completeness:** Dataset was well-structured with no missing critical fields.
* **Consistency:** Date formats and currency values were standardized using Power Query.
* **Accuracy:** Data is simulated but designed to closely mimic real-world Amazon sales transactions.

### ⚠️ Challenges Faced

* **Date Formatting:** Required transformation to a consistent YYYY-MM-DD format for time intelligence in Power BI.
* **Profit Calculations:** Some rows had negative profits (losses) that required careful validation.
* **Data Granularity:** Multiple products per order required grouping and aggregation to get accurate order-level totals.

### ✅ Resolution

* Applied Power Query transformations for data cleaning.
* Used DAX to create calculated columns for profit margin and validated results.
* Ensured relationships were correctly set between tables to avoid double counting.

> 📌 **Note:** These challenges are common in real-world projects and were addressed to ensure reliable insights in the dashboard.


<h2 style="color:black;">Key Findings & Insights</h2>

### 📊 Summary of Findings

* **Top Performing Region:** EMEA generated the highest total sales across the observed period.
* **Customer Segment Impact:** Enterprise customers contributed the largest share of revenue.
* **Profitability Insight:** Some orders had negative profit margins, highlighting discount or cost issues.
* **Product Performance:** FinanceHub and Marketing Suite were the most frequently purchased products.
* **Trend Observation:** Sales showed strong growth in 2024 compared to 2023.

### 🎯 Recommendations

* **Focus on High-Performing Regions:** Continue to invest in EMEA growth opportunities.
* **Review Negative Margins:** Investigate loss-making transactions and optimize discount strategy.
* **Customer Segmentation:** Tailor offerings for Enterprise and Strategic segments to maximize revenue.
* **Product Portfolio Optimization:** Promote top products while reviewing underperforming SKUs.


<h2 style="color:black;">Visualizations & Dashboard</h2>

### 📊 Power BI Dashboard Preview

![Amazon Sales Dashboard](dashboard-screenshot.png)

### 🖼 Dashboard Features

* **Interactive Filters:** Year, Region, Segment, Product slicers for dynamic exploration.
* **KPIs at a Glance:** Total Sales, Total Profit, Profit Margin %, Quantity Sold, and Discount Impact.
* **Visuals Used:** Bar charts, line charts, and cards for clear, actionable insights.
* **Drill-Down Capability:** Allows users to explore sales performance by country, city, and customer.

> 📌 **Note:** Dashboard screenshot is for educational demonstration only.





