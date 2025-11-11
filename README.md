# 📚 Online Bookstore SQL Database Project

![MySQL Badge](https://img.shields.io/badge/Database-MySQL-blue)
![SQL Badge](https://img.shields.io/badge/Language-SQL-lightgrey)
![License: MIT](https://img.shields.io/badge/License-MIT-green)

---

## 🧠 Project Overview

The **Online Bookstore Database Project** is a structured SQL project built to simulate the operations of a real-world online bookstore.  
It demonstrates database design, data import, and analytical SQL queries using **MySQL**.  

This project is ideal for showcasing SQL proficiency, data modeling, and query optimization skills.

---

## 🏗️ Database Schema

The project uses **three core tables** — `Books`, `Customers`, and `Orders` — connected through primary and foreign key relationships.

### 📘 Tables Overview

| Table | Description |
|--------|-------------|
| **Books** | Stores details of each book (title, author, genre, price, stock, etc.) |
| **Customers** | Contains customer information such as name, contact, and location |
| **Orders** | Tracks purchase transactions linking customers and books |

---

## 🧩 Entity Relationship Diagram (ERD)

> 📌 *You can include your ERD screenshot here.*

Example placeholder:

+------------+ +-------------+ +-----------+
| Customers | <----> | Orders | <----> | Books |
+------------+ +-------------+ +-----------+

---

## ⚙️ Setup Instructions

### Step 1: Create Database and Tables
```sql
CREATE DATABASE OnlineBookstore;
USE OnlineBookstore;
-- Run all CREATE TABLE statements from online_bookstore.sql

SET GLOBAL local_infile = 1;

LOAD DATA LOCAL INFILE 'path/to/Books.csv'
INTO TABLE Books
FIELDS TERMINATED BY ','
ENCLOSED BY '"'
LINES TERMINATED BY '\n'
IGNORE 1 ROWS
(Book_ID, Title, Author, Genre, Published_Year, Price, Stock);

🧮 SQL Queries Overview
🔹 Basic Queries
| # | Query                                               | Description                  |
| - | --------------------------------------------------- | ---------------------------- |
| 1 | `SELECT * FROM Books WHERE Genre = 'Fiction';`      | Retrieve all Fiction books   |
| 2 | `SELECT * FROM Customers WHERE Country = 'Canada';` | List customers from Canada   |
| 3 | `SELECT SUM(Stock) AS Total_Stock FROM Books;`      | Calculate total stock        |
| 4 | `SELECT * FROM Books ORDER BY Price DESC LIMIT 1;`  | Find the most expensive book |

🔹 Advanced Queries
| # | Query                                                                                           | Description                  |
| - | ----------------------------------------------------------------------------------------------- | ---------------------------- |
| 1 | `SELECT Genre, SUM(Quantity) FROM Orders JOIN Books GROUP BY Genre;`                            | Total books sold per genre   |
| 2 | `SELECT c.Name, SUM(o.Total_Amount) FROM Customers c JOIN Orders o ...;`                        | Top-spending customer        |
| 3 | `SELECT b.Title, (b.Stock - SUM(o.Quantity)) AS Remaining FROM Books b LEFT JOIN Orders o ...;` | Remaining stock after orders |

🧰 Tech Stack

| Tool                        | Purpose                                             |
| --------------------------- | --------------------------------------------------- |
| **MySQL / MySQL Workbench** | Database management and query execution             |
| **CSV Files**               | Data import source for Books, Customers, and Orders |
| **SQL**                     | Used for schema creation, joins, and data analysis  |
| **Git & GitHub**            | Version control and project hosting                 |


📊 Sample Output

Example 1 – Total Books Sold by Genre

| Genre   | Total_Books_Sold |
| ------- | ---------------- |
| Fiction | 120              |
| Fantasy | 85               |
| Mystery | 64               |

Example 2 – Top Spending Customer

| Customer_ID | Name       | Total_Spent |
| ----------- | ---------- | ----------- |
| 104         | John Smith | 185.50      |

Example 3 – Remaining Stock

| Book_ID | Title          | Stock | Ordered | Remaining |
| ------- | -------------- | ----- | ------- | --------- |
| 1       | The Silent Sea | 25    | 10      | 15        |


---


