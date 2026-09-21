# Machine Learning Techniques for Fraud Detection

This directory contains a Google Colab notebook that demonstrates a big-data
workflow for exploring credit-card transactions and preparing the data for
fraud detection.

## Notebook

- `Big_data_Analytics_assignment.ipynb` - End-to-end Hadoop/HDFS setup,
  transaction ingestion, PySpark cleaning, exploratory analysis, and fraud
  rate visualizations.

## Project workflow

The notebook covers:

1. Installing and configuring Java 11 and Hadoop 3.3.6.
2. Starting a single-node HDFS environment in Google Colab.
3. Loading the IBM credit-card transactions CSV from Google Drive.
4. Uploading the CSV to HDFS and inspecting file blocks, size, and replication.
5. Reading the data with Pandas and PySpark.
6. Cleaning transaction amounts, timestamps, numeric fields, categorical
   values, missing values, and the `Is Fraud?` target.
7. Exploring fraud rates by month, transaction hour, and payment method.
8. Plotting aggregate fraud-rate results with Pandas and Matplotlib.

## Dataset

The notebook expects the IBM credit-card transactions archive to be available
at:

```text
/content/drive/MyDrive/credit_card_transactions-ibm_v2_csv.zip
```

The extracted CSV is expected at:

```text
/content/extracted_folder/credit_card_transactions-ibm_v2.csv
```

The source dataset is approximately 2.3 GB and contains 15 columns, including
transaction date/time, amount, merchant details, payment method, error data,
and the `Is Fraud?` label. The notebook records approximately 24.4 million
transactions covering 1991-2020.

## Requirements

- Google Colab or a Linux environment with shell-command support
- Python 3.13 (as stated in the notebook)
- Java 11
- Apache Hadoop 3.3.6
- PySpark 3.5.6
- Pandas, NumPy, Matplotlib, and Seaborn
- Google Drive access to the dataset archive

## Running the notebook

1. Open `Big_data_Analytics_assignment.ipynb` in Google Colab.
2. Run the setup cells to install Java, Hadoop, and PySpark.
3. Mount Google Drive when prompted.
4. Confirm that the dataset archive is stored at the path above.
5. Run the cells in order so that HDFS is configured and started before the
   data is uploaded and analyzed.

The notebook uses local single-node HDFS settings and is intended for
educational analysis. It does not include a completed supervised-model
training and evaluation section; the current workflow prepares and explores
the fraud-labelled data.
