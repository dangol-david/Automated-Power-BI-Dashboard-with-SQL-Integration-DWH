# Automated Power BI Dashboard with SQL Integration

## Project Overview

This project demonstrates a fully automated workflow for creating and maintaining a Power BI dashboard using SQL Server as the backend data processor. The core objective is to streamline data ingestion from Excel files into SQL, schedule automated updates, and seamlessly connect to Power BI for real-time dashboard refreshes. This automation is particularly beneficial for data scientists, analysts, and business intelligence professionals who need to handle dynamic datasets without manual intervention.

The project automates the process of importing raw GDP data from an Excel CSV file into SQL Server, transforming it via views, and visualizing it in Power BI. By leveraging SQL stored procedures and scheduled jobs, the dashboard updates automatically whenever new data is added to the source Excel file. This eliminates repetitive manual tasks, reduces errors, and ensures data freshness.

### Key Features
- Automated Data Ingestion: Bulk import from Excel CSV to SQL table.
- Data Transformation: SQL views for cleaned and joined data.
- Scheduling: SQL Server Agent jobs for periodic updates.
- Visualization: Interactive Power BI dashboard with slicers, charts, maps, and tables.
- Testing Mechanism: Easy validation of automation through data modifications and refreshes.

### Technologies Used
- SQL Server Management Studio (SSMS)
- Power BI Desktop
- Excel (for raw data source)
- No additional programming languages required beyond SQL queries.

### Prerequisites
- SQL Server installed and running.
- SQL Server Agent enabled.
- Power BI Desktop installed.
- Access to an Excel file with raw data (e.g., GDP data in CSV format).

## Setup Instructions

1. Install and Configure SQL Server:
   - Download and install SQL Server and SSMS if not already available.
   - Open SSMS and connect to your database server (e.g., local instance).
   - Ensure TCP/IP is enabled in SQL Server Configuration Manager.
   - Set the SQL Server service start mode to "Automatic" for reliable job execution.

2. Prepare Raw Data:
   - Use an Excel file containing raw data (e.g., GDP metrics with columns like Demo_IND, Indicator, Location, Country, Time, Value, Flag Codes, Flags).
   - Export or save as CSV, ensuring no header row if using bulk insert.
   - Close the Excel/CSV file before importing to avoid file locks.

## Step-by-Step Process

The workflow is divided into clear stages, from data setup to dashboard creation and automation testing.

### 4. Automating Data Flow with Stored Procedures and Jobs
A stored procedure is created to encapsulate the steps of dropping the existing raw data table (if it exists) and bulk inserting the latest data from the Excel file. This procedure is designed to be created once and then scheduled.

SQL Server Agent is configured by ensuring it is running, TCP/IP is enabled for the server, and the server's start mode is set to "automatic" to guarantee scheduled jobs execute reliably.
A SQL Server Agent job (job_test_one) is created and scheduled (e.g., weekly on Monday at 7 a.m.) to execute the stored procedure, thereby automating the data update process.

### 5. Connecting to Power BI and Building the Dashboard
Power BI is connected to the SQL view (GDP_Excel_input) by selecting "Get Data," choosing SQL Server, and entering the server and database names.
Once loaded, the data types in Power BI are inspected and adjusted (e.g., changing 'year' from text to a whole number).
The video then guides through building an interactive Power BI dashboard, including adding a title, an image, and a horizontal line.
Slicers are created for country (with search functionality) and year, with formatting for background, border, and titles applied.
Visualizations are added: A line graph showing year vs. GDP value, a map visual displaying country and GDP value, and a simple table with country, GDP value, and GDP per capita, including conditional formatting for GDP per capita.

### 6. Testing the Automation
The automation is tested by modifying the raw Excel data (deleting data after a certain year), manually executing the stored procedure in SQL, and then refreshing the Power BI dashboard to observe that the dashboard updates to reflect the changes. The process is repeated by restoring the original Excel data, running the procedure, and refreshing Power BI again to confirm it updates with the full dataset, demonstrating that the automation works perfectly within seconds.

## Usage
Update the Excel CSV file with new data.
The scheduled job will automatically import and update the SQL view.
Open Power BI and refresh to see live updates in the dashboard.

## Contributing
Feel free to fork this repository, suggest improvements, or submit pull requests. For issues, open a GitHub issue with details.

## License
This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Acknowledgments
Inspired by educational videos on automating BI workflows. Special thanks to the data analysis community for sharing best practices.
