# 🛒 Super Store Sales – MySQL Project

## 📌 Project Overview
This project is built around a **Super Store Sales** dataset stored in MySQL.  
It demonstrates how to design relational tables, insert real-world style data, and run queries to extract valuable insights such as **customer behavior, sales performance, and satisfaction analysis**.

---

## 🗄️ Database & Table Creation
The SQL script creates a database named **`super_store_sales`** with the following schema:

- **Transactions**  
  - Stores purchase data: `Customer_ID`, `Product_Name`, `Unit_Price`, `Units_Sold`, `Discount_Applied`, `Total_Revenue`, `Date`, and `Payment_Method`.  
  - Acts as the core sales record table.  

- **Customer_Details**  
  - Contains customer demographics: `Customer_ID`, `Store_Location`, `Email_Address`, `Phone_Number`, `Membership_Tier`.  
  - Includes **unique constraints** on `Email_Address` and `Phone_Number`.  
  - Linked to `Transactions` via `Customer_ID` (foreign key).  

- **Customer_Support**  
  - Stores customer interactions: `Customer_ID`, `Email_Address`, `Feedback_Type`, and `Satisfaction_Rating`.  
  - Useful for analyzing **customer experience vs purchase behavior**.  

---

## 🔍 Queries & Insights

### 1. Show Customer, Product, Email & Tier (Join)
**Query Goal**: Joins `transactions` with `customer_details` to show `Customer_ID`, `Product_Name`, `Email_Address`, and `Membership_Tier` for each purchase.  
**Insight**: Baseline view linking sales with customer contact and loyalty tier.

![Query 1 Result](images/query1.jpeg)

---

### 2. Top 10 Customers by Revenue (with Contact Info)
**Query Goal**: Joins `transactions` and `customer_details`, orders by `Total_Revenue` (descending), and returns the **top 10** customers with their `Email_Address` and `Phone_Number`.  
**Insight**: Quickly identifies highest-revenue customers and how to reach them.

![Query 2 Result](images/query2.jpeg)

---

### 3. Customers with Revenue > 2000 (with Contact Info)
**Query Goal**: Returns customers whose `Total_Revenue` is **greater than 2000**, along with their `Email_Address` and `Phone_Number`.  
**Insight**: Segments high-value customers for retention and VIP programs.

![Query 3 Result](images/query3.jpeg)

---

### 4. New York Customers & Their Purchases
**Query Goal**: Filters for `Store_Location = "New York"` and shows `Customer_ID` and `Product_Name` for their purchases.  
**Insight**: Location-based view of purchasing behavior in New York.

![Query 4 Result](images/query4.jpeg)

---

### 5. Customers Who Bought > 5 Units
**Query Goal**: Lists `Customer_ID`, `Product_Name`, `Units_Sold`, and `Email_Address` where `Units_Sold > 5`.  
**Insight**: Identifies bulk purchasers for volume discounts or targeted offers.

![Query 5 Result](images/query5.jpeg)

---

### 6. Customers Who Gave Feedback (3-Table Join)
**Query Goal**: Joins `transactions`, `customer_details`, and `customer_support` to list `Customer_ID`, `Product_Name`, `Email_Address`, and `Feedback_Type` for customers who have feedback records.  
**Insight**: Shows post-purchase engagement and feedback context.

![Query 6 Result](images/query6.jpeg)

---

### 7. Top 5 by Revenue + Tier + Satisfaction
**Query Goal**: Ranks by `Total_Revenue` (descending) and returns the **top 5** customers with `Membership_Tier` and `SatisfactionRating` from support.  
**Insight**: Cross-checks spend vs satisfaction among your most valuable customers.

![Query 7 Result](images/query7.jpeg)

---

### 8. Electronics Buyers + Contact + Feedback Status
**Query Goal**: Filters purchases where `Product_Category = "Electronics"` and returns customer contact (`Email_Address`, `Phone_Number`), `Feedback_Type`, and `Resolution_Status`.  
**Insight**: Monitors after-sales service signals for Electronics customers.

![Query 8 Result](images/query8.jpeg)

---

### 9. Above-Average Revenue Customers (with Contact)
**Query Goal**: Uses a subquery to compare each customer’s `Total_Revenue` against the **average** across all transactions; returns those above average with `Email_Address` and `Phone_Number`.  
**Insight**: Finds high performers relative to overall store performance.

![Query 9 Result](images/query9.jpeg)

---

### 10. Feedback Givers Below the Max Revenue
**Query Goal**: Among customers who have feedback (via join with support), returns those with `Total_Revenue` **less than** the **maximum** recorded revenue.  
**Insight**: Contrasts mid/upper-mid spenders’ feedback patterns with top spenders.

![Query 10 Result](images/query10.jpeg)

## 📊 Potential Dashboards
Using the exported query results, dashboards can be created in **Excel, Power BI, or Tableau** for:
- Revenue trends by product category  
- Membership tier distribution  
- Feedback analysis linked to sales data  

## 🚀 How to Use
1. Import the SQL file into MySQL:
   ```sql
   SOURCE Super_Store_Sales.sql;
Run the included queries to explore insights.

Add query result screenshots in the images/ directory.

📂 Repository Structure
graphql
Copy code
├── Super_Store_Sales.sql       # SQL dump with schema, data, and queries
├── README.md                   # Project documentation
└── images/                     # Folder for query results & dashboard screenshots
For collaboration, feedback or suggestions email me at shahidabbas2104514@gmail.com
pgsql
Copy code
