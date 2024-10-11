# Data Pipeline Project

This project is designed to create and manage a data pipeline using AWS Redshift. The pipeline extracts data from S3, stages it in Redshift, and transforms it into a set of dimensional tables for analytics purposes.

## Project Structure

- **create_tables.sql**: SQL script to create the necessary tables in Redshift.
- **data_quality.py**: Contains functions to perform data quality checks on the tables.
- **load_dimension.py**: Script to load data into dimension tables.
- **load_fact.py**: Script to load data into the fact table.
- **README.md**: This file.
- **sql_queries.py**: Contains SQL queries used in the ETL process.
- **stage_redshift.py**: Script to stage data from S3 to Redshift.
- **udac_example_dag.py**: Example DAG for Apache Airflow to orchestrate the ETL process.

## Getting Started

### Prerequisites

- Python 3.x
- Apache Airflow
- AWS Redshift
- AWS S3

### Installation

1. Clone the repository:
    ```sh
    git clone <repository-url>
    cd <repository-directory>
    ```

2. Install the required Python packages:
    ```sh
    pip install -r requirements.txt
    ```

### Configuration

1. Update the `dwh.cfg` file with your AWS and Redshift configurations.

### Running the Pipeline

1. Create the tables in Redshift:
    ```sh
    psql -h <redshift-cluster-endpoint> -U <username> -d <database> -f create_tables.sql
    ```

2. Run the Airflow DAG:
    ```sh
    airflow dags trigger udac_example_dag
    ```

## Scripts Description

- **create_tables.sql**: This script contains SQL statements to create staging, fact, and dimension tables in Redshift.
- **data_quality.py**: This script contains functions to check the quality of data loaded into Redshift tables.
- **load_dimension.py**: This script loads data into dimension tables from staging tables.
- **load_fact.py**: This script loads data into the fact table from staging tables.
- **sql_queries.py**: This script contains SQL queries used for creating tables, inserting data, and performing data quality checks.
- **stage_redshift.py**: This script stages data from S3 to Redshift.
- **udac_example_dag.py**: This script defines an Airflow DAG to orchestrate the ETL process.

