# Snowflake Assignment

This repository contains documentation for setting up roles, warehouses, and tables in Snowflake, as per the structured approach defined in our project requirements.

## Overview
I've implemented a Snowflake schema to handle various tasks including role management, warehouse creation, data loading, and querying without loading data into tables. This approach emphasizes security and efficiency, particularly with PII data.

## Setup Details

### Roles Hierarchy

- **Accountadmin** - Root role provided by Snowflake.
- **Admin** - Inherits permissions from Accountadmin, manages database and user roles.
- **Developer** - Sub-role under Admin with restricted permissions, mainly for development purposes.
- **PII** - Special role for managing Personally Identifiable Information.
  <img width="640" alt="image" src="https://github.com/owais-ash/SNOWFLAKE/assets/158836234/7e8032bd-6100-4be3-94bf-2ed77d415b79">


### Warehouse Setup

- **Warehouse Name**: `assignment_wh`
- **Size**: Medium
- Utilized for all queries requiring computational resources.

### Database and Schema

- **Database Name**: `assignment_db`
- **Schema Name**: `my_schema`

### Tables

- **Employee Data Table**
  - Loaded from CSV.
  - Contains PII which is masked unless accessed by users with the PII role.

### Data Loading

- Data is loaded into both internal and external stages.
- External table created to query Parquet files directly.

### Masking Policies

- Policies applied to columns containing PII to ensure that data is displayed as masked to unauthorized roles.

## Usage

To query the system, switch to the appropriate role and execute standard SQL queries within the Snowflake UI or via SnowSQL.

## Security

PII data is masked using dynamic data masking to ensure that only authorized roles can view sensitive information.

## Files

- `employee_dataset.csv`: Sample CSV file used for table creation.
- `test1.parquet`: Parquet file for external table querying.

