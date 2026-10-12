# People Data Pipeline - Azure Databricks

This is my data engineering project built with Azure Databricks, PySpark, ADLS Gen2 and Delta Lake.

The pipeline processes employee data using the Bronze, Silver and Gold architecture.

## How it works

1. **Generator** - creates a CSV file with 1,000 sample employee records, including some invalid data.
2. **Bronze** - reads the CSV file from Azure Storage and saves the raw data to a Delta table.
3. **Silver** - validates and cleans the data, removes duplicates and separates valid, rejected and excluded records. It also checks the record counts to make sure no data is missing.
4. **Gold** - creates a star schema with employee, department and date dimensions and a salary fact table. I use Spark SQL for reporting.

I connected the four notebooks using Databricks Jobs so they run in the correct order. The full job completed successfully.

## Technologies

- Azure Databricks
- Azure Data Lake Storage Gen2
- Python and PySpark
- Spark SQL
- Delta Lake
- Unity Catalog
- Databricks Jobs

## Notebooks

- `employees_generator.ipynb`
- `bronze.ipynb`
- `silver.ipynb`
- `gold.ipynb`

The project currently uses full data loads. Incremental loading and CI/CD are not implemented yet.
