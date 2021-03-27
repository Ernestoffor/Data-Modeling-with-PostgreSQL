# Data Modeling in PostgreSQL
This project centers on building an ETL (Extract, Transform and Load) data pipeline in PostgreSQL RDBM.
The aim of the project is to simplify quering of data collected by a music streaming company in their app directory  JSON logs and another JSON directory containing some metadata. 
The project develops a star schema consisting of a fact table and four dimensional tables.
The fact table is called songplays while songs, users, artists and time  tables are the dimensional tables. 
The fact table is called songplays table while songs, users, artists and time  tables are the dimensional tables. The star schema is shown in the figure below.

![Star Schema](table.png)


## Project Steps
1. The tables are created in a file called sql_queries.py using SQL CREATE statements. DROP statements precedes the CREATE statements to drop the tables if they already exist. DROP statements become particularly useful when the code is to be rerun in which case the tables already exist.

1. A test file "test.ipynb" is created and run to confirm the correctness of table creations with the right columns.

1. ETL processes are developed in the etl.ipynb file to extract and tranform some data from the the given directories and load them into the tables created in step 1. test.ipynb is again used to check the correctness of the ETL operations. Thereafter, create_tables.py is developed to be run after each run of etl.ipynb followed by test.ipynb to reset the tables.

1. Finally, etl.py file is where ETL pipeline processing is carried out on the entire datasets. 

## The order and methods of running the files are as follows:
   
1.  python3 sql_queries.py
1.  python3 create_tables.py
1.  python3 etl.py or run the etl.ipynb
1.  Run test.ipynb in Ipython
                            

## Credits
This project is a partial requirement for the completion of Udacity Data Engineering Nanodegree program. Hence, it is designed to meet Udacity project rubrics. 

## Software Packages
* Python2 or Python3
* PostgreSQL
* psycopg2 (a python driver for postgresql)



