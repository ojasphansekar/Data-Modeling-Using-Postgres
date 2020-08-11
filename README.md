# Udacity Data Engineer Nanodegree - Data Modeling with Postgres

### Introduction
A startup called Sparkify wants to analyze the data they've been collecting on songs and user activity on their new music streaming app. The analytics team is particularly interested in understanding what songs users are listening to. Currently, they don't have an easy way to query their data, which resides in a directory of JSON logs on user activity on the app, as well as a directory with JSON metadata on the songs in their app.

As a data engineer, I have created a Postgres database with tables designed to optimize queries on song play analysis. My role is to create a database schema and ETL pipeline for this analysis, test the database I created and ETL pipeline by running queries given to me by the analytics team from Sparkify and compare my results with their expected results.

### Files
<b>test.ipynb</b> displays the first few rows of each table to check the database.
<b>create_tables.py</b> drops and creates your tables. You run this file to reset your tables before each time you run your ETL scripts.
<b>etl.ipynb</b> reads and processes a single file from song_data and log_data and loads the data into your tables. This notebook contains detailed instructions on the ETL process for each of the tables.
<b>etl.py</b> reads and processes files from song_data and log_data and loads them into your tables.
<b>sql_queries.py</b> contains all the SQL queries, and is imported into the last three files above.
The Schema for the Song Play Analysis

Using the song and log datasets, I have created a star schema optimized for queries on song play analysis.
### Below are the tables created in this project :

#### Fact Table
<b>songplays</b> - records in log data associated with song plays i.e. records with page NextSong
songplay_id, start_time, user_id, level, song_id, artist_id, session_id, location, user_agent
#### Dimension Tables
<b>users</b> - users in the app
user_id, first_name, last_name, gender, level
<b>songs</b> - songs in the music database
song_id, title, artist_id, year, duration
<b>artists</b> - artists in the music database
artist_id, name, location, latitude, longitude
<b>time</b> - timestamps of records in songplays broken down into the specific unit
start_time, hour, day, week, month, year, weekday

### Use
Remember to run create_tables.py before running etl.py to reset your tables. Run test.ipynb to confirm your records were successfully inserted into each table.

### NOTE: You will not be able to run test.ipynb, etl.ipynb, or etl.py until you have run create_tables.py at least once to create the sparkifydb database, which these other files connect to.