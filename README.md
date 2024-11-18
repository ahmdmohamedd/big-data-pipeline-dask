# Big Data Pipeline with Dask

This repository contains an advanced data pipeline built using **Dask**, designed to process and analyze large datasets that do not fit into memory. The pipeline performs essential tasks such as data loading, cleaning, feature engineering, advanced aggregations, and parallel processing, leveraging Dask's distributed computing capabilities.

## Features
- **Data Loading**: Efficiently load large datasets from CSV files using Dask, which reads the data in chunks and processes it in parallel.
- **Data Cleaning**: Handle missing values by filling categorical columns with "Unknown" and impute numerical fields if required.
- **Feature Engineering**: Create new features like `ORDERYEAR`, `ORDERMONTH`, and `TOTAL_SALE` for better analysis.
- **Advanced Aggregations**: Calculate metrics such as total sales per customer, average sales per order line, and order counts per territory.
- **Parallel Processing**: Utilize Dask's distributed computing to process data across multiple cores or machines, scaling the system for big data workloads.
- **Save Processed Data**: Save the cleaned and aggregated data in CSV or Parquet formats, enabling easy further analysis.

## Installation

### Prerequisites
Before running the pipeline, you need to install the following dependencies:
- **Dask**: For distributed data processing.
- **Pandas**: For general data manipulation.
- **NumPy**: For numerical operations.

You can install these libraries using `pip` or `conda`.

```bash
pip install dask pandas numpy
```

Alternatively, you can use the following `conda` command:
```bash
conda install -c conda-forge dask pandas numpy
```

## How to Use

### Step 1: Clone the repository

Clone this repository to your local machine:

```bash
git clone https://github.com/ahmdmohamedd/big-data-pipeline-dask.git
```

### Step 2: Upload your dataset

Replace `big_data.csv` in the code with the path to your own dataset (ensure it's a large dataset for best results). Make sure your dataset has the necessary structure to match the pipeline's expectations (columns for order details, sales, customer information, etc.).

### Step 3: Run the notebook

Open the `big_data_pipeline.ipynb` in Jupyter or a compatible notebook interface and run the cells sequentially. The notebook will guide you through the data processing pipeline.

### Key Features Breakdown
1. **Loading Data**:
   The data is loaded into Dask DataFrame, enabling the pipeline to handle datasets that are too large to fit into memory.
   
2. **Data Cleaning**:
   Missing values in critical columns (like `ADDRESSLINE2`, `STATE`, `POSTALCODE`, `TERRITORY`) are handled by filling them with "Unknown". This ensures no data is lost during analysis.

3. **Feature Engineering**:
   Additional features are generated, such as `ORDERYEAR`, `ORDERMONTH`, and `TOTAL_SALE`, to enhance the analysis and provide deeper insights into the data.

4. **Parallel Computation**:
   Dask's distributed system is utilized to speed up the computations by using multiple cores or machines, making it highly scalable for big data tasks.

5. **Data Aggregation**:
   Aggregations are performed to calculate key metrics like total sales per customer, average sales per order line, and counts of orders per territory.

6. **Saving Processed Data**:
   After processing, the cleaned and aggregated data is saved in either CSV or Parquet format, which can be further analyzed or used for reporting.

## Example Output
Once the pipeline runs, it will produce various outputs, such as:
- **Total Sales Per Customer**: Aggregated sales data grouped by customer.
- **Average Sales Per Order Line**: The mean sales value for each order line.
- **Orders Per Territory**: Count of orders by territory.

Here is an example of the type of data you can expect after running the pipeline:

### Total Sales Per Customer:
| Customer Name   | Total Sales |
|-----------------|-------------|
| Customer A      | 5000        |
| Customer B      | 12000       |
| Customer C      | 7000        |

### Average Sales Per Order Line:
| Order Line Number | Average Sales |
|-------------------|---------------|
| 1                 | 300           |
| 2                 | 450           |
| 3                 | 600           |

### Orders Per Territory:
| Territory | Orders Count |
|-----------|--------------|
| North     | 1200         |
| South     | 850          |
| West      | 1050         |

## Contributing

Contributions are welcome! If you have ideas for improving the pipeline or fixing any bugs, feel free to open an issue or submit a pull request.

1. Fork the repository.
2. Create a new branch (`git checkout -b feature-branch`).
3. Make your changes.
4. Commit your changes (`git commit -am 'Add new feature'`).
5. Push to your branch (`git push origin feature-branch`).
6. Open a pull request.
