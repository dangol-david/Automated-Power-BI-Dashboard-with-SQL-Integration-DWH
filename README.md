# Automating Power BI Dashboard with SQL

This project demonstrates how to **fully automate a Power BI dashboard using SQL**, a process beneficial for **data scientists** or **data analysts**.  
The core idea is to automate the raw data input from **Excel into SQL**, schedule this process, and then connect SQL with Power BI to create a dashboard that **automatically updates whenever new data is added** to the Excel file.

---

## 📌 Steps Covered in the Video

### 1. Setting up SQL Server
- Open **SQL Server Management Studio (SSMS)** and connect to a database.

### 2. Creating the SQL Table & Importing Data
- Create an empty SQL table (`raw_data_GDP`) to receive raw data from an Excel CSV file, defining column names and data types.
- Import data into this table using a **bulk insert command**.  
  ⚠️ Note: Remove column names from the CSV and close the file before importing.

### 3. Creating a SQL View
- Create a SQL view (`GDP_Excel_input`) to select and join specific data from the raw table.  
- This ensures only the **necessary data** is sent to Power BI.

### 4. Automating Data Flow with Stored Procedures & Jobs
- **Stored Procedure**:  
  Encapsulates steps to:
  - Drop the existing raw data table (if it exists).
  - Bulk insert the latest data from the Excel file.
- **SQL Server Agent Setup**:  
  - Ensure SQL Server Agent is running.  
  - Enable TCP/IP for the server.  
  - Set the server’s start mode to **automatic** for reliable execution.
- **Job Scheduling**:  
  - Create a job (`job_test_one`) in SQL Server Agent.  
  - Schedule it (e.g., every Monday at 7 a.m.) to run the stored procedure automatically.

### 5. Connecting to Power BI & Building the Dashboard
- Connect Power BI to the SQL view (`GDP_Excel_input`) using **Get Data → SQL Server**.  
- Adjust data types as needed (e.g., change `year` from text to whole number).
- Build an interactive dashboard:
  - Add a title, image, and separator line.
  - Create slicers for **Country** (with search) and **Year**.
  - Add visuals:
    - **Line Graph** → Year vs. GDP Value
    - **Map Visual** → Country and GDP Value
    - **Table** → Country, GDP Value, GDP per Capita (with conditional formatting).

### 6. Testing the Automation
- Modify raw Excel data (e.g., delete data after a certain year).  
- Manually execute the stored procedure in SQL.  
- Refresh Power BI → Dashboard updates with new data.  
- Restore original Excel data, rerun the procedure, and refresh → Dashboard updates again with the full dataset.  

✅ The process works **seamlessly and updates within seconds**.

---

## 🚀 Key Benefits
- **End-to-End Automation**: No manual imports or refreshes needed.  
- **Scalable**: Works with any structured Excel-to-SQL workflow.  
- **Time-Saving**: Dashboard stays up-to-date with minimal effort.  

---

## 🛠️ Tech Stack
- **SQL Server** (SSMS, SQL Server Agent)  
- **Power BI**  
- **Excel (CSV)**  

---
