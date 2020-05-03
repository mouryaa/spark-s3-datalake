# Project: Data Lake

*This project creates a data lake in S3 by processing data using Spark.*

## ETL pipeline

1. Load credentials
2. Read data from S3
    - Song data: 's3://sparkify-data-mourya/song_data'
    - Log data: 's3://sparkify-data-mourya/log_data'

    The script reads song_data and load_data from S3.

3. Process data using spark

    Transforms them to create five different tables listed under `Dimension Tables and Fact Table`.
    Each table includes the right columns and data types. Duplicates are addressed where appropriate.

4. Load it back to S3

    Writes them to partitioned parquet files in table directories on S3.

    Each of the five tables are written to parquet files in a separate analytics directory on S3. Each table has its own folder within the directory. Songs table files are partitioned by year and then artist. Time table files are partitioned by year and month. Songplays table files are partitioned by year and month.
