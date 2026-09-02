# 🚀 Unified Marketing Data Warehouse

## Overview

The Unified Marketing Data Warehouse project demonstrates how campaign performance data from multiple advertising platforms can be consolidated into a centralized reporting model.

Marketing teams often manage campaigns across various platforms, each with different data structures and reporting formats. This project showcases a scalable approach to integrating, standardizing, and analyzing marketing data from multiple sources.

The solution simulates a modern marketing data warehouse using Python, SQL, Jupyter Notebooks, and dimensional modeling concepts.

---

## 🎯 Business Problem

Marketing performance data is generated across multiple advertising platforms:

- Google Ads
- Meta Ads
- DV360
- LinkedIn Ads
- TikTok Ads
- CM360
- Amazon Advertising

Challenges include:

- Data silos across platforms
- Different metric definitions
- Manual reporting efforts
- Lack of a single source of truth
- Difficult cross-channel analysis

---

## ✅ Solution

A centralized marketing data warehouse that:

- Integrates cross-channel marketing data
- Standardizes campaign metrics
- Creates a unified reporting layer
- Enables cross-platform performance analysis
- Supports scalable reporting and dashboarding

---

# 🏗 Solution Architecture

```text
Google Ads
Meta Ads
DV360
LinkedIn Ads
TikTok Ads
CM360
Amazon Ads
        │
        ▼
     Extract
        │
        ▼
   Transform
        │
        ▼
 Staging Layer
        │
        ▼
 Marketing Data Warehouse
        │
        ▼
 Reporting & Analytics
```

---

## Repository Structure

```text
unified-marketing-data-warehouse
│
├── README.md
│
├── architecture/
│   └── data_warehouse_architecture.png
│
├── sample_data/
│   ├── google_ads.csv
│   ├── meta_ads.csv
│   ├── dv360.csv
│   └── linkedin_ads.csv
│
├── notebooks/
│   ├── data_integration.ipynb
│   └── performance_analysis.ipynb
│
├── sql/
│   ├── staging_tables.sql
│   ├── fact_campaign_performance.sql
│   └── reporting_queries.sql
│
├── python/
│   ├── extract.py
│   ├── transform.py
│   └── load.py
│
├── data_model/
│   └── star_schema.md
│
└── docs/
    └── warehouse_design.md
```

---

# 📊 Data Sources

The project simulates campaign data from major marketing platforms.

| Platform | Data Type |
|-----------|------------|
| Google Ads | Search Campaigns |
| Meta Ads | Social Campaigns |
| DV360 | Programmatic Media |
| LinkedIn Ads | B2B Campaigns |

---

# 🔄 ETL Workflow

## Extract

Campaign performance data is collected from source files.

Examples:

```text
google_ads.csv
meta_ads.csv
dv360.csv
linkedin_ads.csv
```

---

## Transform

Data standardization includes:

- Platform normalization
- Campaign mapping
- KPI calculations
- Data quality checks

Calculated metrics:

```text
CTR
CPC
CPM
ROAS
Conversion Rate
```

---

## Load

The transformed datasets are loaded into a unified reporting table.

Output Table:

```text
fact_campaign_performance
```

---

# 🐍 Python Components

## extract.py

Responsible for reading source datasets.

Example:

```python
read_google_ads()
read_meta_ads()
read_dv360()
```

---

## transform.py

Applies business transformations.

Example:

```python
CTR = Clicks / Impressions

CPC = Cost / Clicks

ROAS = Revenue / Cost
```

---

## load.py

Creates reporting-ready datasets.

Example Output:

```text
fact_campaign_performance.csv
```

---

# 📓 Notebooks

## data_integration.ipynb

Demonstrates:

- Reading multiple source files
- Standardizing schemas
- Merging data
- Creating unified reporting tables

---

## performance_analysis.ipynb

Demonstrates:

- KPI calculations
- Platform comparisons
- Spend analysis
- Performance trends

---

