# FMCG Data Engineering Project with Databricks

## Project Overview
This is a comprehensive data engineering project for a Fast-Moving Consumer Goods (FMCG) company, implemented using Databricks. The project demonstrates a modern data pipeline for processing and analyzing sales data from both parent and child companies.

## Project Structure

### 1. Data Organization
```
project-de-fmcg-atlikon/
├── 0_data/
│   ├── 1_parent_company/
│   │   ├── full_load/
│   │   │   ├── dim_customers.csv
│   │   │   ├── dim_gross_price.csv
│   │   │   ├── dim_products.csv
│   │   │   └── fact_orders.csv
│   │   └── incremental_load/
│   │       ├── fact_orders.csv
│   │       └── incremental_data_parent_company_query.txt
│   └── 2_child_company/
│       └── full_load/
│           ├── customers/
│           │   └── customers.csv
│           ├── gross_price/
│           │   └── gross_price.csv
│           └── orders/
│               └── landing/
│                   ├── orders_2025_07_01.csv
│                   └── orders_2025_07_02.csv
│
└── 1_codes/
    ├── 1_setup/
    │   ├── dim_date_table_creation.ipynb
    │   ├── setup_catalog.ipynb
    │   └── utilities.ipynb
    ├── 2_dimension_data_processing/
    │   ├── 1_customers_data_processing.ipynb
    │   ├── 2_products_data_processing.ipynb
    │   └── 3_pricing_data_processing.ipynb
    └── 3_fact_data_processing/
        ├── 1_full_load_fact.ipynb
        └── 2_incremental_load_fact.ipynb
```

### 2. Data Model

#### Dimension Tables:
- **dim_customers**: Customer information
- **dim_products**: Product catalog with categories and variants
- **dim_gross_price**: Pricing information for products
- **dim_date**: Date dimension table for time-based analysis

#### Fact Tables:
- **fact_orders**: Sales transactions with product, customer, and quantity details

## Technical Stack
- **Databricks**: Cloud-based data processing platform
- **Delta Lake**: For reliable data lakes
- **PySpark**: For distributed data processing
- **SQL**: For data manipulation and analysis

## Data Processing Pipeline

### 1. Setup and Initialization
- Catalog and schema creation
- Date dimension table generation
- Utility functions setup

### 2. Dimension Data Processing
- Customer data processing
- Product data processing
- Pricing data processing

### 3. Fact Data Processing
- Full load processing for historical data
- Incremental load for new transactions

## Key Features

1. **Multi-Company Data Integration**
   - Handles data from both parent and child companies
   - Standardizes data from different sources

2. **Incremental Processing**
   - Efficient processing of new data
   - Minimizes processing time and resource usage

3. **Data Quality**
   - Data validation and cleaning
   - Consistent data types and formats

4. **Scalable Architecture**
   - Built on Databricks for horizontal scaling
   - Handles large volumes of data efficiently

## Getting Started

### Prerequisites
- Databricks workspace
- Access to Databricks File System (DBFS)
- Appropriate permissions to create catalogs and tables

### Setup Instructions
1. Run the setup notebooks in order:
   - `1_setup/setup_catalog.ipynb`
   - `1_setup/dim_date_table_creation.ipynb`
   - `1_setup/utilities.ipynb`

2. Process dimension data:
   - `2_dimension_data_processing/1_customers_data_processing.ipynb`
   - `2_dimension_data_processing/2_products_data_processing.ipynb`
   - `2_dimension_data_processing/3_pricing_data_processing.ipynb`

3. Process fact data:
   - `3_fact_data_processing/1_full_load_fact.ipynb` (for initial load)
   - `3_fact_data_processing/2_incremental_load_fact.ipynb` (for ongoing updates)

## Data Flow
1. Raw data is loaded from CSV files
2. Data is transformed and cleaned
3. Dimension tables are created/updated
4. Fact tables are populated with transaction data
5. Data is made available for analysis and reporting

## Maintenance
- Regular monitoring of data loads
- Performance optimization of queries
- Periodic validation of data quality

## Note
This project is designed to work with Databricks' free edition, making it accessible for learning and small-scale implementations.
