# Analysis of Standardized Test Scores for the PyCity School District
This project contains tools to help with the analysis of standardized test data for the PyCity School District.

This report contains the analyis for the current school year.

## Overview of Analysis
Here is the list of deliverables for the analysis of the school district: 

- A high-level snapshot of the district's key metrics, presented in a table format
- An overview of the key metrics for each school, presented in a table format
- Tables presenting each of the following metrics:
   - Top 5 and bottom 5 performing schools, based on the overall passing rate
   - The average math score received by students in each grade level at each school
   - The average reading score received by students in each grade level at each school
   - School performance based on the budget per student
   - School performance based on the school size 
   - School performance based on the type of school

## Input Data
The input file containing a complete list of school will be in the following format:
- School ID: This is a unique integer identifying each school in the district.
- school_name: The name of the high school in text formatted printable string.
- type: String indictating whether the school is a "District" or "Charter" school.
- size: integer indicting the total number of students in the school.
- budget: long integer indicating the school's budget fot the year the students were tested.

THe snippet below shows the heading and first few rows of data:

(TODO: change this link to point to an image in the assets folder.)
<img width="399" alt="image" src="https://user-images.githubusercontent.com/110138522/185729706-d6cd514d-6468-4f0d-adc4-f816d4ff0e30.png">

### Verify Data Results
Before running the analysis tools on the input files, the data was inspected for anomolies such as missing data values, missing rows, incorrect data types, etc. 

First, the number of rows were calculated as follows:
- School Data has 15 rows
- Student Data has 9.999 rows TODO: find real value

Next, both input files were verified. To check for missing data, several methods are available in Jupyter. For this analyis, checking for null data and summing the count was used since the student data has thousands of rows and this was more concise. The following images show the results from this inspection:

TODO: add image of the following results:
- sum of null school values
- sum of null student values 

After verifying the School and Student data files did not have any missing values, the file of grades for each student was verified.

TODO: insert image of NaN vales found in the grades data file

As shown above, it turned out that there were a couple of N/A values that needed to be addressed.  Three different options were considered for dealing with this issue.
#### Option 1: Do Nothing
Leaving N/A values will be skipped during calls to sum or average the data, howver, if multiplicaton or division with a NaN value may cause problems if the answer is required elsewhere in the code.
#### Option 2: Drop the Row
Dropping the row for a NaN value will also remove any other useful data that is contained in that row which could pose a problem later in the code. Before going this route these questions must be answered for every dataset:
   1. How much data would be removed if NaNs are dropped?
   2. How would this impact the analysis?
#### Option 3: Fill in the Row
Choose an appropriate value to be filled in place of every NaN value encountered. If this route is chosen, the values inserted must be carefully be considered for every analysis performed later.

For this analysis, the fillna() method was used to fill in rows with NaN values.

Next, the data types of the values were verified that they made sense for any analysis that were the data will be needed later. The dtypes attribute of the Pandas DataFrame was used to verify data types.

TODO: add images of school and student column data types.

As shown in the image above, all fields such as scores and budget have integer data types which is correct so no changes were needed based on data type.









