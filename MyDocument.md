## NYC Jobs Data Analysis — Documentation

Analyze NYC job postings dataset using PySpark to extract insights related to job categories, salaries, qualifications, and skills.


### Data Exploration
Column Types

Numerical: Salary Range From, Salary Range To.  
Categorical: Agency, Job Category, Salary Frequency.   
Text: Job Description, Minimum Qual Requirements.   

## Exploratory finding from Source

Text fields contain unstructured information  
Salary values use multiple frequencies  
Some columns contain missing or noisy data   

## Data Cleaning

Removed duplicates  
Standardized text fields (lowercase, encoding fixes)  
Parsed the dates and removed invalid entries for salary.

## Feature Engineering

Converted salaries to annual equivalents using frequency multipliers.  
Skills extracted from noisy text fields.  
Extracted highest degree requirements using regex patterns.  

## Data Insights

Licensing requirements significantly influence pay levels.   
Salary normalization is required due to mixed frequency types.  
Public sector roles looked into domain expertise rather than specific skills.   

## Assumptions made

Average salary computed as midpoint of salary range.  
Annual salary calculated using standard working hours and multipling based on the frequency of pay.  
Skills inferred from Preferred Skills, although it can be dedused from 'Job Description' as well.  
Only valid dates are taken for job-posting based KPI's.  
matplotlib used for visualization.  

## Deployment Proposal Pipeline

Raw Data > Spark Processing > Curated Dataset > BI / Reporting  

Scheduling can be done by Azure Data Factory by batch processing.  
Execution Trigger can be Batch processing triggered upon arrival of new job posting data for near real-time data.  

## Learnings & Challenges

Set-up for the project locally was difficult in macs for jupiter notebooks execution,relatively easy in windows machine.  
Handling noisy text data  
Dealing with inconsistent salary formats  
Extracting structured features from unstructured fields  
Importance of domain understanding.  