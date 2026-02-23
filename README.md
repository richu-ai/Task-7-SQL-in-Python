# 📊 Task 7 – Basic Sales Summary using SQLite and Python

## 📌 Objective
The objective of this task is to use SQL inside Python to extract basic sales information from a small SQLite database and visualize the results using a simple bar chart.

This task demonstrates how SQL and Python can work together for data analysis.

---

## 🛠 Tools Used
- Python
- SQLite (sqlite3 module)
- pandas
- matplotlib
- Jupyter Notebook

---

## 📂 Database Details

Database Name: `sales_data.db`

Table Name: `sales`

Columns:
- product (TEXT)
- quantity (INTEGER)
- price (REAL)

---

## 🧠 SQL Query Used

```sql
SELECT 
    product,
    SUM(quantity) AS total_quantity,
    SUM(quantity * price) AS revenue
FROM sales
GROUP BY product;
```

### Purpose:
- Calculate total quantity sold per product
- Calculate total revenue per product
- Group results using `GROUP BY`

---

## 🐍 Python Implementation

### 1️⃣ Connect to SQLite Database
```python
import sqlite3
conn = sqlite3.connect("sales_data.db")
```

### 2️⃣ Run SQL Query and Load into Pandas
```python
import pandas as pd
df = pd.read_sql_query(query, conn)
```

### 3️⃣ Print Results
```python
print(df)
```

### 4️⃣ Visualize Using Bar Chart
```python
import matplotlib.pyplot as plt
df.plot(kind="bar", x="product", y="revenue")
plt.title("Revenue by Product")
plt.ylabel("Revenue")
plt.show()
```

---

## 📊 Output
- Sales summary table printed using pandas
- Bar chart showing revenue by product
- Chart saved as `sales_chart.png`

---

## 📁 Project Structure

Task-7-SQL-in-Python  
│  
├── Task7_Sales_Summary.ipynb  
├── sales_chart.png  
├── output_screenshot.png  
└── README.md  

---

## 🎯 Key Concepts Learned
- Connecting Python to SQLite using sqlite3
- Writing SQL queries with GROUP BY
- Using pandas to read SQL results
- Performing revenue calculations using SQL
- Creating simple data visualizations with matplotlib

---

## 🎓 Conclusion
This task demonstrates how SQL can be integrated into Python to perform data analysis efficiently. By combining SQLite, pandas, and matplotlib, we generated meaningful sales summaries and visualized revenue trends effectively.
