Stefan Reesberg
DV.2021.W6H4J8
Database Management Project 2 – Tygervalley Pet Shelter
User Documentation

Project Specification
Create an ER diagram of the Tygervalley Pet Shelter Scenario.
Create a database.
Create tables for the database while using proper constraints.
Insert sample data into the created tables.
Create the following views:
•	vw_ManufacturerDetails - Select manufacturing company details, the food type, food ID and amount per category.
•	vw_PetsPerType - Select each animal type, total animals in stock, the animal category ID and category name.
•	w_ExpiredFoodDetails - Select the company name, contact number, food ID, name, expiry date, amount per category, measurement and the category name. This only applies to expired products that are in use (have dependent records).
•	vw_LowestFoods - Select the category name and the sum of the total animals in the category. Only the three records with the lowest pets must be selected.
Create the following stored procedures: 
•	sp_NewPetType - Insert a new pet type record. Remember to check whether the foreign key argument is an existing category primary key. 
•	sp_UpdateStock - Update an existing pet type record. The procedure must make use of three arguments – 1: pet type primary key, 2: the number of animals that must be added/subtracted, 3: bit number representing addition (1) or subtraction (0).
•	sp_DeleteFoodType - Delete a specified food type and all dependent/child records. However, only delete the type if it is contained in the vw_ExpiredFoodDetails view. 
•	sp_Report - Print a specified manufacturing company’s details and all its expired products in use. The report should also display a header as well as the current date and time. Retrieve the products by using the vw_ExpiredFoodDetails view. The report should be displayed as follows:
Create two after triggers on the tables you have created.
Create indexes on the tables you have created.
Create a zipped backup of your database and hand it in with your script files.


Program Design
My program has been designed to address the above specifications in segments of script files that are opened by Microsoft SQL Server Management Studio 2019. The list is as follows:
1.	Creation_Database_Tables.sql – this script file creates the database and tables of Tygervalley Pet Shelter.
2.	Sample_Data_Insert.sql – this script file inserts sample data to populate the tables of the database for other functions to be demonstrated and used.
3.	View_Creation.sql – this script file creates the 4 requested views stipulated in the project specifications.
4.	Stored_Procedure_Insert.sql – this script file creates a stored procedure that inserts a new record into the specified table.
5.	Stored_Procedure_Update.sql – this script file updates an existing record of a specified table.
6.	Stored_Procedure_Report.sql – this script file generates a report on a manufacturer and displays any expired food types that are present.
7.	Creation_Triggers.sql – this script file creates 2 after triggers (1. When a new record is inserted, 2. When an existing record is updated.) for each table.
8.	Creation_Indexes.sql – this script file creates indexes for each table that has been created.
NB! These should be executed in sequence according to their numbers.
Finally, a backup of the database will be created and zipped with the script files, ERD and this document.
Project Source Code
The source code for my project can be found in each of the script files provided in the zipped file.
Databases
My project only consists of one database: TygervalleyPetShelter.dbo
Error Handling
Throughout my project, in each script file there are validation checks for important information being input into the program. IF EXISTS is used to validate whether a specified record exists, IDENTITY is used to create auto-incremented primary keys and UNIQUE is used to make sure a given entry is completely unique.
Furthermore, many of the script files have checks against negative numbers, checks for expiry dates and included with each script file are examples of faulty inputs that test the validation provided.

