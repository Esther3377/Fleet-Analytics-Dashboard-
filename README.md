Fleet Analytics Dashboard | SQL & Power BI
Project Overview
This project analyses fleet operations using 14 related datasets covering 120 trucks, 150 drivers, 85,410 loads, and 170 reported safety incidents.
The objective is to investigate operational efficiency, delivery reliability, financial performance, maintenance, and safety risks using SQL analysis and an interactive Power BtI dashboard.


Dashboard Preview
The dashboard contains four analytical sections:
1.	Financial Overview — fleet financial indicators and potential loss exposure.







2.	Fleet Operations & Maintenance — operational efficiency and maintenance performance.












3.	Driver & Delivery Performance — delivery reliability and driver-related indicators.



4.	
Safety & Risk — incident patterns and safety-claim indicators.



Tools and Techniques
•	SQL using the project's SQLite database
•	Microsoft Power BI
•	DAX measures
•	Data relationships and modelling
•	KPI analysis and data visualisation
Key Findings
•	Reported on-time delivery rate: 44.6%.
•	Loads associated with the reported loss estimate: 11,664.
•	Reported potential loss exposure: $8.7 million.
•	Safety analysis covering 170 reported incidents.
These figures are based on the project analysis. The loss figure represents an estimate and should not be interpreted as independently verified financial loss.


SQL Analysis
The SQL work supports querying, joining, filtering, aggregating, and cross-checking operational data.
The repository should include the actual SQL queries, with comments explaining the business question addressed by each query and the resulting insight.
Business Value
The analysis highlights areas for further investigation in delivery reliability, operational efficiency, financial exposure, and fleet safety. These insights can support evidence-based operational reviews and help management prioritise improvement opportunities.
Project Files
•	SQL queries: 
•	SELECT truck_id,status
•	FROM Trucks
•	WHERE status = 'Active'
•	
•	SELECT driver_id,first_name,last_name,hire_date,date_of_birth,home_terminal,employment_status,years_experience
•	FROM Drivers
•	
•	SELECT COUNT(driver_id) as 'Total driver ID'
•	FROM Drivers
•	
•	SELECT load_id,customer_id,route_id,load_type,revenue,fuel_surcharge,accessorial_charges,load_status,booking_type
•	FROM loads
•	
•	SELECT AVG(revenue) as 'Avg Revenue'
•	FROM loads
•	
•	SELECT*
•	FROM Customers
•	
•	SELECT customer_type,account_status
•	FROM Customers
•	WHERE customer_type = 'Dedicated'
•	
•	SELECT customer_type,account_status
•	FROM Customers
•	WHERE customer_type = 'Contract'
•	
•	SELECT customer_type,account_status
•	FROM Customers
•	WHERE customer_type = 'spot'
•	
•	SELECT Top 10 load_id
•	FROM loads
•	ORDER BY (load_date) DESC
•	
•	SELECT incident_id,trip_id,truck_id,driver_id,incident_type,location_city,claim_amount,preventable_flag
•	FROM [Safety incidents]
•	
•	SELECT COUNT (preventable_flag)
•	FROM [Safety incidents]
•	WHERE preventable_flag = '1'
•	
•	SELECT SUM (claim_amount) as 'Total Claim'
•	FROM [Safety incidents]
•	
•	SELECT maintenance_id,truck_id,maintenance_type,total_cost,facility_location,downtime_hours
•	FROM [Maintenance records]
•	
•	SELECT AVG (downtime_hours)
•	FROM [Maintenance records]
•	
•	SELECT driver_id
•	FROM Drivers
•	WHERE years_experience >10
•	
•	SELECT COUNT (load_type)
•	FROM loads
•	
•	SELECT SUM (revenue+fuel_surcharge+accessorial_charges) as 'Total Revenue'
•	FROM loads
•	
•	SELECT event_id,load_id,trip_id,event_type,facility_id,actual_datetime,detention_minutes,on_time_flag,location_city
•	FROM [Delivery events]
•	WHERE event_type = 'Delivery'
•	
•	SELECT event_id,load_id,trip_id,event_type,facility_id,actual_datetime,detention_minutes,on_time_flag,location_city
•	FROM [Delivery events]
•	WHERE event_type = 'Pickup'
•	
•	SELECT AVG (CAST(on_time_flag AS decimal(5,2)))*100 as 'OnTime Delivery %'
•	FROM [Delivery events]
•	
•	SELECT Top 10 driver_id,claim_amount
•	FROM [Safety incidents]
•	ORDER BY 'claim_amount' DESC
•	
•	SELECT SUM (claim_amount)
•	FROM [Safety incidents]
•	
Author
Esther Ndibueze
Data Analyst | SQL & MySQL | Power BI | Microsoft Excel
GitHub | LinkedIn






