# Data Cleaning Process

## Overview

The dataset contains information on layoffs across various industries, companies, and locations. Raw data often comes with challenges such as inconsistencies, duplicate entries, and missing values. This phase of the project focused on cleaning the data to ensure its accuracy and readiness for analysis.

---

## Steps in Data Cleaning

### 1. Removing Duplicates
**Objective**: To eliminate duplicate rows that could distort the analysis.  
**Approach**:  
- A combination of columns (such as company, location, industry, and date) was used to identify duplicates.  
- Duplicate rows were flagged and removed, keeping only the first occurrence.  
**Outcome**: Duplicates were successfully removed, resulting in unique and reliable data.

### 2. Standardizing Data
**Objective**: To ensure consistency across columns in the dataset.  
**Actions Taken**:  
- The industry column was standardized by consolidating variations (e.g., "CryptoCurrency" was changed to "Crypto").  
- Inconsistencies in the country column were fixed (e.g., "United States." was updated to "United States").  
- The date column was reformatted to the proper DATE type using the `STR_TO_DATE` function.  
**Outcome**: The data is now uniform and consistent, making it easier to analyze.

### 3. Handling Null Values
**Objective**: To address missing values in crucial columns.  
**Approach**:  
- Empty strings in the industry column were converted to NULL for better handling.  
- Missing industry values were filled by referencing rows with matching company names.  
- NULL values were retained in numeric fields (such as `total_laid_off`) to avoid skewing calculations.  
**Outcome**: Missing values were appropriately handled, either by filling or leaving them as NULL, ensuring clarity in the dataset.

### 4. Removing Unnecessary Rows and Columns
**Objective**: To remove irrelevant data that does not contribute to the analysis.  
**Actions Taken**:  
- Rows where both `total_laid_off` and `percentage_laid_off` were NULL were removed as they were not valuable.  
- Temporary columns (like `row_num`) that were created during the cleaning process were dropped.  
**Outcome**: The dataset was streamlined, eliminating unnecessary data and focusing on the relevant information.

---

## Key Highlights

- **Duplicates Removed**: All redundant rows were eliminated to maintain data integrity.
- **Standardized Columns**: Variations in fields like industry, country, and date were unified to ensure consistency.
- **Missing Data Addressed**: Missing values in critical fields were handled logically, either by population or leaving them as NULL.
- **Streamlined Dataset**: The dataset was reduced by removing irrelevant rows and columns, making it more efficient for analysis.
