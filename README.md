# Sparkify Data Lake Project

### Project Summary: 
Sparkify is a music streaming app who wants to analyze the user activity and song details through their streaming app. The data regarding what users are listening to is being sent in json format. Since the logs of user activity and metadata of songs are present in json format, it is difficult for them to query. 
For the ETL job processesI have created a spark session and read the song and log data from s3 bucket s3a://udacity-dend/,  processed the json files and loaded parquet files for users, songs, artists, time, and songplays.
            
**Songs Dataset Example:**
Song dataset contains metadata about the artist and the songs they composed.

**Song Data S3 link:** s3://udacity-dend/song_data

{"num_songs": 1, "artist_id": "ARJIE2Y1187B994AB7", "artist_latitude": null, "artist_longitude": null, "artist_location": "", "artist_name": "Line Renaud", "song_id": "SOUPIRU12A6D4FA1E1", "title": "Der Kleine Dompfaff", "duration": 152.92036, "year": 0}


**Logs Dataset Example:**
Logs dataset contains activity of the users from the streaming app based on certain configurations.

**Log Data S3 link:** s3://udacity-dend/log_data

The json contains details regarding the users such as firstname, lastname, gender, artists, songs, length of the song, starttime, userid.


**FACT Table:**

> **songplays:** records in log data associated with song plays 

>> songplay_id, start_time, user_id, level, song_id, artist_id, session_id, location, user_agent

**Dimension Tables:**

> **users:** users in the app
>>    userId, firstName, lastName, gender, level

> **songs:** songs in music database
>>    song_id, title, artist_id, year, duration

>**artists:** artists in music database
>>    artist_id, name, location, latitude, longitude

>**time:** timestamps of records in songplays broken down into specific units
>>    start_time, hour, day, week, month, year, weekday


### Python Script:

>**etl.py**
- The ETL that reads data from S3, processes that data using Spark, and writes them to a new S3 bucket.
>**dl.cfg**
- Configuration file that contains info about AWS credentials
>**PROJECT.ipynb**
- Test file for etl.py  
   
>**Emptied the S3 bucket**

Emptied the s3 bucket after testing.


**REFERENCES**

> Udacity Knowledge hub.