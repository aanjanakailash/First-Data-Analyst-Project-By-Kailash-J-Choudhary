# 📊 Sales Data Analytics Project

> End-to-end data analytics pipeline — from raw Excel/CSV files to an interactive Power BI dashboard.

---

## 🗂️ Project Overview

This project demonstrates a complete data analytics workflow using **Python (Pandas)**, **SQL**, and **Power BI**.  
Raw sales data is cleaned, queried, and visualized across a 3-page interactive dashboard.

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
├── notebooks/
│   └── data_cleaning.ipynb     # Pandas data cleaning notebook
│
├── sql/
│   └── queries.sql             # All SQL queries used for analysis
│
├── dashboard/
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
| `customer.csv` | Customer dimension table | CustomerID, Name, Age, Segment |
| `product.csv` | Product dimension table | ProductID, ProductName, Category, Price |
| `city.csv` | City/location dimension table | CityID, City, State, Region |

---

## ⚙️ Workflow

### Step 1 — Data Cleaning with Python (Pandas)

**Notebook:** `notebooks/data_cleaning.ipynb`

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

- Total Revenue, Total Orders, Avg Order Value (KPI cards)
- Monthly Sales Trend (Line Chart)
- Revenue by Region (Bar / Map Chart)
- Sales by Product Category (Donut Chart)

![Sales Overview](https://github.com/aanjanakailash/First-Data-Analyst-Project-By-Kailash-J-Choudhary/blob/0844a4bf2468f9ff51455c65b66038313ee404cf/Screenshots/Screenshot%202026-06-27%20112327.png))

---

### Page 2 — Customer Analysis

> Deep dive into customer behavior and segmentation.

- Customer Segment Distribution (Pie Chart)
- Top 10 Customers by Revenue (Horizontal Bar Chart)
- Customer Count by City (Map / Treemap)
- Revenue per Customer Segment over Time (Line Chart)

![Customer Analysis](screenshots/page2_customer.png](https://github.com/aanjanakailash/First-Data-Analyst-Project-By-Kailash-J-Choudhary/blob/e937299c693d708361eb96b5b867bf62ab063ac6/Screenshots/Screenshot%202026-06-27%20112338.png))

---

### Page 3 — Product Performance

> Product-level insights for inventory and sales strategy.

- Top 10 Products by Revenue (Bar Chart)
- Product Category Performance (Matrix / Heatmap)
- Price vs Sales Volume Scatter Plot
- Low Performing Products (Filtered Table)

![Product Performance](screenshots/page3_product.png](https://github.com/aanjanakailash/First-Data-Analyst-Project-By-Kailash-J-Choudhary/blob/e937299c693d708361eb96b5b867bf62ab063ac6/Screenshots/Screenshot%202026-06-27%20112349.png))

---

## 🛠️ Tools & Technologies

| Tool | Purpose |
|---|---|
| Python 3.x | Data cleaning and transformation |
| Pandas | DataFrame manipulation |
| SQL (SQLite / PostgreSQL) | Data querying and analysis |
| Power BI Desktop | Dashboard and visualizations |
| Jupyter Notebook | Interactive data cleaning environment |
| Git & GitHub | Version control |

---

## 💡 Key Insights (from Dashboard)

- 📍 **Top Revenue City:** *(add your finding here)*
- 🛒 **Best-Selling Product:** *(add your finding here)*
- 👥 **Most Valuable Customer Segment:** *(add your finding here)*
- 📈 **Peak Sales Month:** *(add your finding here)*

---

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

**Your Name**  
📧 your.email@example.com  
🔗 [LinkedIn](https://linkedin.com/in/your-profile) | [GitHub](https://github.com/your-username)

---

## 📄 License

This project is open source and available under the [MIT License](LICENSE).
