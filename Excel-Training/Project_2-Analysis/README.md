
# Project 2 Analysis

## About the Project

This is one of the projects I completed while learning Excel for data analysis.
The purpose of the project was to use Excel to explore data about data-related jobs, including job titles, salaries, locations, and the skills requested by employers.
I used this project to practice working with a larger dataset and applying some of the Excel tools I had learned during my training.

### Questions I Wanted to Answer

During the analysis, I looked at four main questions:

1. **Does having more skills relate to higher salaries?**
2. **How do salaries differ between different regions?**
3. **Which skills appear most often in data-related jobs?**
4. **What are the salaries associated with the top 10 skills?**

### Excel Skills Used

The following Excel skills were utilized for analysis:

- **📊 Pivot Tables**
- **📈 Pivot Charts**
- **🧮 DAX (Data Analysis Expressions)**
- **🔍 Power Query**
- **💪 Power Pivot**

### Data Jobs Dataset

The dataset used for this project contains real-world data science job information from 2023. 

The main information I worked with included:

- **👨‍💼 Job titles**
- **💰 Salaries**
- **📍 Locations**
- **🛠️ Skills**

## 1️⃣ Does having more skills relate to higher salaries?

### 🔍 Skill: Power Query (ETL)

#### 📥 Extract

- I first used Power Query to extract the original data (`data_salary_all.xlsx`) and create two queries:
    - 🗃️ First one with all the data jobs information.
    - 🔧 The second listing the skills for each job ID.

#### 🔄 Transform

- Then, I transformed each query by changing column types, removing unnecessary columns, cleaning text to eliminate specific words, and trimming excess whitespace.
    - 📊 data_jobs_all

        ![2_Project_Analysis_Screenshot1.png](/0_Resources/Images/2_Project_Analysis_Screenshot1.png)

    - 🛠️ data_job_skills

        ![2_Project_Analysis_Screenshot2.png](/0_Resources/Images/2_Project_Analysis_Screenshot2.png)

#### 🔗 Load

- Finally, I loaded both transformed queries into the workbook, setting the foundation for my subsequent analysis.
    - 📊 data_jobs_all

        ![2_Project_Analysis_Screenshot3.png](/0_Resources/Images/2_Project_Analysis_Screenshot3.png)

    - 🛠️ data_job_skills

        ![2_Project_Analysis_Screenshot4.png](/0_Resources/Images/2_Project_Analysis_Screenshot4.png)

### 📊 Analysis

#### 💡 Insights

From the analysis, I noticed that some roles requiring more skills also had higher median salaries. Senior Data Engineer and Data Scientist roles were among the roles with higher salaries.

This helped me understand how the number and type of skills requested in a job posting can be useful when looking at salary patterns.

   ![2_Project_Analysis_Chart1.png](/0_Resources/Images/2_Project_Analysis_Chart1.png)


- This trend emphasizes the value of acquiring multiple relevant skills, particularly for individuals aiming for higher-paying roles.

## 2️⃣ How do salaries differ between different regions?

### 🧮 Skills: PivotTables & DAX

#### 📈Pivot Table

- 🔢 I created a PivotTable using the Data Model I created with Power Pivot.
- 📊 I moved the `job_title_short` to the rows area and `salary_year_avg` into the values area.
- 🧮 Then I added new measure to calculate the median salary for United States jobs.
    ```
    =CALCULATE(
        MEDIAN(data_jobs_all[salary_year_avg]),
        data_jobs_all[job_country] = "United States")
    ```

#### 🧮 DAX

- To calculate the median year salary I used DAX.

    ```
    Median Salary := MEDIAN(data_jobs_all[salary_year_avg])
    ```

### 📊 Analysis

#### 💡 Insights

- 💼 The analysis showed differences between salaries in the United States and other regions. Some roles, such as Senior Data Engineer and Data Scientist, had relatively high median salaries.
- 💰 The salary disparity between US and Non-US roles is particularly notable in high-tech jobs, which might be influenced by the concentration of tech industries in the US.

    ![2_Project_Analysis_Chart2.png](/0_Resources/Images/2_Project_Analysis_Chart2.png)


## 3️⃣ Which skills appear most often in data-related jobs?

### 🔧 Skill: Power Pivot

#### 💪 Power Pivot

- 🔗 I created a data model by integrating the `data_jobs_all` and `data_jobs_skills` tables into one model.
- 🧹 Since I had already cleaned the data using Power Query; Power Pivot created a relationship between these two tables.

#### 🔗 Data Model

- I created a relationship between my two tables using the `job_id` column.

    ![2_Project_Analysis_Screenshot5.png](/0_Resources/Images/2_Project_Analysis_Screenshot5.png)

#### 📃 Power Pivot Menu

- The Power Pivot menu was used to refine my data model and makes it easy to create measures.

    ![2_Project_Analysis_Screenshot6.png](/0_Resources/Images/2_Project_Analysis_Screenshot6.png)

### 📊Analysis

#### 💡Insights

- 💻 SQL and Python dominate as top skills in data-related jobs, reflecting their foundational role in data processing and analysis.
- ☁️ Emerging technologies like AWS and Azure also show significant presence, underlining the industry's shift towards cloud services and big data technologies.

    ![2_Project_Analysis_Chart3.png](/0_Resources/Images/2_Project_Analysis_Chart3.png)



## 4️⃣ What are the salaries associated with the top 10 skills?

### 📊 Skill: Advanced Charts (Pivot Chart)

#### 📈 PivotChart

- I created a combo PivotChart to plot median salary and skill likelihood (%) from my PivotTable.
    - 🪙 **Primary Axis:** Median Salary (as a Clustered Column)
    - 👍 **Secondary Axis:** Skill Likelihood (as a Line with Markers)
- To customize the chart, I added a title axis title, removed the lines (skill likelihood), and changed the markers to diamonds.

### 📊 Analysis

#### 💡Insights

- 💰 Higher median salaries are associated with skills like Python, Oracle, and SQL, suggesting their critical role in high-paying tech jobs.
- 📉 Skills like PowerPoint and Word have the lowest median salaries and likelihood, indicating less specialization and demand in high-salary sectors.

    ![2_Project_Analysis_Chart4.png](/0_Resources/Images/2_Project_Analysis_Chart4.png)


## Conclusion

This project helped me put the Excel skills I had been learning into practice using a real-world type of dataset.

I was able to explore salaries, job roles, locations, and skills and then present some of the findings using PivotTables and charts.

This was also useful for me as I continue building my data analytics skills and portfolio.
