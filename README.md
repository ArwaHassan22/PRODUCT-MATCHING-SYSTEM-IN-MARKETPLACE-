# Product Matching System  

## Overview  
This project implements a product matching system that utilizes machine learning techniques to match seller product names with a master product database. The system is designed to improve the accuracy of product listings by automatically identifying and matching products based on their names and attributes.  

## Features  
- **Text Cleaning**: Preprocess product names to standardize formats and remove unwanted characters.  
- **Feature Extraction**: Extract relevant features such as concentration and dosage form from product names.  
- **Fuzzy Matching**: Use the RapidFuzz library to perform fuzzy string matching, allowing for flexible comparisons between product names.  
- **Parallel Processing**: Enhance performance by leveraging multiprocessing to handle large datasets efficiently.  
- **Confidence Scoring**: Provide confidence levels for matches based on similarity scores.  
- **SKU Integration**: Compare and store expected SKUs to evaluate the accuracy of matches against the seller's actual SKUs.  

## Requirements  
To run this project, you need the following Python packages:  
- `numpy`  
- `pandas`  
- `matplotlib`  
- `seaborn`  
- `rapidfuzz`  
- `openpyxl`  
- `joblib`  
- `scikit-learn`  

You can install the required packages using pip:  
```bash  
pip install numpy pandas matplotlib seaborn rapidfuzz openpyxl joblib scikit-learn
```

## Dataset
The project requires Excel sheets:

Dataset: Contains seller product names, associated information, and actual SKUs.

Master File: Contains a list of standardized product names and their corresponding SKU values.

## Usage
- Load the datasets using the provided code snippet.
- Clean and preprocess the text data.
- Extract features from the product names.
- Use the find_best_match function to match seller products with master products.
- Analyze the results, including expected SKUs, and export the matched products to an Excel file.

Example:
```bash
import pandas as pd  
.
.
.
# Load datasets  
seller_sheet = pd.read_excel('Product Matching Dataset.xlsx', sheet_name='Dataset')  
master_sheet = pd.read_excel('Product Matching Dataset.xlsx', sheet_name='Master File')  

# Clean and process data (as shown in the provided code)  
# ...  

# Export results  
seller_sheet.to_excel('matched_products.xlsx', index=False)  
```
## Output
The output of the program will be an Excel file named matched_products.xlsx containing:

- Matched products
- Similarity scores
- Confidence levels
- Expected SKUs

## Accuracy
The system calculates the accuracy of the matching process by comparing the expected SKU with the actual SKU from the seller sheet. 
The accuracy percentage is printed to the console, giving insights into the performance of the matching algorithm.

