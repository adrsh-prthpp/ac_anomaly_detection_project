# Air-Conditioner Anomaly Detection

An end-to-end data and machine-learning exercise that ingests air-conditioner
product listings through AWS S3 and Snowflake, cleans them with Snowpark, and
uses Isolation Forest to flag unusual prices and product attributes.

## Pipeline

```text
CSV -> Amazon S3 -> Snowflake stage -> Snowpark transformations
    -> pandas features -> Isolation Forest -> anomaly visualization
```

## Features

- Snowflake storage integration and staging SQL
- Data cleaning and feature engineering in Snowpark
- Unsupervised anomaly detection
- Notebook-based analysis
- Output visualization and sample dataset

## Tech stack

- Python and Jupyter
- Snowflake and Snowpark
- Amazon S3
- pandas and scikit-learn
- Matplotlib

## Repository structure

```text
dataset/        Sample product data
snowflake/      Setup SQL and analysis notebook
visualization/  Anomaly scatter plot
```

## Usage

1. Review `snowflake/snowflake_setup.sql` and replace all account-specific
   identifiers with your own environment values.
2. Upload the dataset to a private S3 bucket.
3. Configure a least-privilege Snowflake storage integration.
4. Run `snowflake/ac_anomaly_detection_notebook.ipynb`.

No AWS access keys are required in this repository; use IAM roles and local
credential configuration.

## Project status

**Course/portfolio project.** The repository demonstrates the complete workflow,
but the cloud resources are not provisioned automatically and no automated
tests are included.

## Screenshot

See `visualization/anomaly_scatterplot.png`. Add a sanitized Snowflake worksheet
screenshot or short notebook GIF if it contains no account identifiers.

## Future improvements

- Add infrastructure-as-code with least-privilege defaults
- Add a reproducible local baseline and data-validation tests
- Document dataset provenance and license
- Compare Isolation Forest with robust statistical baselines
- Report precision after manually labeling a validation sample
