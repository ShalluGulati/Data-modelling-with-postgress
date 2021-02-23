# Introduction

A startup called Sparkify wants to analyze the data they've been collecting on songs and user activity on their new music streaming app. The analytics team is particularly interested in understanding what songs users are listening to. Currently, they don't have an easy way to query their data, which resides in a directory of JSON logs on user activity on the app, as well as a directory with JSON metadata on the songs in their app.

They'd like a data engineer to create a Postgres database with tables designed to optimize queries on song play analysis, and bring you on the project. Your role is to create a database schema and ETL pipeline for this analysis. You'll be able to test your database and ETL pipeline by running queries given to you by the analytics team from Sparkify and compare your results with their expected results

## Project Description

In this project, I'll apply what I've learned on data modeling with Postgres and build an ETL pipeline using Python. To complete the project, I have defined fact and dimension tables for a star schema for a particular analytic focus, and wrote an ETL pipeline that transfers data from files in two local directories into these tables in Postgres using Python and SQL.

## Schema for Song Play Analysis

### Fact Table

* songplays - records in log data associated with song plays

### Dimension Tables

* users- in the app
* songs - in music database
* artists- in music database
* time- timestamps of records in songplays broken down into specific units

![Star Schema](Star_Schema.PNG)


## Project Design

I have created the suggested database design to create Start schema model with Songplay as fact and other tables as dimensions with fact table storing the foriegn keys which are primary key in dimension table

ETL pipeline is buily by using Python scripts with Panda dataframes for loading the song and user datasets and importing them to dimension tables.

### Scripts

There are 3 python scripts with desicription as below :

* "create_tables.py" - This is the first script to be executed to drop and create tables , run this script on terminal by %run create_tables.py command, please note this script uses "sql_queries.py" for only dropping and creating tables  
* "sql_queries.py" - This scipt is used by other 2 python scripts for DROP, CREATE, INSERT and SELECT(Find) statements
* "Etl.py" - This script is used to insert data into all tables and process the ETL pipeline

### Jupyter Notebook

* "etl.ipynb" - This notebook is provided to develop ETL process by loading sample dataset before processing full dataset in the ETL.py
* "test.ipynb" - This notebook is provided to verify the loaded dataset.

Note: I have take some internet reference for code syntax and guidance.
