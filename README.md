# BnBTrend Insights – Airbnb Booking Trends in NYC

A cloud-based data analytics solution using **AWS services** and **Amazon QuickSight** to analyze Airbnb booking trends, pricing, and customer reviews in New York City. This project helps Airbnb identify optimal pricing strategies and potential areas for expansion.

---

## 📌 Problem Statement

Airbnb wants to understand how customer reviews and pricing are interrelated to:
- Set competitive prices
- Identify growth opportunities across NYC
- Enhance guest satisfaction based on room types and neighborhood demand

---

## 🧠 Goal

Develop a cloud-based solution that integrates structured and unstructured data sources, performs ETL using AWS, and visualizes insights using **Amazon QuickSight** dashboards.

---

## 🧰 Tech Stack

- **Cloud Platform:** AWS (S3, Lambda, Glue, RDS, VPC, CloudWatch, IAM)
- **ETL Tools:** AWS Glue, Python
- **Automation:** AWS Lambda
- **Database:** AWS RDS (MySQL/PostgreSQL)
- **Visualization:** Amazon QuickSight
- **Languages:** Python, SQL
- **Data Sources:**
  - Structured CSV from Inside Airbnb (2023 listings)
  - API-based unstructured listing details

---

## 🗃️ Data Modeling

### Fact Table:
- `Fact_Listings`

### Dimension Tables:
- `Dim_Host`
- `Dim_Location`
- `Dim_Neighbourhood`
- `Dim_Neighbourhood_Group`
- `Dim_Room_Type`

Used **Kimball’s 4-step dimensional modeling** to define grain, dimensions, and facts for booking analysis.

---

## 🛠️ AWS Architecture

1. **S3** stores raw Airbnb data
2. **AWS Lambda** automates data extraction and loading
3. **AWS Glue** performs transformation and ETL jobs
4. **AWS RDS** stores cleaned and structured OLAP data
5. **CloudWatch** monitors scheduled ETL jobs
6. **IAM** ensures role-based permissions and security
7. **Amazon QuickSight** connects to RDS for interactive dashboards

<p align="center">
  <img src="diagrams/aws_architecture.png" alt="AWS Architecture Diagram" width="600"/>
</p>

---

## 📊 QuickSight Dashboards

| Metric | Insight |
|--------|---------|
| **Total Bookings** | Manhattan has the highest number, Staten Island the lowest |
| **Room Type Demand** | Brooklyn dominates in private room bookings |
| **Average Price/Night** | Staten Island is the most expensive, Bronx the cheapest |
| **Review Counts** | Brooklyn listings receive the most reviews |
| **Price Distribution** | Ranges from $55 to $900+ per night |

---

## 🔁 ETL Flow

```text
Raw CSV/API Data → S3 → AWS Lambda → AWS Glue (ETL) → RDS → QuickSight Dashboards
