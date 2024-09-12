# NTI-Final-project

# Supermarket Sales Data Cleaning and Analysis

This notebook documents the process of cleaning and preparing the "Supermarket Sales" dataset for analysis.

## Data Overview

The dataset contains information about supermarket sales, including:

* **Invoice ID:** Unique identifier for each transaction.
* **Branch:**  The branch where the sale occurred (A, B, or C).
* **City:** The city where the branch is located (Yangon, Mandalay, or Naypyitaw).
* **Customer type:** Type of customer (Member or Normal).
* **Gender:** Gender of the customer.
* **Product line:** Category of the product sold.
* **Unit price:** Price of a single unit of the product.
* **Quantity:** Number of units sold.
* **Tax 5%:** Tax applied to the sale.
* **Total:** Total amount of the sale.
* **Date:** Date of the sale.
* **Time:** Time of the sale.
* **Payment:** Payment method used.
* **Rating:** Customer rating of the shopping experience.

## Data Cleaning Process

### Quality Issues

* **Missing values:**  'Tax 5%' and 'Total' columns had missing values.
* **Invalid data types:** 'Unit price' contained 'USD' and needed to be converted to float. 'Invoice ID' contained hyphens and needed to be converted to int.
* **Inconsistent values:** 'Customer type' had inconsistent values (e.g., 'Memberr' instead of 'Member').
* **Incorrect values:** 'Rating' had an incorrect value (97). 'Quantity' had negative values.
* **Duplicate rows:**  Duplicate rows were identified and removed.

![image](https://github.com/user-attachments/assets/bd7c43eb-f1e7-45cc-b0a9-16d22f20e989) 
![image](https://github.com/user-attachments/assets/b0d48600-1d80-43c5-bdcf-07bd9e654b2e)
![image](https://github.com/user-attachments/assets/4b11459e-bfeb-499c-8090-c19e52040be0)


### Tidiness Issues

* **Multiple columns representing one variable:**  'Yangon', 'Naypyitaw', and 'Mandalay' columns represented the same variable 'City'.

### Cleaning Steps

1. **Remove duplicates:** Duplicate rows were dropped.
2. **Fix 'Rating' values:**  Replaced the incorrect value 97 with 9.7.
3. **Fix 'Quantity' values:**  Converted negative values to positive.
4. **Clean 'Invoice ID':** Removed hyphens and converted to int.
5. **Clean 'Unit price':** Removed 'USD' and converted to float.
6. **Clean 'Customer type':** Corrected inconsistent values.
7. **Fill missing values:**  Filled missing values in 'Tax 5%' and 'Total' columns based on other values.
8. **Clean 'Time':** Removed 'PM' and converted to 24-hour format.
9. **Create 'City' column:**  Combined 'Yangon', 'Naypyitaw', and 'Mandalay' columns into a single 'City' column.

## Data Tidying

* **Combined columns:**  The 'Yangon', 'Naypyitaw', and 'Mandalay' columns were combined into a single 'City' column by creating a function to map branch codes to city names.

## Final Dataset

The cleaned dataset was saved as 'Cleaned_data.csv'.
