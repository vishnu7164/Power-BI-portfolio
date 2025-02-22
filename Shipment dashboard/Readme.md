## Data Cleaning
Data cleaning tasks using Power Query: 
•	After importing it was noticed that column headers for Country, SalesPerson tables are not added as headers so used PowerQuery to promote the respective rows to header
•	Some empty rows are present in Sales person file they are removed 
•	To ensure data is standardized all columns are verified for correct datatype. While checking noticed date columns ‘Delivered on’, ‘Date’ columns are not assigned date type so they are changed

## Calendar table
For the purpose of calculating time-based measures Calendar table is created for reference. Used DAX measure to create Calendar table.

DAX expression used:
Calendar = 
            var start_date = MIN(Shipment[Date])
            var end_date = MAX(Shipment[Date])
RETURN

            ADDCOLUMNS(CALENDAR(start_date,end_date),
            "Year", YEAR([Date]),
            "Month", MONTH([Date]),
            "Quarter", "Q " & QUARTER([Date]),
            "Weekday", WEEKDAY([Date],2),
            
            "Month name", FORMAT([Date], "mmmm"),
            "Weekday name", FORMAT([Date], "dddd"),
            "week num", WEEKNUM([Date])

## Creating connection using model view
After creating all the tables needed and standardising information connections are established between tables

## Measures
A measures table is created in order to keep all measures created in a single location which will be easy for debugging incase of error and improved the readability of data model

### Base measures are created initially in order to simplify creating further measures
1.	Total shipments
2.	Revenue
3.	Delivery time
Among all measures created calculation Delivery time is bit challenging as it contain blank cells in the column where some orders with status ‘Active’ are not yet delivered. 
While handling blank value I used containstring() method to identify the blank value and replace it with zero for time being as it is indefinite as date is not mentioned in the dataset

### Measures built using base measures
1.	Active shipments
2.	Completed shipments
3.	Return Shipments
4.	Active Shipments %
5.	Completed shipments %
6.	Return Shipments %
7.	Returned Shipments cost
