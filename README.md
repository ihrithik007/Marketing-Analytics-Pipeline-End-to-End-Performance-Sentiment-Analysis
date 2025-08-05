# ShopEasy Customer Analytics Dashboard

## 📊 Project Overview

This end-to-end data analytics project tackles a real-world business problem for an online retailer ("ShopEasy") experiencing a decline in customer engagement and conversion rates. The project covers the full data lifecycle:

- Business understanding
- Data cleaning and transformation with SQL
- Sentiment analysis using Python (NLTK)
- Data visualization in Power BI
- Insight communication via PowerPoint

The final deliverable is a dynamic, multi-page Power BI dashboard and a stakeholder-facing presentation highlighting actionable insights.

---

## 🛠️ Technology Stack

| Layer                     | Tool/Language            |
|--------------------------|--------------------------|
| Database                 | SQL Server               |
| Data Transformation      | SQL                      |
| Sentiment Analysis       | Python (Pandas, NLTK)    |
| Data Visualization       | Power BI (DAX)           |
| Presentation             | PowerPoint               |

---

## 🚀 End-to-End Implementation

### ✅ Step 1: Business Understanding

- Defined KPIs: Conversion Rate, Engagement Rate, Avg. Order Value, Sentiment Score
- Identified data sources: 
  - Fact Tables: `CustomerJourney`, `EngagementData`, `CustomerReviews`
  - Dimension Tables: `Customers`, `Geography`, `Products`

---

### 🧹 Step 2: Data Cleaning & Transformation (SQL Server)

- **Products Table**: Categorized product prices using `CASE` statements.
- **Customers + Geography**: Merged using `LEFT JOIN` for optimized data modeling.
- **Customer Reviews**: Cleaned text (e.g., fixed double spaces).
- **Engagement Data**:
  - Standardized text using `UPPER()`
  - Split combined views/clicks using `LEFT()` and `RIGHT()`
- **Customer Journey**:
  - De-duplicated using `ROW_NUMBER()` with CTE
  - Imputed nulls in duration using AVG over visit date with subquery

---

### 🤖 Step 3: Sentiment Analysis (Python)

- Connected to SQL Server using Python
- Cleaned and analyzed text reviews using **NLTK**
- Added:
  - `sentiment_score` (range: -1 to 1)
  - `sentiment_category` (e.g., “high rating + positive sentiment”)
  - `sentiment_bucket` (e.g., “strongly negative”)
- Exported enriched data to CSV for Power BI

---

### 📈 Step 4: Dashboard in Power BI

- Modeled data using **star schema**
- Imported SQL-cleaned data + Python sentiment CSV
- Created custom **calendar table** with DAX
- Built DAX measures for key metrics:
  - Clicks, Views, Avg. Rating, Conversion Rate
- Dashboard Pages:
  1. Overview
  2. Conversion Details
  3. Social Media Details
  4. Customer Reviews
- Used visuals: KPI cards, line charts, funnel charts, scatter plots
- Added slicers: Product Name, Year, Month

---

### 🗣️ Step 5: Data Storytelling

- Exported Power BI visuals to PowerPoint
- Structured presentation to align with business problems
- Highlighted:
  - Key trends in engagement and sentiment
  - Product/category performance
  - Targeted, actionable recommendations

---

## 🧰 Installation & Run Instructions

### 1. Prerequisites

- SQL Server (with database setup)
- Python 3.8+
- Power BI Desktop
- PowerPoint (for final presentation)
- Git

---

### 2. Clone the Repository

```bash
git clone https://github.com/yourusername/shopeasy-customer-analytics.git
cd shopeasy-customer-analytics
```

## 3. Set Up the SQL Server Database

Open the `sql/` folder.

Run the scripts in the following order:

1. `create_tables.sql`
2. `load_data.sql`
3. `data_cleaning_transformation.sql`

> ✅ Ensure you're connected to your SQL Server instance and have the necessary permissions.

---

## 4. Run Python Sentiment Analysis

### Install dependencies:

```bash
pip install pandas nltk pyodbc
```

### Run the Python script:

```bash
python python/sentiment_analysis.py
```

This script will:

- Connect to SQL Server
- Retrieve customer review data
- Perform sentiment analysis
- Save `enriched_reviews.csv` to the `output/` folder

---

## 5. Open Power BI Dashboard

1. Launch **Power BI Desktop**
2. Open the file: `powerbi/ShopEasyDashboard.pbix`
3. Update data connections:
   - ✅ SQL Server connection string
   - ✅ CSV path: `output/enriched_reviews.csv`

---

## 6. Presentation

Open the file: `presentation/ShopEasy_Insights.pptx` for a business-friendly summary of the insights.

---

## 📌 Key Results

- Identified customer segments with low engagement
- Highlighted underperforming content types
- Linked positive/negative sentiment with product categories
- Improved understanding of conversion funnels

## 📁 Folder Structure
```bash
shopeasy-customer-analytics/
├── sql/
│   ├── create_tables.sql
│   ├── load_data.sql
│   └── data_cleaning_transformation.sql
├── python/
│   └── sentiment_analysis.py
├── powerbi/
│   └── ShopEasyDashboard.pbix
├── presentation/
│   └── ShopEasy_Insights.pptx
└── output/
    └── enriched_reviews.csv
```


