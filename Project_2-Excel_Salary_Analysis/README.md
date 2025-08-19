
# 📊 Project 2 – Data Jobs Market Analysis (Excel, Power Query, Power Pivot & DAX)

## Introduction

As a data enthusiast and job seeker, I’ve often noticed the lack of structured analysis exploring the most optimal jobs and skills in the **data science job market**.  
The goal of this project is to uncover insights about **skills, salaries, and regional trends** to better understand what top employers are looking for and how professionals can position themselves for higher pay.

---

### Questions to Analyze

To understand the data science job market, I asked the following:

1. **Do more skills get you better pay?**
2. **What’s the salary for data jobs in different regions?**
3. **What are the top skills of data professionals?**
4. **What’s the pay for the top 10 skills?**

---

### Excel Skills Used

The following Excel skills were utilized for analysis:

- **🔍 Power Query** → ETL (Extract, Transform, Load) for data cleaning & preparation.  
- **💪 Power Pivot** → Data modeling and table relationships.  
- **🧮 DAX (Data Analysis Expressions)** → Calculations and advanced measures.  
- **📊 Pivot Tables** → Aggregation and analysis.  
- **📈 Pivot Charts** → Visualization of insights.

---

## 📂 Dataset

The dataset used contains **real-world job postings from 2023**, including:  
- **👨‍💼 Job titles**  
- **💰 Salaries**  
- **📍 Locations**  
- **🛠️ Required skills**  

It provides a representative view of the data analytics & data science job market.  

---

## 1️⃣ Do more skills get you better pay?

### 🔍 Skill: Power Query (ETL)

#### 📥 Extract

- I first used Power Query to extract the original data (`data_salary_all.xlsx`) and create two queries:
    - 🗃️ First one with all the data jobs information.
    - 🔧 The second listing the skills for each job ID.

#### 🔄 Transform

- Then, I transformed each query by changing column types, removing unnecessary columns, cleaning text to eliminate specific words, and trimming excess whitespace.
    - 📊 data_jobs_all

        ![2_Project_Analysis_Screenshot1.png](/Resources/Images/2_Project_Analysis_Screenshot1.png)

    - 🛠️ data_job_skills

        ![2_Project_Analysis_Screenshot2.png](/Resources/Images/2_Project_Analysis_Screenshot2.png)

#### 🔗 Load

- Finally, I loaded both transformed queries into the workbook, setting the foundation for my subsequent analysis.
    - 📊 data_jobs_all

        ![2_Project_Analysis_Screenshot3.png](/Resources/Images/2_Project_Analysis_Screenshot3.png)

    - 🛠️ data_job_skills

        ![2_Project_Analysis_Screenshot4.png](/Resources/Images/2_Project_Analysis_Screenshot4.png)

### 📊 Analysis

#### 💡 Insights

- 📈 There is a positive correlation between the number of skills requested in job postings and the median salary, particularly in roles like Senior Data Engineer and Data Scientist.
- 💼 Roles that require fewer skills, like Business Analyst, tend to offer lower salaries, suggesting that more specialized skill sets command higher market value.

    ![2_Project_Analysis_Chart1.png](/Resources/Images/2_Project_Analysis_Chart1.png)

#### 🤔 So What

- This trend emphasizes the value of acquiring multiple relevant skills, particularly for individuals aiming for higher-paying roles.

## 2️⃣ What’s the salary for data jobs in different regions?

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

- 💼 Job roles like Senior Data Engineer and Data Scientist command higher median salaries both in the US and internationally, showcasing the global demand for high-level data expertise.
- 💰 The salary disparity between US and Non-US roles is particularly notable in high-tech jobs, which might be influenced by the concentration of tech industries in the US.

    ![2_Project_Analysis_Chart2.png](/Resources/Images/2_Project_Analysis_Chart2.png)

#### **🤔 So What**

- These salary insights are important for planning and salary negotiations, helping professionals and companies align their offers with market standards while considering geographical variations.

## 3️⃣ What are the top skills of data professionals?

### 🔧 Skill: Power Pivot

#### 💪 Power Pivot

- 🔗 I created a data model by integrating the `data_jobs_all` and `data_jobs_skills` tables into one model.
- 🧹 Since I had already cleaned the data using Power Query; Power Pivot created a relationship between these two tables.

#### 🔗 Data Model

- I created a relationship between my two tables using the `job_id` column.

    ![2_Project_Analysis_Screenshot5.png](/Resources/Images/2_Project_Analysis_Screenshot5.png)

#### 📃 Power Pivot Menu

- The Power Pivot menu was used to refine my data model and makes it easy to create measures.

    ![2_Project_Analysis_Screenshot6.png](/Resources/Images/2_Project_Analysis_Screenshot6.png)

### 📊Analysis

#### 💡Insights

- 💻 SQL and Python dominate as top skills in data-related jobs, reflecting their foundational role in data processing and analysis.
- ☁️ Emerging technologies like AWS and Azure also show significant presence, underlining the industry's shift towards cloud services and big data technologies.

    ![2_Project_Analysis_Chart3.png](/Resources/Images/2_Project_Analysis_Chart3.png)

#### 🤔So What

- Understanding prevalent skills in the industry not only helps professionals stay competitive but also guides training and educational programs to focus on the most impactful technologies.

## 4️⃣ What’s the pay of the top 10 skills?

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

    ![2_Project_Analysis_Chart4.png](/Resources/Images/2_Project_Analysis_Chart4.png)

### 🤔So What

- This chart highlights the importance of investing time in learning high-value skills like Python and SQL, which are evidently tied to higher paying roles, especially for those looking to maximize their salary in the tech industry.

## 📌 Conclusion

This project demonstrates how **Excel’s advanced features** (Power Query, Power Pivot, DAX, PivotTables & Charts) can be leveraged to perform **end-to-end data analysis**.  

Key takeaways:  
- Professionals with **multiple high-demand skills** achieve better salaries.  
- **Python, SQL, and cloud technologies** stand out as the most valuable skills.  
- Salary potential varies strongly by **region** and **job title**.  

💡 This repository can serve as a reference for:  
- Job seekers planning their **career development**.  
- Data professionals aiming to **maximize salary** by investing in high-value skills.  
- Recruiters and companies to benchmark **market standards**.  

---

## 🚀 Next Steps

- Expand analysis with **Power BI** for interactive dashboards.  
- Automate insights with **Python** or **SQL queries**.  
- Compare results with additional datasets (e.g., LinkedIn, Kaggle job postings). 
