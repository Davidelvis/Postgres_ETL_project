# Sparkify ETL Pipeline

## Overview
This repository provides an ETL (Extract, Transform, Load) pipeline to populate the Sparkifydb database. The purpose of this database is to enable Sparkify to analyze user behavior, song preferences, and artist information using data from logs and song files. The database serves as a reliable source for answering various business questions and achieving analytical goals.

## Database Design
The schema design follows the STAR schema, which simplifies queries and allows for fast aggregations of data. The schema includes dimension tables for users, artists, and time, along with a fact table for songplays.

### Schema Structure
- **users dimension table**: Contains information about Sparkify users.
- **artists dimension table**: Stores details about artists and their songs.
- **time dimension table**: Records timestamp information for user sessions.
- **songplays fact table**: Central table connecting users, songs, artists, and timestamps.

## ETL Pipeline
The ETL pipeline is implemented in Python, utilizing libraries such as Pandas for efficient data manipulation. The pipeline extracts and loads two types of data: song data and log data.

### Song Data
- Extracts information about songs and artists from song files.
- Loads data into users and artists dimension tables.

### Log Data
- Extracts user session information from log files.
- Loads data into time, users dimension tables, and the songplays fact table.

## Running the ETL Pipeline
1. Run `create_tables.py` to create the data tables based on the specified schema. Existing tables will be dropped and recreated.
2. Run `etl.py` to populate the created data tables.

## Analytical Goals
The Sparkify database serves as a valuable resource for achieving analytical goals, such as identifying popular songs, understanding user behavior, and analyzing traffic patterns at different times of the day.

## Requirements
- Python
- PostgreSQL Database
- Pandas library

## Dependencies
Ensure that the required dependencies are installed before running the ETL pipeline. You can install them using the following command:
```bash
pip install -r requirements.txt
