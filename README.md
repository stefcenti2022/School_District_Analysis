# Analysis of Standardized Test Scores for the PyCity School District
This project uses a Jupyter Notebook that contains code and results for this analysis. There are 2 notebooks of interest in the repository for this project.

PyCitySchools.ipynb contains the original data used to determine the performance of the schools in the PyCity School district.  Later it was suspected that the 9th grade scores at Thomas High School may have been tampered with which would have affected the original analysis. The code from this report has been refactored and is now superceded by the PyCityChallenge.inpynb file.

PyCityChallenge.ipynb is the latest report based on all scores except the 9th grade scores from Thomas High School.

The goal of this analysis is two-fold. For one, we want to find out if the grades from Thomas High School affected the overall performance for the school and for the summary of the entire district.  
The other goal of this analysis is to use it instead of the report containing 9th grades scores from Thomas High School since they have been determined to be invalid for this partiulcar school year.

## Overview of Analysis
This report contains the following information in 2 parts:

### Part 1:
Replaces the reading an math scores for the 9th graders at Thomas High School and shows a summary of these results.

### Part 2:
Repeats the school district analysis and contains the following information:

- A high-level snapshot of the district's key metrics, presented in a table format
- An overview of the key metrics for each school, presented in a table format
- Tables presenting each of the following metrics:
   - Top 5 and bottom 5 performing schools, based on the overall passing rate
   - The average math score received by students in each grade level at each school
   - The average reading score received by students in each grade level at each school
   - School performance based on the budget per student
   - School performance based on the school size 
   - School performance based on the type of school

## Resources
The following CSV files were used as input to this analysis. If modifications were needed they are indicated here:
- schools_complete.csv: This file contains a complete list of school will be in the following format:
   - School ID: This is a unique integer identifying each school in the district.
   - school_name: The name of the high school in text formatted printable string.
   - type: String indictating whether the school is a "District" or "Charter" school.
   - size: integer indicting the total number of students in the school.
   - budget: long integer indicating the school's budget fot the year the students were tested.
- students_complete.csv: This file contains a complete list of the student data for the entire district and is in the following format:
   - Student ID: District-wide unique integer used to identify each student enrolled in the district.
   - student_name: Name of the student.  Some names are not in the proper format and were re-formatted to ensure the names were valid.
   - gender: gender of the student
   - grade: A string representation of the grade level of the student.
   - school_name: A string representing the name of the school the student is enrolled in.
   - reading_score: integer representation of the student's reading score achieved on the standardized test results being analyzed.
   - math_score: integer representation of the student's math score achieved on the standardized test results being analyzed.

## Input Data Cleanup
Before performing a new analysis of the data, the data contained in the students_complete.csv file needed to be cleaned up to fix any student names with suffixes or prefixes and to replace the math and reading scores for every student in Thomas High School with the value 'NaN' or 'not a number'.  This replacement will tell the notebook to ignore any rows that contain a value of 'NaN' when used in any math calculations.

### Removal of Prefixes and Suffixes
These 2 images shows a before and after snapshot of the names that were changed. In particular, notice that "Dr. xyz" was modified to simply "xyz".

Before cleaning:


After cleaning:
<img src="./Resources/after_names_cleaned.png" alt="names after cleaning" width="600"/>


### Replacement of Reading and Math Scores:
The following image shows a snapshot of how the 9th graders have 'Nan' values for their math and reading scores while the rest of the students have the original scores read in from the input file:









