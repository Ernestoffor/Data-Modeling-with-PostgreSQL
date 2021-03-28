# Data Modeling in PostgreSQL
This project centers on building an ETL (Extract, Transform and Load) data pipeline in PostgreSQL RDBM.
The aim of the project is to simplify quering of data collected by a music streaming company in their app directory  JSON logs and another JSON directory containing some metadata. 
The project develops a star schema consisting of a fact table and four dimensional tables.
The fact table is called songplays while songs, users, artists and time  tables are the dimensional tables. 
The fact table is called songplays table while songs, users, artists and time  tables are the dimensional tables. The star schema is shown in the figure below. 
![alt text](table.png "Star Schema")

![Star Schema](table.png)


## Project Steps
1. The tables are created in a file called sql_queries.py using SQL CREATE statements. DROP statements precedes the CREATE statements to drop the tables if they already exist. DROP statements become particularly useful when the code is to be rerun in which case the tables already exist.

1. A test file "test.ipynb" is created and run to confirm the correctness of table creations with the right columns.

1. ETL processes are developed in the etl.ipynb file to extract and tranform some data from the given directories and load them into the tables created in step 1. test.ipynb is again used to check the correctness of the ETL operations. Thereafter, create_tables.py is developed to be run after each run of sql_queries.py followed by etl.ipynb followed and then test.ipynb.

1. Finally, etl.py file is where ETL pipeline processing is carried out on the entire datasets. The file includes four functions, namely:
    * process_song_file: This accepts two inputs, cursor and filepath to extract songs and artists tables from the song_data folder.
    * process_log_file: It also uses two arguments, cursor and filepath to extract  data for users, time and songplays tables from the log_data directory.
    * process_data function: This function accepts four inputs, namely: cursor, connection to the database, filepath and another function. It performs insertion operations to populate the tables.
    * main function: This defines all the argument/inputs variables and does the actual work of extraction, transformation and loading of the data.

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



