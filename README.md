***Cafe Sales Data Cleaning Project***

This project demonstrates the process of cleaning and transforming a raw cafe sales dataset using Power Query.

The goal was to convert messy transactional data into a structured and analyzable dataset while learning and improving data cleaning skills.

***Project Objective**

* Produce a clean dataset ready for analysis or visualization

***Repository Structure**

-raw_data/dirty_cafe_sales.csv 			      ~ Original, uncleaned dataset

-cleaned_data/cleaned_cafe_sales.xlsx 		~ Final cleaned dataset

-documentation/cleaning_steps.md 		      ~ Step-by-step explanation of all cleaning transformations

-documentation/cafe_sales_m.txt 		      ~ Power Query M code used for the transformations


***Tools Used**

* Microsoft Excel (Power Query)

***Skills Practiced**

* Data cleaning techniques (handling missing values, duplicates, normalization)
* Creating calculated columns to fix inconsistent numeric data
* Adding flags for inconsistent transactions
* Documenting workflow for clarity and reproducibility
* Applying logical reasoning to clean and validate data

***Key Transformations**

* Promoted headers and set correct data types
* Trimmed and cleaned text columns
* Replaced blank or invalid entries with "BLANK"
* Calculated Quantity and Price per Unit when missing or inconsistent
* Recalculated Total Spent if necessary
* Added flags for inconsistent Data

***Notes**

* Some transactions contained errors or unknown values; these were handled with custom logic and flagged for review.
* The cleaning_steps.md file provides a detailed, step-by-step explanation of every transformation applied.
* This project reflects ongoing learning: *I am continuously improving my skills in Excel, Power Query, and data cleaning best practices.*
