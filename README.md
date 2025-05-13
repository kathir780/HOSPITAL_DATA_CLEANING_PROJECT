# Hospital Data Cleaning Project

## Project Overview
This project focuses on cleaning a large real-world hospital dataset with over 2.1 million rows and 33 columns. The goal was to prepare the data by handling missing values, removing inconsistencies, and standardizing formats to make the data analysis-ready. This clean dataset enables better analysis of patient demographics, diagnoses, admission types, and healthcare system performance.

## Dataset
- **Initial Rows**: 2,101,588
- **Initial Columns**: 33
- **Final Columns**: 27
- **Source**: Kaggle - Hospital Patient Admission Dataset

## Objective
To clean and standardize a large hospital dataset for the purpose of enabling accurate and efficient data analysis.

## Cleaning Workflow

1. **Load & Preview the Data**:
   - Loaded the dataset using pandas.
   - Previewed data using:
     - `df.shape` for dimensions
     - `df.head()` for a preview of rows
     - `df.info()` for column types and null counts
     - `df.describe()` for numeric summary

2. **Handle Missing Values**:
   - **Dropped Columns with Too Many Nulls**: 
     - Birth Weight (90.1% missing)
     - CCSR Procedure Code (27% missing)
     - Total Charges, Total Costs, Ratio of Costs to Charges (35% missing)
   - **Imputed or Cleaned Columns**:
     - Hospital Service Area, Permanent Facility ID, APR Risk of Mortality, and APR Severity of Illness Description were filled with 'Unknown' or mode values.
     - Dropped columns with minimal missing data.

3. **Standardize Column Names**:
   - Converted all column names to lowercase and replaced spaces and hyphens with underscores.

4. **Remove Duplicates**:
   - Checked for duplicate rows and removed them using `df.drop_duplicates()`.

5. **Data Type Fixes**:
   - Ensured `discharge_year` was an integer.
   - Converted `zipcode3` to a string type.
   - Converted categorical columns to 'category' data type for memory efficiency.

6. **Categorical Value Normalization**:
   - Standardized categorical values (e.g., "M" → "Male", "U" → "Unknown") using `.replace()` and `.str.lower()`.

7. **Final Dataset**:
   - After cleaning, the dataset had 2,099,954 rows and 27 columns.
   - Exported the final cleaned dataset as `hospital_cleaned.csv`.

## Results
- Cleaned and standardized a massive dataset with over 2.1 million rows.
- Removed 6 columns with excessive null values.
- Imputed or cleaned the remaining critical columns.
- Resulted in an analysis-ready hospital dataset for further insights and visualizations.

## Key Learnings
- Learned the importance of data cleaning before any analysis or modeling.
- Gained experience with large-scale datasets using efficient pandas operations.
- Developed strategies for dropping or imputing columns based on null thresholds.
- Practiced handling categorical normalization and data type optimization.

## Files
- `hospital_raw.csv`: Original dataset
- `hospital_cleaned.csv`: Final cleaned dataset
- `Hospital_Cleaning_Project.ipynb`: Jupyter Notebook for data cleaning steps
- `README.md`: GitHub documentation file

## License
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

