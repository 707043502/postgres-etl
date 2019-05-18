# ETL For Sparkify -V1.0.2

## 1.INTRODUCTION

🏡Sparkify has been collecting on songs and user activity on their new music streaming. 🙏In order to support further data analysis which is really important for such online bussiness, this project are launched🚀 to help parse data from 😭`json logs` and create 😄reasonable `database schema` for further analysis purpose.

## 2.DATA ORGANIZATION
We choose relational database for analytical reason, since the scale of data is relatively small Postgres works out well😄. Then it's 👌we use star schema to decompose our table into `FACTS` and `DIMENSION`

Tables are organized as:
- FACTS: songplays
- DIMENSION: users, songs, artists, time

The following picture shows how we organize our tables

<div align=center>
<img src="https://github.com/707043502/postgres-etl/blob/master/pic/schema.png" width="150" height="200">
</div>

## 3.PRACTICE
Users can run the scripts follow steps bellow😋

`Step1`: **data preparation**
- **log data** and **song data** should be provided in the folder &emsp;&emsp;`./data/log_data/` <br>
  &emsp;&emsp;`./data/song_data/` <br>as **json file**

`Step2`: **prepare database env**
- create tables using<br>     &emsp;&emsp;```python create_tables.py```

`Step3`: **start ETL**
- using<br> &emsp;&emsp;```python etl.py```
    
## 4.FILEs 
In case any customization,we post out our file organization strategies for referencing.👨

```create_tables.py```: process to prepare database

```sql_queries.py```: basic queries used in this project, including:
- create table
- queries of updating 
- queries of selecting
- drop table

```etl.py```: main logic that maintain the ETL process

- parse a `./data/song_data/*.json` to update TABLE: `songs`, `artists`

- parse a `./data/log_data/*.json` to update TABLE: `time`, `users` join with songs and artists to maintain TABLE: `songplays`
  
- read a `json file` and deliver duty to exact process function



