# Excel Salary Dashboard
<img width="2898" height="996" alt="Project1_Dashboard" src="https://github.com/user-attachments/assets/e6a8c750-6d6a-43b7-a216-e3acf4583fd6" />

# 🟦 Introduction
This dashboard was created for those searching for work in data. It allows the inquierer to gauge the average salary of different data positions based on their desired country location and their desired position type.
## Excel Skills Used
This project untilized the following skills:
- 📊 Charts
- 🔢 Formulas and Functions
- ☑️ Data Validation
  
## Data Jobs Dataset
The dataset used for this project contains real-world data science job information from 2023. The dataset was provided via Luke Barousse's Excel course. The following information could be foudn in this dataset:
- Job titles
- Yearly and Hourly Salaries
- Locations
- Required Skills
  
# 🟦 Dashboard Build
## 📈 Charts
### Data Science Job Salaries - Horizontal Bar Chart
 <img width="910" height="445" alt="Project1_JobTitle_BarChart" src="https://github.com/user-attachments/assets/63b2903c-e760-48ef-86d2-d3d8d2eb5653" />

- **Excel Features:** Used the bar chart feature and axis formatting.
  
- **Design Choice:** Used horizontal bar charts to easily compare median salaries across different data positions.
  
- **Organization:** Positions were organized in descending order based on the median salary to aid in readability.
  
-  **Insights:** Showed which data positions, on average, paid more.  
   
### Country Median Salaries - Map Chart
<img width="802" height="417" alt="Project1_Country_MapChart" src="https://github.com/user-attachments/assets/1d00be18-0293-42f8-8e42-05bbdf34fa8c" />

- **Excel Features:** Used the map chart feature.
  
- **Design Choice:** Used a color-coded map to visualize where data job were located and what the median salary for each country in the data set.
  
-  **Insights:** Provided representation of the median salary ranked high to low from one country to the next.

## 🧮 Formulas and Functions
### Median Salary by Job Title
```
=MEDIAN(
  IF(
    (jobs[job_title_short]=A2)*
    (jobs[salary_year_avg]<>0)*
    (jobs[job_country]=country_ex)*
    (ISNUMBER(SEARCH(type,jobs[job_schedule_type]))),
    jobs[salary_year_avg]
  )
)
```
- **Filtering:** Filteted by job title, country, and schedule type while ignoring all blank salaries.
   
- **Formula:** Nested the `IF()` function inside of the `MEDIAN()` to analyze an array.
  
- **Formula Purpose:** Calculates the median salary for the table used to display the horizontal bar chart for Data Science Job Salaries.
  
### Count of Job Schedule Type
`=SORT(FILTER(K2#,NOT(ISNUMBER(SEARCH("and",K2#)))*(K2# <> 0)))`
- **Unique List Generation:** Used the `FILTER()` function to narrow down the list of job titles to get rid of zero values and any entries with "and" or commas.
  
- **Purpose:** Used to generate the table that will populate the validation filter for job title selection.
    
## ✅ Data Validation
<img width="956" height="654" alt="Project1_DataValidation" src="https://github.com/user-attachments/assets/68ae5eef-c573-4fb4-bbfe-dd286c8c04ed" />


- Data validatin was applied to the selection of the job title, country, and job type. It was used to enure the following:
  - The dashboard is easy to use
  - Reducing the use of incorrect inputs
    
# 🟦 Conclusion
I created this project through the Excel course I took so I and others can gain insight on what data related jobs were available, what the expected salary for these positions are, and ultimately where these positions were located. This dashboard provides great insight for me and others like me wanting to find a career in data.  
