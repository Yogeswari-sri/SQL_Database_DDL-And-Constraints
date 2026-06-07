# SQL_Database_DDL And Constraints
 A collection of SQL scripts demonstrating table creation, constraints, and relational design.
# 🗄️ SQL Database DDL & Constraints

This repository demonstrates **MySQL DDL commands and constraints** as part of a structured database design assignment.  
It covers database creation, table management, and enforcement of integrity rules through constraints.

---

## 📌 DDL Commands Implemented
- **CREATE**: Database and tables with appropriate data types and relationships  
- **ALTER**:  
  - Add new column (`email`) to Employees  
  - Modify data type of `designation`  
  - Drop `age` column  
  - Rename `hire_date` → `date_of_joining`  
- **RENAME**:  
  - `Departments` → `Departments_Info`  
  - `Location` → `Locations`  
- **TRUNCATE**: Clear all records from Employees table  
- **DROP**: Remove Employees table and database  

---

## 📌 Constraints Applied
- **Departments Table**  
  - `department_id` as unique identifier (Primary Key)  
  - `department_name` with NOT NULL and UNIQUE constraints  

- **Locations Table**  
  - Auto‑incremented unique identifiers for each location  
  - Prevent null and duplicate entries  

- **Employees Table**  
  - `employee_id` as distinct identifier (Primary Key)  
  - `name` must always be provided (NOT NULL)  
  - `gender` restricted to values `'M'` or `'F'` (CHECK)  
  - `age` must be ≥ 18 (CHECK)  
  - `date_of_joining` defaults to current date if not specified  
  - Foreign Keys:  
    - `department_id` → Departments_Info  
    - `location_id` → Locations
   
OUTPUT
<img width="1591" height="781" alt="image" src="https://github.com/user-attachments/assets/4220f06a-93c5-4287-9e18-c3bca0bc06fc" />
 
RELATIONSHIP OUTPUT

---<img width="1600" height="768" alt="image" src="https://github.com/user-attachments/assets/44fd6574-65a9-46b8-a1d8-312b80c51c2c" />


## 📂 Example Script

```sql
CREATE TABLE Employees (
    employee_id INT PRIMARY KEY,
    name VARCHAR(100) NOT NULL,
    gender CHAR(1) CHECK (gender IN ('M','F')),
    age INT CHECK (age >= 18),
    designation VARCHAR(100),
    email VARCHAR(100),
    department_id INT,
    location_id INT,
    date_of_joining DATE DEFAULT CURRENT_DATE,
    FOREIGN KEY (department_id) REFERENCES Departments_Info(department_id),
    FOREIGN KEY (location_id) REFERENCES Locations(location_id)
);

OUTPUT SCREEN
<img width="1591" height="811" alt="image" src="https://github.com/user-attachments/assets/ee084412-863f-4669-b7b1-a2429d3de4ce" />

RELATIONSHIP DIAGRAM
<img width="1600" height="768" alt="image" src="https://github.com/user-attachments/assets/825758a9-c4cf-4c9b-a950-6e2642b262fa" />










