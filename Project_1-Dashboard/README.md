# Excel Salary Dashboard
<img width="2898" height="996" alt="Project1_Dashboard" src="https://github.com/user-attachments/assets/e6a8c750-6d6a-43b7-a216-e3acf4583fd6" />

# Introduction
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
  
# Dashboard Build
## Charts
### Data Science Job Salaries - Horizontal Bar Chart
<img width="900" height="496" alt="Project1_JobTitle_BarChart" src="https://github.com/user-attachments/assets/04a2c616-c99c-4c4d-a43c-c86a76afa93a" />  
  
- **Excel Features:** Used the bar chart feature and axis formatting.
- **Design Choice:** Used horizontal bar charts to easily compare median salaries across different data positions.
- **Organization:** Positions were organized in descending order based on the median salary to aid in readability.
-  **Insights:** Showed which data positions, on average, paid more.  
   
### Country Median Salaries - Map Chart
<img width="802" height="417" alt="Project1_Country_MapChart" src="https://github.com/user-attachments/assets/1d00be18-0293-42f8-8e42-05bbdf34fa8c" />

- **Excel Features:** Used the map chart feature.
- **Design Choice:** Used a color-coded map to visualize where data job were located and what the median salary for each country in the data set.
-  **Insights:** Provided representation of the median salary ranked high to low from one country to the next.

## Formulas and Functions
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
- **Filtering:**
- **Formula:**
- **Purpose:**
## Data Validation
# Conclusion
