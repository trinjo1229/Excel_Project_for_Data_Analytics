# 🟪 Introduction
## Questions to Analyze
1. Do more skills earn you more money?
2. What's the average salary for different data positions across different locations?
3. What are the top 10 request skills in data?
4. What's the average for those top 10 skills?
   
## Excel Skills Used
- 📅 Pivot Tables
- 📊 Pivot Charts
- 🧼 Power Query
- ⚒ Power Pivot
- 🧮 DAX
## Data Jobs Dataset
The dataset used for this project contains real-world data science job information from 2023. The dataset was provided via Luke Barousse's Excel course. The following information could be foudn in this dataset:
- Job titles
- Yearly and Hourly Salaries
- Locations
- Required Skills
# 🟪 Questions
## ❔ Do more skills earn you more money?
### **Analysis**
<img width="1152" height="646" alt="Project2_PayForSkills" src="https://github.com/user-attachments/assets/17addb12-1485-4f08-adcc-d6c5d75b76a9" />

- There is a positive linear trend that indicates the more skills a data professional has, the more they can expect to earn. This proves to those going into data and those already in the profession that the more skills you gain the more leverage you have for earning a higher salary.
  
### **Method**
#### Over Arching Skill(s): Power Query
- Extracted all of the original data into two queries, one for all of the data job information and one for matching the job ID of each position to the skills requested for the position.

- Cleaned and structured the data for analysis including: changing column types, removing unnecessary columns, and formatting text (i.e uniforming capitalization, removing whitespace, removing punctuation, etc.).

- Loaded all the information into a pivot table for analysis.

## ❔ What's the average salary for different data positions across different locations?
### **Analysis**
<img width="1486" height="554" alt="Project2_SaalryByLocation" src="https://github.com/user-attachments/assets/e7c92c1d-d3f3-4993-8d51-4c34a5c011e7" />

- Based on the data it's clear to see that the average salary for data positions is higher in the US compared to other countries. Amongst these positions, Senior Data Scientist and Machine Learning Engineers are top earners across the world.
  
- It is possible that the US offers higher average salaries for data positions due to vast amount of tech ventures and companies here.
  
- This information let's those trying to find work in data, and those already in the field what negotiation power they have based on their location and it lets companies know the average so they can offer their own competative offers.
  
### **Method**
#### Over Arching Skill(s): PivotTables & DAX
- Created PivotTable using the data model I created in PowerPivot.
- Calculated the average salary values by creating the following measures:
   - Median Salary:
      - ```
        Median Salary:=Calculate(MEDIAN(data_jobs_all[salary_year_avg]),
                                        CROSSFILTER(data_jobs_all[job_id],
                                        data_jobs_skills[job_id], Both))
        ``` 
   - Median Salary In The US:
      - ```
        Median Salary US:=CALCULATE(MEDIAN(data_jobs_all[salary_year_avg]),
                                           data_jobs_all[job_country] = "United States")
        ```
   - Median Salary Outside The US:
      - ```
        Median Salary Non-US:=CALCULATE(MEDIAN(data_jobs_all[salary_year_avg]),
                                               data_jobs_all[job_country] <> "United States")
        ```

## ❔ What are the top 10 request skills in data?
### **Analysis**
<img width="1022" height="617" alt="Project2_SkillLikelihood" src="https://github.com/user-attachments/assets/d9159c6d-d7b6-4052-a1e4-f1b8c20c6744" />

- Amongst the different data positions, SQL and Python are the top 2 most requested skills, followed by AWS and Spark.
  
- Knowing this allows for those trying to break into the data industry know which skills they should prioritize to optimize their chances of getting hired.
  
### **Method**
#### Over Arching Skill(s): PowerPivot
<img width="2606" height="1072" alt="Project2_DataModel" src="https://github.com/user-attachments/assets/d3de0366-6b79-4981-9e09-f35f6f30c2df" />

- Created a data model by linking by `data_jobs_all` table with `data_jobs_skills` by the job ID.

## ❔ What's the average for those top 10 skills?
### **Analysis**
<img width="1156" height="560" alt="Project2_SkillstoPay" src="https://github.com/user-attachments/assets/022689c8-848d-4593-902a-485d54201d5f" />

- Shows that Python and SQL are both highly requested skills in the data industry, and the average salary that can be earned from having these skills is relatively high. While, although having skills in Spark or AWS is not as requested, having then lends to earning a higher salary on average.
  
- This information informs those in the industry and or wanting to go into the industry what their earning potential is based on the skills they currently have or will learn. This gives them the power to negotiate their salary accordingly.
   
### **Method**
#### Over Arching Skill(s): Pivot Chart
- Plotted data into a combonation pivot chart to display salary and skills likelihood (%) simultaneously. I customized the chart by revoming the lines, only leaving the line markers.

# 🟪 Conclusion
I created this project through the Excel course I took so I can gain further insight about the data related jobs available. This included finding out the most requested skills amongst positions, knowing what and how many skills should I learn, and what is the average salary I can expect for learning these skills. I used feaures like Powery Query, PivotTables, DAX, and multiple charts types to discover these insights.   
