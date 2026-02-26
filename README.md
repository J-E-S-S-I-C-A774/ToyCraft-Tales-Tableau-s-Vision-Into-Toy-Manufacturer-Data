🎯 ToyCraft Tales: Tableau's Vision Into Toy Manufacturer Data

Course: Data Analytics and Tableau

📌 STEP 1: Project Overview
🎯 Objective

To analyze toy manufacturer sales data using MySQL and Tableau, and build an interactive dashboard that helps business decision-making.

📌 STEP 2: MySQL Database Setup
1️⃣ Create Database
CREATE DATABASE toycraft_db;
USE toycraft_db;
2️⃣ Create Table
CREATE TABLE toy_sales (
    order_id INT,
    order_date DATE,
    region VARCHAR(50),
    manufacturer VARCHAR(100),
    category VARCHAR(100),
    product_name VARCHAR(150),
    units_sold INT,
    sales DECIMAL(10,2),
    profit DECIMAL(10,2)
);
3️⃣ Import Data

Use MySQL Workbench

Table → Import Wizard

Select CSV file

4️⃣ Important SQL Queries Used
🔹 Total Revenue
SELECT SUM(sales) AS total_revenue FROM toy_sales;
🔹 Profit by Category
SELECT category, SUM(profit) 
FROM toy_sales
GROUP BY category;
🔹 Regional Performance
SELECT region, SUM(sales), SUM(profit)
FROM toy_sales
GROUP BY region;
📌 STEP 3: Connect MySQL to Tableau

Open Tableau

Connect → MySQL

Enter:

Server: localhost

Username

Password

Select database → toycraft_db

Drag table to canvas

📌 STEP 4: Data Preparation in Tableau
✔ Clean Data

Check null values

Rename columns

Change date format

✔ Create Calculated Fields
1️⃣ Profit Margin
SUM([Profit]) / SUM([Sales])
2️⃣ Year Field
YEAR([Order Date])
3️⃣ Growth Rate
(SUM([Sales]) - LOOKUP(SUM([Sales]), -1)) 
/ ABS(LOOKUP(SUM([Sales]), -1))
📌 STEP 5: Build Advanced Dashboard
🎯 Dashboard 1: Executive Overview

Include:

KPI Cards:

Total Revenue

Total Profit

Profit Margin %

Total Units Sold

Line Chart → Monthly Sales Trend

Bar Chart → Category Sales

Map → Regional Sales

Pie/Donut → Manufacturer Share

📌 STEP 6: Interactive Filters

Add Filters:

Region

Category

Manufacturer

Date Range

Right-click filter → Apply to Worksheets → All using this data source

✅ Interactive filters allow dynamic exploration of data.

📌 STEP 7: Dashboard Design Best Practices

Your dashboard must follow:

✔ Use consistent color theme
✔ Avoid too many colors
✔ Use white background
✔ Proper spacing
✔ Align objects properly
✔ Use readable font
✔ Place KPIs at top

✅ Dashboard design follows best data visualization practices.

📌 STEP 8: Create Tableau Story

Click → New Story

🎯 Story Structure
Slide 1 – Project Introduction

Objective & dataset summary

Slide 2 – Revenue Analysis

Monthly & yearly trend

Slide 3 – Category Insights

Top & low performing categories

Slide 4 – Regional Insights

High growth regions

Slide 5 – Manufacturer Analysis

Top profitable manufacturers

Slide 6 – Final Recommendations

Strategic suggestions

📌 STEP 9: Flask Web Application (VS Code)

This is for advanced submission (extra marks).

🔹 Project Folder Structure
toycraft_project/
│
├── app.py
├── templates/
│     └── index.html
└── static/
🔹 Install Flask
pip install flask
🔹 app.py
from flask import Flask, render_template

app = Flask(__name__)

@app.route("/")
def home():
    return render_template("index.html")

if __name__ == "__main__":
    app.run(debug=True)
🔹 index.html (BootstrapMade Style Template)

Use BootstrapMade template (like "Arsha" or "BizLand")

Paste this inside templates/index.html:

<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>ToyCraft Tales Dashboard</title>
  <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.2/dist/css/bootstrap.min.css" rel="stylesheet">
</head>
<body>

<nav class="navbar navbar-dark bg-dark">
  <div class="container-fluid">
    <span class="navbar-brand">ToyCraft Tales</span>
  </div>
</nav>

<div class="container mt-4">
  <h2 class="text-center">Tableau Dashboard</h2>

  <div class="ratio ratio-16x9">
    <iframe 
      src="PASTE_YOUR_TABLEAU_PUBLIC_LINK_HERE"
      frameborder="0"
      allowfullscreen>
    </iframe>
  </div>
</div>

</body>
</html>
🔹 Run Project
python app.py

Open:

http://127.0.0.1:5000/

🎯 Final Conclusion

ToyCraft Tales transforms raw sales data into actionable business intelligence using:

MySQL (Data Storage)

Tableau (Visualization)

Flask (Deployment)

Bootstrap (UI Design)

This project demonstrates real-world data analytics implementation suitable for business environments.


👩‍💻 Author

Alexander Mercelin Jessica B.Sc Statistics Student Tableau Data Visualization Project
