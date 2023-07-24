# SQL_DATA_Engineer_Exercise

Achievement First Data Engineer Exercise
This repository contains the solution for the Achievement First Data Engineer Exercise. The exercise involves working with various CSV files sourced from the Student Information System, Infinite Campus. The goal is to perform data analysis, SQL queries, and Python operations to update and manipulate the provided data.

## Project Structure
The project is organized into two main parts:

SQL: This section focuses on loading the CSV data into a SQLite database named 'ic' and performing SQL-related tasks. It includes:

 - create_database.py: A script to create the SQLite database and load the CSV data.
execute_sql.py: A Python script defining functions to execute SQL queries on the 'ic' database.
update_schoolyear.py: A Python script to update the 'schoolyear' table with the active school year set to 2020.
sql_queries.md: A markdown file containing the SQL queries used to answer specific questions.
Python: In this section, we use Python and pandas DataFrames to add and manipulate data. It includes:

 - add_city_to_school.py: A Python script to add the 'city' column to the 'school' DataFrame using an API link.
add_final_enddate_to_enrollment.py: A Python script to add the 'final_enddate' column to the 'enrollment' DataFrame based on 'enddate' and 'calendar' data.
export_active_enrollment.py: A Python script to merge the 'enrollment' and 'school' DataFrames using complex joins and export the resulting DataFrame to a CSV file with additional columns.
Instructions

## To execute the scripts and reproduce the analysis:

Clone this repository to your local machine:

 - git clone https://github.com/your-username/achievement-first-data-engineer.git

Make sure you have the required Python libraries installed. You can install them using the following command:

 - pip install pandas requests sqlite3 concurrent

Execute the scripts in the 'SQL' and 'Python' sections as needed.

###  The resulting CSV file containing the active enrollment data will be generated in the root directory with the name 'active_enrollment.csv'.


## Struggles and Solutions
During the implementation of the Python section, I encountered a performance issue when merging the 'enrollment' and 'school' DataFrames. The merge operation took a considerable amount of time, and I suspected it was due to the size of the DataFrames.

To address this issue, I researched and discovered that multi-threading could potentially speed up the merging process. I decided to use the concurrent.futures.ThreadPoolExecutor to execute the merge concurrently for improved performance.

I modified the code in the 'export_active_enrollment.py' script to utilize multi-threading during the merging process. By doing so, I observed a significant reduction in the execution time, making the operation more efficient and scalable.

## What I Learned

Through this exercise, I gained valuable experience in the following areas:

 - Data Analysis: I learned how to work with CSV data and perform data manipulation and analysis using pandas DataFrames in Python.

 - SQL Queries: I gained proficiency in writing SQL queries to retrieve, update, and manipulate data stored in a SQLite database.

 - Multi-Threading: I learned how to use the concurrent.futures.ThreadPoolExecutor to perform concurrent and parallel processing, which significantly improved the performance of certain operations.

 - API Integration: I acquired knowledge of how to make HTTP requests to external APIs and extract relevant data to enrich existing datasets.

 - Complex Joins: I practiced performing complex joins between DataFrames, enabling me to merge data from different sources based on specified relationships.

Overall, this exercise provided me with a comprehensive understanding of data engineering concepts, including data integration, data manipulation, and database management. It also equipped me with valuable tools and techniques to efficiently handle and process large datasets.

## Initital Schema

<img width="998" alt="Screenshot 2023-07-23 at 9 06 23 PM" src="https://github.com/yannellym/SQL_DATA_Engineer_Exercise/assets/91508647/24cc7eef-6375-426e-b491-76bda0e261cd">

##  Results produced:

![Screenshot 2023-07-24 at 7 20 13 PM](https://github.com/yannellym/SQL_DATA_Engineer_Exercise/assets/91508647/92eed3e4-791f-4aea-ac1d-14ef7c5e9e66)

## Additional Information

The 'ic' SQLite database file is created when running the 'create_database.py' script. It stores the data from the provided CSV files.

For SQL-related tasks, we used SQLite to perform database operations. The 'execute_sql.py' script provides functions to execute SQL queries and save changes to the 'ic' database.

For Python-related tasks, pandas DataFrames are used to manipulate and analyze the data. API calls are made to fetch city information for the schools' zip codes, and 'final_enddate' is calculated based on available data.

The results of the SQL queries and the exported CSV file can be found in the respective sections of this README.

Feel free to reach out to me at yannellym@gmail.com if you have any questions or need further assistance.

