# 📊 Sales Data Analytics Project

> End-to-end data analytics pipeline — from raw Excel/CSV files to an interactive Power BI dashboard.

---

## 🗂️ Project Overview

The Sales Data Analyst Project is an end-to-end data analytics project designed to transform raw sales data into meaningful business insights using Python, MySQL, and Power BI.

The project begins with cleaning and preprocessing the dataset using Python (Pandas). The cleaned data is then imported into MySQL, where SQL queries are used for validation and business analysis. Finally, the processed data is connected to Power BI to build interactive dashboards that help visualize sales performance, profitability, regional trends, product category performance, discounts, and customer return patterns.

The dashboards enable users to analyze sales data across different years, regions, states, and product categories through dynamic filters and interactive visualizations. This project demonstrates the complete data analytics workflow, from raw data processing to business intelligence reporting.

---

## 📁 Project Structure

```
sales-analytics-project/
│
├── data/
│   ├── raw/                    # Original Excel / CSV files (4 files)
│   │   ├── mainsales2.csv
│   │   ├── customer.csv
│   │   ├── product.csv
│   │   └── city.csv
│   └── cleaned/                # Cleaned output files after Pandas processing
│       ├── mainsales2_clean.csv
│       ├── customer_clean.csv
│       ├── product_clean.csv
│       └── city_clean.csv
│
├── Python/
│   └── data_cleaning.ipynb     # Pandas data cleaning notebook
│
├── sql/
│   └── queries.sql             # All SQL queries used for analysis
│
├── power BI/
│   └── sales_dashboard.pbix    # Power BI dashboard file
│
├── screenshots/                # Dashboard screenshots (3 pages)
│   ├── page1_overview.png
│   ├── page2_customer.png
│   └── page3_product.png
│
└── README.md
```

---

## 🗃️ Data Sources

| File | Description | Key Columns |
|---|---|---|
| `mainsales2.csv` | Main sales transactions (fact table) | SaleID, CustomerID, ProductID, CityID, Amount, Date |
| `customers.csv` | Customer dimension table | CustomerID, Name, Age, Segment |
| `products.csv` | Product dimension table | ProductID, ProductName, Category, Price |
| `city.csv` | City/location dimension table | CityID, City, State, Region |

---

## ⚙️ Workflow

### Step 1 — Data Cleaning with Python (Pandas)

**Notebook:** `python /data_cleaning.ipynb`

- Loaded all 4 raw CSV/Excel files into Pandas DataFrames
- Removed duplicate rows from each table
- Handled missing/null values — filled or dropped based on column importance
- Standardized column names (lowercase, underscores, no spaces)
- Fixed incorrect data types (e.g., dates parsed as strings → datetime)
- Removed leading/trailing whitespace from text columns
- Validated foreign keys — ensured CustomerID, ProductID, CityID matched across tables
- Exported cleaned files to `data/cleaned/`

---

### Step 2 — SQL Analysis

**File:** `sql/queries.sql`

After cleaning, data was loaded into a SQL database (SQLite / PostgreSQL / MySQL) and the following queries were run:

- Total sales revenue by city and region
- Top 10 best-selling products by revenue and quantity
- Customer segmentation analysis (high/medium/low value customers)
- Month-over-month and year-over-year sales trends
- Sales performance by product category
- Average order value per customer segment
- Revenue contribution by city tier
- JOIN queries across all 4 tables to build a master sales view

---

### Step 3 — Power BI Dashboard

**File:** `dashboard/sales_dashboard.pbix`

Cleaned data was imported into Power BI.  
Relationships were set between all 4 tables using their respective ID columns.  
DAX measures were created for KPIs like Total Revenue, Avg Order Value, and Growth %.

---

## 📊 Dashboard Pages

### Page 1 — Sales Overview

> High-level KPIs and overall performance at a glance.

- Total Revenue, Total Orders, total profit ,profit margin  (KPI cards)
- Revenue by Region (Bar / )
- Sales by Product Category (Donut Chart)
- high profit category
- average dicoutby category

![Sales Overview](https://github.com/aanjanakailash/First-Data-Analyst-Project-By-Kailash-J-Choudhary/blob/0844a4bf2468f9ff51455c65b66038313ee404cf/Screenshots/Screenshot%202026-06-27%20112327.png))

---

### Page 2 — Customer Analysis

> Deep dive into customer behavior and segmentation.

- count total order by region(Pi chart)
- Monthly Sales Trend (Line Chart)
- count cancel orderd by region (pi chart)
 


![Customer Analysis](https://github.com/aanjanakailash/First-Data-Analyst-Project-By-Kailash-J-Choudhary/blob/e937299c693d708361eb96b5b867bf62ab063ac6/Screenshots/Screenshot%202026-06-27%20112338.png))

---

### Page 3 — Product Performance

>  find insights(critical,warning,watch)

![Product Performance](https://github.com/aanjanakailash/First-Data-Analyst-Project-By-Kailash-J-Choudhary/blob/e937299c693d708361eb96b5b867bf62ab063ac6/Screenshots/Screenshot%202026-06-27%20112349.png))

---

## 🛠️ Tools & Technologies

| Tool 
| Excel
| Python 
| Pandas 
| SQL 
| Power BI Desktop 
| Git & GitHub 


## 🚀 How to Run This Project

1. Clone this repository
   ```
   git clone https://github.com/your-username/sales-analytics-project.git
   ```

2. Install Python dependencies
   ```
   pip install pandas openpyxl jupyter sqlalchemy
   ```

3. Open and run `notebooks/data_cleaning.ipynb` to clean the raw data

4. Execute `sql/queries.sql` in your preferred SQL environment

5. Open `dashboard/sales_dashboard.pbix` in Power BI Desktop

---

## 📌 Future Improvements

- [ ] Automate the data cleaning pipeline using a Python script (`.py`) instead of just a notebook
- [ ] Schedule SQL queries using Apache Airflow or a simple cron job
- [ ] Add Python-based visualizations (Matplotlib / Seaborn / Plotly) as an alternative to Power BI
- [ ] Connect Power BI directly to a live SQL database instead of CSV imports
- [ ] Add a machine learning model to forecast future sales (using Scikit-learn)
- [ ] Deploy the dashboard to Power BI Service for online sharing
- [ ] Add data validation tests using `Great Expectations` library

---

## 🙋 Author

**Kailash J Choudhary**  
📧 kailashhkumarr30@gmail.com
🔗 [LinkedIn](linkedin.com/in/kailash-j-choudhary-b39325300) | 

---

## 📄 License

This project is open source and available under the [MIT License](LICENSE).
