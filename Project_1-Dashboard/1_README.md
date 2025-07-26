# Excel Salary Dashboard

![1_Salary_Dashboard.png](/Resources/Images/1_Salary_Dashboard_Final_Dashboard.gif)

### Introduction
This dashboard was built to explore salary patterns across data-related roles, helping users compare job titles, regions, and work types. The goal was to apply Excel techniques in a real-world scenario while improving analytical insight and dashboard design.

### Dashboard File
My final dashboard is in Salary_Dashboard.xlsx.

### Excel Skills Demonstrated

- 📊 Charts (Bar, Map, Clustered)
- 🔎 Advanced Filtering with `FILTER`, `SEARCH`, `ISNUMBER`
- 📈 Dynamic KPIs with `MEDIAN`, `COUNT`, `IF`, `XLOOKUP`
- 🎛️ Data Validation with dependent dropdowns
- 📋 Structured Tables and Named Ranges
- 🧠 Conditional calculations with array logic

### Data Jobs Dataset
The dataset used for this project contains real-world data science job information from 2023. It includes detailed information on:

👨‍💼 Job titles

💰 Salaries

📍 Locations

🛠️ Skills

## Dashboard Build

📉 Charts

📊 Data Science Job Salaries - Bar Chart

<img src="/Resources/Images/1_Salary_Dashboard_Chart1.png" width="850" height="550" alt="Salary Dashboard Chart1">

- 🛠️ **Excel Features:** Utilized bar chart feature (with formatted salary values) and optimized layout for clarity.
  
- 🎨 **Design Choice:** Horizontal bar chart for visual comparison of median salaries.
  
- 📉 **Data Organization:** Sorted job titles by descending salary for improved readability.
  
- 💡 **Insights Gained:** This enables quick identification of salary trends, noting that Senior roles and Engineers are higher-paying than Analyst roles.

**🗺️ Country Median Salaries - Map Chart**

![1_Salary_Dashboard_Chart2.png](/Resources/Images/1_Salary_Dashboard_Country_Map.gif)

- 🛠️ **Excel Features:** Utilized Excel's map chart feature to plot median salaries globally.

- 🎨 **Design Choice:** Color-coded map to visually differentiate salary levels across regions.

- 📊 **Data Representation:** Plotted median salary for each country with available data.

- 👁️ **Visual Enhancement:** Improved readability and immediate understanding of geographic salary trends.

- 💡 **Insights Gained:** Enables quick grasp of global salary disparities and highlights high/low salary regions.

### 🧮 Formulas and Functions

**💰 Median Salary by Job Titles**
```=MEDIAN(
IF(
    (jobs[job_title_short]=A2)*
    (jobs[job_country]=country)*
    (ISNUMBER(SEARCH(type,jobs[job_schedule_type])))*
    (jobs[salary_year_avg]<>0),
    jobs[salary_year_avg]
)
)
```

🔍 **Multi-Criteria Filtering:** Checks job title, country, schedule type, and excludes blank salaries.

📊 **Array Formula:** Utilizes MEDIAN() function with nested IF() statement to analyze an array.

🎯 **Tailored Insights:** Provides specific salary information for job titles, regions, and schedule types.

🔢 **Formula Purpose:** This formula populates the table below, returning the median salary based on job title, country, and type specified.

🍽️ Background Table

<img src="/Resources/Images/1_Salary_Dashboard_Job_Title.png" width="400" height="500" alt="Salary Dashboard Title">

📉 Dashboard Implementation

Salary Dashboard Title

⏰ **Count of Job Schedule Type**

```=FILTER(J2#,(NOT(ISNUMBER(SEARCH("and",J2#))+ISNUMBER(SEARCH(",",J2#))))*(J2#<>0))```

- 🔍 **Unique List Generation:** This Excel formula below employs the FILTER() function to exclude entries containing "and" or commas, and omit zero values.
- 🔢 **Formula Purpose:** This formula populates the table below, which gives us a list of unique job schedule types.

🍽️ Background Table

![1_Salary_Dashboard_Type.png](/Resources/Images/1_Salary_Dashboard_Screenshot2.png)

📉 Dashboard Implementation:

<img src="/Resources/Images/1_Salary_Dashboard_Type.png" width="350" height="500" alt="Salary Dashboard Type">

### ❎ Data Validation

🔍 **Filtered List**

- **🔒 Enhanced Data Validation:** Implementing the filtered list as a data validation rule under the Job Title, Country, and Type option in the Data tab ensures:
 
  - 🎯 User input is restricted to predefined, validated schedule types

  - 🚫 Incorrect or inconsistent entries are prevented
  - 👥 Overall usability of the dashboard is enhanced

    <img src="/0_Resources/Images/1_Salary_Dashboard_Data_Validation.gif" width="425" height="400" alt="Salary Dashboard Data Validation">

## 📌 Insights and Reflection

This project allowed me to explore advanced Excel techniques while analyzing real-world data science jobs. I practiced logical filtering, dynamic formulas, and interactive visualization. This dashboard is a helpful tool for job seekers, analysts, and anyone interested in salary trends across countries and job types.

I'm proud of the outcome and eager to improve it further with user feedback or new ideas.

## 🚀 Next Steps

- 🧠 Improve interactivity by integrating with Power Query
- 📂 Expand with historical salary data across years
- 💬 Feedback and contributions are welcome!

If you find this project interesting, feel free to ⭐ the repo or connect with me on [LinkedIn](https://www.linkedin.com/in/aurifabio-de-souza-lima).
