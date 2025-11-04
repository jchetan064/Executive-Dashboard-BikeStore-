# 🚴‍♂️ Executive-Dashboard-BikeStore-
A complete data analytics project using SQL, Excel, and Tableau on the BikeStores dataset. Includes database creation, data loading, and sales performance analysis with an interactive Tableau dashboard showcasing revenue, top brands, and regional insights.

---

## 📘 Project Overview
The goal is to analyze **bike sales performance** across stores, products, and sales representatives using the BikeStores dataset.

---

## 🛠️ Tools Used
- **SQL Server** – Database creation, data loading, and querying.
- **Excel** – Data cleaning, aggregation, and pivot analysis.
- **Tableau** – Interactive dashboard creation.

---

## 📂 Project Files
| Folder | Description |
|--------|-------------|
| `SQL/` | Scripts to create, load, and drop database objects. |
| `Data/` | Contains Excel workbook used for analysis. |
| `Tableau/` | Tableau workbook (`.twb`) and packaged workbook (`.twbx`). |
| `Images/` | Project logo or dashboard snapshot. |

---

## 🧩 SQL Pipeline
1. **Create Database and Schemas:**  
   `BikeStores Sample Database - create objects.sql`
2. **Load Data into Tables:**  
   `BikeStores Sample Database - load data.sql`
3. **Drop Database Objects (optional):**  
   `BikeStores Sample Database - drop all objects.sql`
4. **Data Analysis Query:**  
   `SQLQuery2.sql` — joins multiple tables to calculate revenue, sales units, and representative details.

```sql
select ord.order_id,
       CONCAT(cus.first_name,' ',cus.last_name) as customers,
       cus.city, cus.state,
       ord.order_date,
       SUM(ite.quantity) as total_units,
       SUM(ite.quantity*ite.list_price) as revenue,
       pro.product_name,
       cat.category_name,
       bra.brand_name,
       sto.store_name,
       CONCAT(sta.first_name,' ',sta.last_name) as sales_rep
from ...
group by ...
