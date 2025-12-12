# Snowflake Hevy Workout Data Pipeline

This repository contains the Snowflake setup for loading and processing workout data from Hevy.

## Overview

The pipeline loads workout data from CSV files into Snowflake using a bronze/silver architecture:

- **BRONZE**: Raw data ingestion (`WORKOUT_LOG_RAW`)
- **SILVER**: Cleaned and transformed data with normalized tables:
  - `WORKOUT_LOG_CLEANSED`: Cleaned ledger table
  - `EXERCISES`: Exercise master table
  - `WORKOUTS`: Workout master table
  - `WORKOUT_EXERCISES`: Junction table
  - `SETS`: Individual set records

## Prerequisites

- SnowSQL CLI installed and configured
- Snowflake connection profile named `training_conn` (or update the script)
- Access to `TRAINING_DB` database with `BRONZE` and `SILVER` schemas

## Usage

```bash
./load_workouts.sh /path/to/workouts.csv
```

The script will:
1. Upload the CSV file to Snowflake stage
2. Load data into BRONZE table
3. Transform and load into SILVER tables
4. Display summary statistics

## Database Structure

### BRONZE Schema
- `WORKOUT_STAGE`: Internal stage for file uploads
- `WORKOUT_LOG_RAW`: Raw CSV data
- `WORKOUT_CSV_FORMAT`: File format definition

### SILVER Schema
- `WORKOUT_LOG_CLEANSED`: Cleaned workout log with proper timestamps
- `EXERCISES`: Unique exercises
- `WORKOUTS`: Unique workouts
- `WORKOUT_EXERCISES`: Workout-exercise relationships
- `SETS`: Individual set records with metrics

## Notes

- CSV files are excluded from git (see `.gitignore`)
- Update the `CONN` variable in `load_workouts.sh` if using a different connection profile