# ⭐ Data Model

## Fact Table

### fact_campaign_performance

Stores campaign performance metrics:

```text
Date
Platform
Campaign Name
Impressions
Clicks
Cost
Conversions
Revenue
```

---

## Dimension Tables

### dim_platform

```text
Platform ID
Platform Name
```

### dim_campaign

```text
Campaign ID
Campaign Name
Campaign Objective
```

### dim_date

```text
Date
Month
Quarter
Year
```

---

# 🌟 Star Schema Design

```text
             dim_date
                 │
                 │
dim_platform ─ fact_campaign_performance ─ dim_campaign
```

---

# 💾 SQL Layer

## staging_tables.sql

Creates staging tables.

Example:

```sql
CREATE TABLE stg_google_ads (
    date DATE,
    campaign_name STRING,
    impressions INT64,
    clicks INT64,
    cost FLOAT64
);
```

---

## fact_campaign_performance.sql

Creates a unified fact table.

Example:

```sql
SELECT *
FROM stg_google_ads

UNION ALL

SELECT *
FROM stg_meta_ads

UNION ALL

SELECT *
FROM stg_dv360;
```

---

## reporting_queries.sql

Reporting-ready metrics.

Example:

```sql
SELECT
    platform,
    SUM(cost) AS spend,
    SUM(clicks) AS clicks,
    SUM(impressions) AS impressions
FROM fact_campaign_performance
GROUP BY platform;
```

---

# 📈 Marketing KPIs

### CTR

```text
Clicks / Impressions × 100
```

### CPC

```text
Cost / Clicks
```

### CPM

```text
(Cost / Impressions) × 1000
```

### Conversion Rate

```text
Conversions / Clicks × 100
```

### ROAS

```text
Revenue / Cost
```

---

# 📊 Example Reporting Use Cases

## Executive Dashboard

Tracks:

```text
Total Spend
Total Revenue
ROAS
Conversions
```

## Platform Performance

Tracks:

```text
Google Ads
Meta Ads
DV360
LinkedIn Ads
```

## Campaign Analysis

Tracks:

```text
Top Campaigns
Best Performing Platforms
Spend Trends
Conversion Trends
```

---

# 🛠 Tech Stack

## Programming

- Python
- SQL

## Data Processing

- Pandas
- NumPy

## Analysis

- Jupyter Notebook

## Marketing Platforms

- Google Ads
- Meta Ads
- DV360
- LinkedIn Ads
- CM360
- TikTok Ads
- Amazon Advertising

## Data Warehousing

- Star Schema
- Fact Tables
- Dimension Tables
- Marketing Data Modeling

## Reporting

- Looker Studio
- Power BI

## Cloud Concepts

- Google Cloud Platform (GCP)
- BigQuery
- Data Warehousing Architecture

---

# 📌 Business Impact

### Reporting Efficiency

- Reduced manual reporting effort
- Faster campaign analysis
- Standardized KPI reporting

### Data Quality

- Consistent metric calculations
- Unified campaign reporting
- Improved governance

### Scalability

- Supports additional marketing platforms
- Modular ETL architecture
- Flexible reporting layer

---

# 🔮 Future Enhancements

- API-based ingestion
- Automated ETL scheduling
- Data quality monitoring
- Marketing attribution modeling
- Real-time dashboard integration
- Incremental data processing

---

# 📈 Project Impact

Designed a centralized marketing data warehouse that consolidates campaign performance data from multiple advertising platforms into a unified reporting layer. Implemented ETL concepts, dimensional modeling, SQL reporting logic, and cross-channel performance analysis to create a scalable foundation for marketing analytics and business intelligence.

---

## 👩‍💻 Author

**Deepika Devi**

### Skills Demonstrated

- Marketing Analytics
- Data Engineering
- SQL
- Python
- Pandas
- ETL Design
- Data Warehousing
- Dimensional Modeling
- Campaign Reporting
- Marketing Performance Analysis
