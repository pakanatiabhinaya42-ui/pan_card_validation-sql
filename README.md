# PAN Card Validation Project (PostgreSQL + SQL)

## 📌 Overview
This project demonstrates how to *clean, validate, and analyze PAN card numbers* using SQL and PostgreSQL.  
It ensures the PAN numbers follow the correct format, removes duplicates, and categorizes records into *Valid PAN* and *Invalid PAN* using regex and PL/pgSQL functions.

---

## 📂 Dataset
- File: pan_dataset.csv  
- Contains *10,000 PAN card records* (dummy data for validation).  
- Used to test data cleaning and validation queries.

---

## 🛠 Tech Stack
- *PostgreSQL 17*
- *SQL* (DDL, DML, CTEs, Views)
- *Regex* (for PAN pattern validation)
- *PL/pgSQL functions*

---

## 🚀 Features
1. *Data Cleaning*
   - Trim leading/trailing spaces  
   - Convert PAN numbers to uppercase  
   - Remove duplicates  

2. *Validation*
   - Regex check for PAN format: ^[A-Z]{5}[0-9]{4}[A-Z]{1}$  
   - Function to check *adjacent characters*  
   - Function to check *sequential characters*  

3. *Categorization*
   - Create a view to separate *Valid PANs* and *Invalid PANs*  
   - Summary report with total records, valid, invalid, and missing PANs  

---

## ⚡ How to Run
1. Import the dataset:
   sql
   CREATE TABLE stg_pan_numbers_dataset (
       pan_number TEXT
   );
   

   sql
   COPY stg_pan_numbers_dataset(pan_number)
   FROM '/path/to/pan_dataset.csv'
   DELIMITER ','
   CSV HEADER;
   

2. Run the SQL script:
   sql
   \i pan_card_project.sql
   

3. Query results:
   sql
   SELECT * FROM vw_valid_invalid_pans;
   

---

## 📊 Sample Output
| Total Processed Records | Total Valid PANs | Total Invalid PANs | Missing PANs |
|--------------------------|------------------|--------------------|--------------|
| 10000                   | 8420             | 1450               | 130          |

---

## 📂 Project Structure

pan-card-validation-sql/
│
├── pan_card_project.sql     # SQL queries and functions
├── pan_dataset.csv          # Dataset with 10,000 PAN numbers
└── README.md                # Project documentation


---

## 🔮 Future Enhancements
- Build a *Power BI / Tableau dashboard* on valid vs invalid PANs  
- Create a *Python pipeline* to automate data loading & validation  
- Deploy validation as an *API service*

---

## 👩‍💻 Author
*Pakanati Abhinaya*  
- [LinkedIn](https://www.linkedin.com/in/abhinaya-pakanati-29724a2ab/)  
