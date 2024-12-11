# US_visa_approval_prediction_MLOPS
This is end to end Machine Learning project in order predict weather the application for the visa will be approved or not.


## Problem Statement:
**US visa approval status**
Given certain set of feature such as (continent, education, job-experience, training, employment, current age etc.)
We have to predict weather the application for the visa will be approved or not.

**Features:**
Continent: Asia, Africa, North America, Europe, South America, Oceania
Education: High School, Master’s Degree, Bachelor’s, Doctorate
Job Experience: Yes, No
Required training: Yes, No
Number of employees: 15000 to 40000 
Region of employment: West, Northeast, South, Midwest, Island  
Prevailing wage: 700 to 70000 
Contract Tenure: Hour, Year, Week, Month 
Full time: Yes, No 
Age of company: 15 to 180

**Solution Scope:**
This can be used on real life by Us visa applicants so that they can improve their Resume and criteria for the approval process.

**Solution Approach:**
1.	Machine learning : ML Classification Algorithms
2.	Deep Learning: Custom ANN with sigmoid activation Function

**Solution Proposed:**
We will be using ML
1.	Load the data from DB
2.	Perform EDA and feature engineering to select the desirable features.
3.	Fit the ML classification Algorithm and find out which one performs better.
4.	Select top few and tune hyperparameters.
5.	 Select the best model based on desired metrics.






```Powershell
to create file using CMD/Powershell : type filename (type template.py)
```


- To create environment = `conda create -n visa python=3.8 -y`
- To activate environment = `conda activate visa`
- To install requirements.txt = `pip install -r requirements.txt`


```python
>>> from pathlib import Path
>>> path = "test/test.py"
>>> path = "test/test.py"
>>> Path(path)
WindowsPath('test/test.py')
```
