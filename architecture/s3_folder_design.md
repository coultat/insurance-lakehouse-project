# S3 Folder Design for Insurance Lakehouse Project

## Project Bucket
`s3://insurance-lakehouse-project-<your-name>/`

## Folder Structure

### Raw Layer
- `raw/customers/` - Customer data in original format (CSV/JSON)
- `raw/policies/` - Insurance policies
- `raw/claims/` - Claims data
- `raw/payments/` - Payment transactions
- `raw/agents/` - Insurance agents data
- `raw/fraud_indicators/` - Fraud indicators

### Bronze Layer (immutable raw data)
- `bronze/` - Raw data stored as Parquet, minimally cleaned

### Silver Layer (cleaned data)
- `silver/` - Deduplicated, validated data

### Gold Layer (aggregated data)
- `gold/` - Business-ready data for analytics

### Operational Folders
- `checkpoints/` - Spark Structured Streaming checkpoints
- `quarantine/` - Faulty or unprocessable files

## Purpose
This design follows the Medallion Architecture pattern (Bronze/Silver/Gold) for data lakes.