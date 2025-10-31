# 🛍️ Retail Sales Performance Dashboard – Sales Analytics & Insights

[![Power BI](https://img.shields.io/badge/Power_BI-Desktop-blue?logo=powerbi)](https://powerbi.microsoft.com/) 
[![DAX](https://img.shields.io/badge/Language-DAX-purple)](https://learn.microsoft.com/en-us/dax/)
[![Analytics](https://img.shields.io/badge/Type-Sales_Analytics-green)](https://github.com)

A comprehensive Power BI interactive dashboard providing a **360° unified view of sales performance, profitability, and customer purchasing behavior**. Consolidates data from retail transactions to help business teams analyze sales trends, product performance, and regional insights—all in one integrated dashboard.

---

## 📋 Table of Contents

- [Project Overview](#project-overview)
- [Project Objective](#project-objective)
- [Dataset Description](#dataset-description)
- [Data Model Architecture](#data-model-architecture)
- [DAX Measures](#dax-measures)
- [Dashboard Features](#dashboard-features)
- [Installation & Prerequisites](#installation--prerequisites)
- [How to Use](#how-to-use)
- [Key Insights](#key-insights)
- [Tech Stack](#tech-stack)

---

## 📊 Project Overview

This Power BI project provides an **interactive view of retail sales performance and business metrics** using a single-table fact model. It enables monitoring of:

- 📈 **Sales performance and trends** (monthly, yearly, by category)
- 💰 **Profitability analysis** (profit margins, category performance)
- 🏆 **Product category insights** (top performers, revenue distribution)
- 🌍 **Regional performance tracking** (sales contribution by region)
- 📊 **Channel comparison** (online, retail, distributor channels)
- 💳 **Customer purchasing behavior** (order patterns, high-value customers)

---

## 🎯 Project Objective

To build an interactive dashboard that enables real-time monitoring and performance tracking across all retail dimensions:

✅ **Real-time monitoring** of sales, profit, and order KPIs  
✅ **Performance tracking** by product category, region, and channel  
✅ **Identification of high-value customers** and top-performing SKUs  
✅ **Visualization of sales trends** over time for forecasting and planning  
✅ **Profitability analysis** and margin optimization  
✅ **Data-driven decision-making** for sales and inventory management  

---

## 📋 Dataset Description

### Table Used

**`Retail_Sales_Synthetic`**

### Key Columns

| Column | Description | Data Type |
|--------|-------------|-----------|
| **Order_ID** | Unique order identifier | Integer/String |
| **Customer_ID** | Unique customer identifier | Integer/String |
| **Order_Date** | Date of transaction | DateTime |
| **Product_Name** | Name of product | String |
| **Product_Category** | Main product category | String |
| **Product_Subcategory** | Detailed product subcategory | String |
| **Region** | Geographic region | String |
| **Channel** | Sales channel (Online/Retail/Distributor) | String |
| **Quantity** | Order quantity | Integer |
| **Unit_Price** | Price per unit | Decimal |
| **Discount** | Discount applied | Decimal |
| **Total_Sales** | Total order sales amount | Decimal |
| **Profit** | Order profit amount | Decimal |

---

## 🏗️ Data Model Architecture

The dashboard uses a **Fact Table Model** with a single comprehensive retail sales table:

```
Retail_Sales_Synthetic
├── Customer Details (Customer_ID, Region, Channel)
├── Product Details (Product_Name, Product_Category, Product_Subcategory)
├── Order Details (Order_ID, Order_Date, Quantity, Unit_Price, Discount)
└── Financial Metrics (Total_Sales, Profit)
```

**Date Hierarchy:**
- Calendar dates extracted from Order_Date
- Monthly and yearly groupings for time intelligence analysis

---

## 🧮 DAX Measures

All measures are built using DAX calculations for real-time KPI computation.

### Sales Metrics

#### 1️⃣ Total Sales
```dax
Total Sales = SUM('Retail_Sales_Synthetic'[Total_Sales])
```
**Purpose:** Sum all order sales amounts  
**Use Case:** Sales KPI card, revenue trend analysis

### Profitability Metrics

#### 2️⃣ Total Profit
```dax
Total Profit = SUM('Retail_Sales_Synthetic'[Profit])
```
**Purpose:** Sum all order profits  
**Use Case:** Profitability KPI card, margin analysis

#### 3️⃣ Profit Margin %
```dax
Profit Margin % = DIVIDE([Total Profit], [Total Sales]) * 100
```
**Purpose:** Calculate profitability percentage  
**Use Case:** Margin tracking, profitability trends

### Order Metrics

#### 4️⃣ Total Orders
```dax
Total Orders = DISTINCTCOUNT('Retail_Sales_Synthetic'[Order_ID])
```
**Purpose:** Count unique orders  
**Use Case:** Order volume tracking, sales performance

#### 5️⃣ Average Order Value (AOV)
```dax
Average Order Value (AOV) = DIVIDE([Total Sales], [Total Orders])
```
**Purpose:** Calculate average value per order  
**Use Case:** Customer value assessment, sales performance analysis

---

## 📈 Dashboard Features

### 1️⃣ Sales Performance Metrics
- Total Sales KPI card
- Total Profit KPI card
- Total Orders KPI card
- Profit Margin % gauge/metric

### 2️⃣ Trend Analysis
- Monthly sales trend visualization
- Yearly sales performance comparison
- Sales trends by product category
- Profit trends over time

### 3️⃣ Product Category Analysis
- Sales by product category
- Profit by product category
- Top-performing categories identification
- Category-wise profit margin comparison

### 4️⃣ Regional Performance
- Sales by region/territory
- Regional profit distribution
- Regional sales contribution analysis
- Regional performance comparison

### 5️⃣ Channel Performance
- Sales by channel (Online/Retail/Distributor)
- Profit by channel
- Channel-wise performance metrics
- Channel comparison analysis

### 6️⃣ Customer Insights
- High-value customers identification
- Customer purchase patterns
- Order frequency analysis

### 7️⃣ Interactive Filters & Slicers
- Filter by product category
- Filter by region
- Filter by channel
- Filter by date range
- Cross-filtering across all visuals

---

## ⚙️ Installation & Prerequisites

### System Requirements
- **Microsoft Power BI Desktop** (Latest version recommended)
- **Windows 10** or later
- **2GB RAM** minimum (4GB+ recommended)
- **1GB** free disk space

### Installation Steps

```
1. Download Power BI Desktop
   → https://powerbi.microsoft.com/downloads/

2. Download the Dashboard File
   → Retail_Sales_Dashboard.pbix

3. Open Power BI Desktop

4. File → Open → Select Retail_Sales_Dashboard.pbix

5. Wait for data model to load

6. Click "Refresh" to load latest data
```

---

## 📊 How to Use

### Viewing the Dashboard

**Step 1: Open the File**
```
Power BI Desktop → File → Open → Retail_Sales_Dashboard.pbix
```

**Step 2: Navigate Between Pages**
- Switch between different dashboard views using tabs
- Each tab shows different sales perspectives

**Step 3: Use Interactive Elements**

| Feature | Action |
|---------|--------|
| **Slicers** | Click to filter by Product Category, Region, Channel, Date |
| **KPI Cards** | View summary metrics at a glance |
| **Charts & Graphs** | Hover to see tooltips with detailed values |
| **Cross-Filtering** | Click on chart elements to filter other visuals |

### Interpreting the Data

- **KPI Cards** → Quick summary of key sales metrics
- **Line Charts** → Sales and profit trends over time
- **Column Charts** → Category and channel comparison
- **Tables** → Detailed transaction-level view
- **Pie/Donut Charts** → Proportion breakdown (channel, category distribution)
- **Gauge Charts** → Profit margin percentage tracking

---

## 💡 Key Insights

### Sales Performance
✅ Track **total sales volume** across all dimensions  
✅ Monitor **sales trends** by month, quarter, and year  
✅ Identify **top-performing product categories** and SKUs  
✅ Compare **sales across regions and channels**  

### Profitability Analysis
✅ Monitor **profit margins** by product category  
✅ Track **profitability trends** over time  
✅ Identify **high-profit product categories**  
✅ Analyze **channel profitability** comparison  

### Customer Insights
✅ Identify **high-value customers** and purchasing patterns  
✅ Measure **order frequency** and customer engagement  
✅ Analyze **customer purchasing behavior** by region and channel  

### Operational Intelligence
✅ Evaluate **channel performance** (online vs retail vs distributor)  
✅ Monitor **regional sales contribution**  
✅ Track **order volume and average order value**  

### Strategic Decision-Making
✅ **Simplifies sales analysis** using unified dashboard  
✅ Enables **inventory optimization** strategies  
✅ Provides **actionable insights** for sales leaders  
✅ Supports **data-driven pricing and promotion** decisions  

---

## 🧰 Tech Stack

| Component | Technology |
|-----------|------------|
| **Platform** | Power BI Desktop |
| **Language** | DAX (Data Analysis Expressions) |
| **Data Model** | Fact Table (Tabular Model) |
| **Data Source** | Retail_Sales_Synthetic.csv |
| **Visualization** | Power BI native visuals |

---

## 📁 Project Files

**File:** `Retail_Sales_Dashboard.pbix`
- Power BI report file
- Contains all data model, measures, and visuals
- Ready for immediate use
- Scalable for production environments

---

## 🎓 Learning Outcomes

By working with this dashboard, you'll gain proficiency in:

✅ **Fact table data modeling** in Power BI  
✅ **DAX formula creation** for business metrics  
✅ **KPI development** and sales performance tracking  
✅ **Interactive dashboard design** with cross-filtering  
✅ **Sales analytics** principles and techniques  
✅ **Time-based analysis** for trend visualization  
✅ **Business intelligence** fundamentals  
✅ **Retail analytics** best practices  

---

## 📝 Notes

- Dataset is **synthetic** for demonstration/learning purposes
- All **DAX measures are production-ready** and optimized
- **Single fact table** structure enables efficient calculations
- **Multiple filter dimensions** allow flexible sales analysis
- Dashboard is **scalable** to larger retail datasets
- **Date hierarchy** supports monthly and yearly analysis

---

*This Power BI Retail Sales Performance Dashboard project demonstrates practical business intelligence expertise in sales analytics, combining fact table data modeling with DAX calculations and interactive visualizations to enable data-driven decisions through comprehensive monitoring of sales performance, profitability, and customer behavior across product categories, regions, and channels.*
