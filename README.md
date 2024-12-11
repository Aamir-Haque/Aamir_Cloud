# Exploratory Data Analysis for Vancouver Parks Dataset

## Project Title
Exploring Infrastructure Allocation in Vancouver Parks

## Objective
The main objective of this project is to perform an exploratory data analysis (EDA) on the Vancouver Parks dataset to uncover patterns, trends, and insights about park infrastructure. Specifically, the project examines:
1. The availability of washrooms in Vancouver parks.
2. The relationship between park size and the presence of washrooms.
## Dataset
The dataset for this project was sourced from the "Parks, Recreation & Pets" category of the Open Data Vancouver portal. It includes information about over 220 parks and 40 major facilities managed by the City of Vancouver. Key features of the dataset include:

- **Park Name**: The name of the park.
- **Park Area (Hectares)**: The size of the park.
- **Washrooms Availability**: Whether the park has washroom facilities (Y/N).
- **Other Features**: Additional facilities and special features.

## Methodology
The analysis followed a structured Data Analysis Process (DAP), which included the following steps:
![Design of DAP](https://github.com/Aamir-Haque/Aamir_Cloud/blob/1e7b4eaed4d1046c772e355661173f1155f42f4d/Design%20of%20the%20Data%20Analytic%20Platform.jpg)
### 1. Data Ingestion
- The dataset was downloaded from the Open Data Vancouver portal in CSV format.
- Uploaded to an Amazon S3 bucket named `prp-parks-raw-aam` for scalable and secure storage.

### 2. Data Profiling
- Conducted using AWS Glue DataBrew to assess the dataset’s structure, content, and quality.
- Identified issues such as missing values in `EWStreet` and `NSStreet` columns and outliers in the `Hectare` column.

### 3. Data Cleaning
- Addressed missing values by removing affected rows.
- Removed outliers from the `Hectare` column to ensure accurate analysis.
- Cleaned data was stored in the transformed bucket `prp-parks-trf-aam.`

### 4. Data Wrangling
Data wrangling was performed to ensure the dataset was properly structured, cleaned, and prepared for analysis. The following steps were included:

- **Handling Missing Data**:
  - Missing values in critical columns were either removed or imputed based on their relevance and potential impact on analysis.

- **Outlier Detection and Removal**:
  - Outliers in numerical fields like `Hectare` were identified and removed to prevent skewed analysis results.

- **Standardization**:
  - Categorical fields were standardized to ensure consistency (e.g., formatting values in the `Washrooms` column as `Yes` or `No`).

- **Data Storage**:
  - The cleaned and transformed data was saved in Amazon S3 buckets (`prp-parks-trf-aam`), ensuring easy access for further analysis.

### 5. Data Pipeline
![Data Pipeline](https://github.com/Aamir-Haque/Aamir_Cloud/blob/1e7b4eaed4d1046c772e355661173f1155f42f4d/Data%20Pipeline.jpg)

- Created a data pipeline using AWS Glue’s Visual ETL tool to:
  - Aggregate the count of washrooms based on availability.
  - Calculate the average park size (in hectares) for each category of washroom availability.
  - Store processed data in both CSV and Parquet formats in Amazon S3.

## Tools and Technologies
- **Cloud Storage**: Amazon S3
- **Data Profiling and Cleaning**: AWS Glue DataBrew
- **Data Pipeline Creation**: AWS Glue Visual ETL

## Insights and Findings
1. **Descriptive Analysis**:
   - The analysis revealed the total number of parks with and without washrooms.
   - This provides insights into infrastructure distribution and highlights potential gaps.

2. **Exploratory Analysis**:
![Data Visualization](https://github.com/Aamir-Haque/Aamir_Cloud/blob/1e7b4eaed4d1046c772e355661173f1155f42f4d/Data%20Visualization.jpg)
   - Larger parks are significantly more likely to have washrooms compared to smaller parks.
   - This indicates a bias in infrastructure allocation favoring larger parks.

## Recommendations
- **Infrastructure Equity**: Consider improving washroom facilities in smaller parks to enhance accessibility and usability for all visitors.
- **Future Analysis**: Expand the scope to include other facilities (e.g., playgrounds, sports fields) and assess their distribution relative to park size and location.

## Deliverables
- **Cleaned Dataset**: Available in CSV and Parquet formats.
- **Visualizations**: Charts illustrating key findings, such as the correlation between park size and washroom availability.
- **Documentation**: Comprehensive report summarizing the methodology, findings, and recommendations.

## Conclusion
This project demonstrates the application of EDA techniques to uncover meaningful insights about public infrastructure. The findings can inform data-driven decisions to improve park amenities and ensure equitable distribution of resources in Vancouver's parks.
