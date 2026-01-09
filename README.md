
# 🛍️ Customer Shopping Trends Analysis
### A Full-Stack Data Analytics Portfolio Project

![Power BI Dashboard]<img width="1170" height="630" alt="image" src="https://github.com/user-attachments/assets/3d8ca516-99ab-4e63-b813-1e039baf8818" />
---

## 📋 Table of Contents
- [Project Overview](#-project-overview)
- [Business Problem](#-business-problem)
- [Tech Stack](#-tech-stack)
- [Project Workflow](#-project-workflow)
- [Key Insights & Results](#-key-insights--results)
- [Database Schema](#-database-schema)
- [How to Run This Project](#-how-to-run-this-project)
- [Future Improvements](#-future-improvements)
- [Author](#-author)

---

## 📖 Project Overview
This project is an end-to-end data analysis of a retail company's customer database. It demonstrates a complete data pipeline: **cleaning raw data** with Python, **storing and querying** it in a PostgreSQL database, and **visualizing** actionable insights in Power BI.

The goal is to transition from simple sales tracking to a proactive, data-driven strategy that improves customer retention and optimizes marketing spend.

---

## 💼 Business Problem
A leading retail company noticed shifts in purchasing patterns but lacked visibility into the drivers of consumer behavior. The management team needed to answer:
* Which demographics (Age/Gender) are the most profitable?
* Do seasonal trends impact specific product categories?
* How effective are subscription models and discounts in driving loyalty?
* Which shipping methods are preferred by high-value customers?

**Objective:** Leverage the "Customer Shopping Trends" dataset to build a dashboard that guides marketing and product strategies.

---

## 🛠 Tech Stack
| Component | Tools Used |
| :--- | :--- |
| **Data Cleaning** | Python (Pandas, NumPy) |
| **Database** | PostgreSQL, pgAdmin 4 |
| **Analysis** | SQL (Window Functions, Aggregations) |
| **Visualization** | Power BI Desktop (DAX, Interactive Dashboards) |
| **Environment** | Jupyter Notebook, Anaconda |

---

## 🔄 Project Workflow

### 1. Data Collection & Cleaning (Python)
* **Source:** `customer_shopping_behavior.csv` (3,900 records).
* **Imputation:** Handled missing `review_rating` values by filling them with the median rating of their specific **Product Category** (not the global median).
* **Standardization:** Renamed all columns to `snake_case` (e.g., `Purchase Amount (USD)` -> `purchase_amount`) for SQL compatibility.
* **Feature Engineering:** Created a new `age_group` column to segment customers into 'Young Adult', 'Adult', 'Middle-Aged', and 'Senior'.

### 2. Database Management (SQL)
* Established a connection between Python and PostgreSQL using `SQLAlchemy`.
* Loaded the processed Pandas DataFrame directly into a SQL table named `shopping_trends`.
* Verified data integrity and data types within pgAdmin.

### 3. Data Analysis (SQL Queries)
Executed complex SQL queries to extract business value:
* **Customer Segmentation:** Categorized customers into 'Platinum', 'Gold', and 'Silver' tiers based on purchase frequency.
* **Revenue Analysis:** Calculated total sales by Gender and Category.
* **Top Products:** Identified the highest-rated and most purchased items using Window Functions (`RANK()`).

### 4. Visualization (Power BI)
Built an interactive dashboard featuring:
* **KPI Cards:**
    * **Average Purchase Amount:** £59.76
    * **Average Review Rating:** 3.75
    * **No of Customers:** 3.9K
* **Slicers (Filters):**
    * Subscription Status (Yes/No)
    * Gender (Male/Female)
    * Category (Accessories, Clothing, Footwear, Outerwear)
    * Shipping Type (Express, Free Shipping, Next Day Air, etc.)
* **Visuals:**
    * **Donut Chart:** *% Customer by Subscription Status* (Visualizes the ratio of subscribers vs. non-subscribers).
    * **Column Charts:**
        * *Sum of Purchase Amount by Category* (Revenue per category).
        * *Sales by Category* (Transaction volume per category).
    * **Bar Charts:**
        * *Sum of Purchase Amount by Age* (Revenue distribution across age groups).
        * *Sales by Age* (Which age group buys the most items).
---

## 🔍 Key Insights & Results
1.  **Category Dominance:** **Clothing** is the clear leader in both revenue (£104K) and sales volume (1,737 sales), followed by **Accessories**.
2.  **Subscription Trends:** The majority of customers **(approx. 73%)** are non-subscribers, as shown in the "No vs Yes" donut chart.
3.  **Age Demographics:**
    * **Young Adults** appear to be the leading group in terms of total sales count.
    * Revenue is relatively evenly distributed across **Young Adult**, **Middle Aged**, and **Adult** groups, with **Seniors** contributing slightly less.
4.  **Customer Satisfaction:** The average review rating is stable at **3.75/5.0**, indicating generally positive customer feedback across the board.
---

## 🗄 Database Schema
The SQL table `shopping_trends` contains the following key columns:
* `customer_id` (Primary Key)
* `age` & `age_group`
* `gender`
* `item_purchased` & `category`
* `purchase_amount`
* `location`
* `size` & `color`
* `season`
* `review_rating`
* `subscription_status`
* `shipping_type`
* `discount_applied` & `promo_code_used`
* `payment_method`

---

## 🚀 How to Run This Project

### Prerequisites
* Python 3.x (Anaconda recommended)
* PostgreSQL & pgAdmin 4
* Power BI Desktop (Windows)

### Steps
1.  **Clone the Repo:**
    ```bash
    git clone[https://github.com/VihangaAmandi/Customer-Behavior-Analysis.git]
    ```
2.  **Setup Database:**
    * Create a database named `customer_shopping_behavior` in pgAdmin.
3.  **Run Python Scripts:**
    * Open `customer_shopping_behavior_analyzer.ipynb`.
    * Update the database connection string: `engine = create_engine('postgresql://postgres:12345@localhost:5432/customer_behavior')`.
    * Run all cells to load data.
4.  **Analyze in SQL:**
    * Use the queries provided in `customer_shopping_behavior.sql` to explore the data.
5.  **View Dashboard:**
    * Open `Customer_behavior_dashboard.pbix` in Power BI.
    * Refresh the data source to connect to your local SQL instance.

---

## 🔮 Future Improvements
* **Predictive Analytics:** Implement a Machine Learning model (Regression) to predict future purchase amounts based on age and category.
* **Automated Reporting:** Set up a Python script to automatically email a weekly PDF summary of the dashboard to stakeholders.

---

## 👤 Author
Vihanga Amandi
* **LinkedIn:** [Link to your Profile]
* **Portfolio:** [Link to your Website]
* **Email:** vihangaherath5@gmail.com

