# UK Food Standards Agency Analysis - Module 12 Challenge

This project analyses the food hygiene ratings of various establishments across the United Kingdom, provided by the UK Food Standards Agency. The analysis is aimed to help journalists and food critics at the food magazine  _Eat Safe, Love_  decide where to focus future articles.

## Project Structure

This project consists of three main parts:

1.  **Database and Jupyter Notebook Setup**
2.  **Database Update**
3.  **Exploratory Analysis**

### Part 1: Database and Jupyter Notebook Setup

-   **Objective**: Set up the MongoDB database and verify the data import and connection.
-   **Steps**:
    1.  Imported the data from  `establishments.json`  into MongoDB using the following command:
        
        `mongoimport --db uk_food --collection establishments --drop --file establishments.json` 
        
    2.  Imported necessary libraries (`pymongo`  and  `pprint`).
    3.  Created an instance of the MongoDB client and connected to the  `uk_food`  database.
    4.  Verified the existence of the  `uk_food`  database and  `establishments`  collection.
    5.  Displayed one document from the  `establishments`  collection using  `find_one()`  and  `pprint`.

### Part 2: Database Update

-   **Objective**: Update the database based on specific requirements from the magazine editors.
-   **Steps**:
    1.  Added a new restaurant "Penang Flavours" in Greenwich to the  `establishments`  collection.
    2.  Queried the  `BusinessTypeID`  for "Restaurant/Cafe/Canteen" and updated the new restaurant with this ID.
    3.  Removed all documents from the  `establishments`  collection where the  `LocalAuthorityName`  is "Dover".
    4.  Converted  `latitude`  and  `longitude`  fields from strings to decimal numbers.
    5.  Converted  `RatingValue`  fields from strings to integers and set non-numeric values to  `null`.

### Part 3: Exploratory Analysis

-   **Objective**: Answer specific questions to guide the magazine's content focus.
-   **Questions and Results**:
    1.  **Which establishments have a hygiene score equal to 20?**
        -   **Result**: Found 41 establishments. Displayed the first result and converted the results to a Pandas DataFrame.
    2.  **Which establishments in London have a RatingValue greater than or equal to 4?**
        -   **Result**: Found 33 establishments. Displayed the first result and converted the results to a Pandas DataFrame.
    3.  **What are the top 5 establishments with a RatingValue of 5, sorted by lowest hygiene score, nearest to the new restaurant added, "Penang Flavours"?**
        -   **Result**: Found and displayed the top 5 establishments meeting the criteria. Converted the results to a Pandas DataFrame.
    4.  **How many establishments in each Local Authority area have a hygiene score of 0?**
        -   **Result**: Aggregated the data and found the top 10 Local Authority areas with the highest count of establishments having a hygiene score of 0. Converted the results to a Pandas DataFrame.

## Results

The analysis provided insights into the hygiene scores and ratings of establishments in various regions, highlighting areas of interest for future articles in the magazine.

### Notebooks

-   `NoSQL_setup_starter.ipynb`: Contains the setup and database update steps.
-   `NoSQL_analysis_starter.ipynb`: Contains the exploratory analysis steps and results.

## Dependencies

-   Python 3.x
-   pymongo
-   pandas
-   pprint

## Usage

1.  Ensure MongoDB is running locally on port 27017.
2.  Import the  `establishments.json`  data into MongoDB using the provided  `mongoimport`  command.
3.  Run the  `NoSQL_setup_starter.ipynb`  notebook to set up and update the database.
4.  Run the  `NoSQL_analysis_starter.ipynb`  notebook to perform the exploratory analysis.

## References
- Carter, Simon. "Data Analysis and Visualization with Python." _Computing in Science & Engineering_ 20, no. 3 (2018): 70-79
-  MongoDB Inc. "MongoDB Python Driver Documentation." MongoDB. Accessed June 16, 2024.  [https://pymongo.readthedocs.io/en/stable/](https://pymongo.readthedocs.io/en/stable/).
-   Python Software Foundation. "Pandas Documentation." Accessed June 16, 2024.  https://pandas.pydata.org/docs/.
