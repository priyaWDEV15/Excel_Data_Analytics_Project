# 📊 Excel Salary Dashboard
## 📌 Overview  

This dashboard was built in **Excel** to explore salaries across data-related jobs.  
It is designed to help job seekers evaluate compensation for different roles and gain insights into global salary trends.  

The dataset is from **LUKE BAROUSSE EXCEL COURSE** and includes information on **job titles, salaries, locations, and required skills**. 

![Salary Dashboard](/Images/Salary_Dashboard_image/Salary_Dashboard_gif.gif)  

---  

## 🛠️ Excel Skills Applied  
- **📉 Charts** – Bar charts, map charts for visualization
- **🧮 Formulas & Functions** – Median salary calculations, filtering, array formulas
- **❎ Data Validation** – Dropdown filters for job title, country, and schedule type  

---

## 📂 Dataset  
The dataset consists of real-world 2023 job postings in the data domain. It includes: 
- **Job Titles**
- **Salaries**
- **Locations**
- **Skills Required**
- **Job posting Dates**
- **Job Types**

---
## 🔧 Dashboard Components

### 1. 📉 Charts
#### 📊 Median Salaries by Job Titles – Bar Chart 
<img src="/Images/Salary_Dashboard_image/Salary_Dashboard_bar_chart.png" width="850" height="550" alt="Salary Dashboard Bar chart">

- **Excel Feature:** Horizontal bar chart with formatted salary values
- **Design** Sorted by descending salary for clarity
- **Insight:** Senior and engineering roles pay significantly higher than analyst roles

#### 2.🗺️ Country Median Salaries – Map Chart  
![Salary Map](/Images/Salary_Dashboard_image/Salary_Dashboard_map_gif.gif)

- **Excel Feature:** Map chart with country-wise salary data
- **Design** Color scale highlights salary disparities globally
- **Insight:** Quickly shows high-paying (Dark shades) vs. low-paying (low shades) regions

#### 3. 📌 KPI Cards 
<img src="/Images/Salary_Dashboard_image/KPI Cards.png" width="850" height="550" alt="Salary Dashboard Bar chart">

- **💰 Median Salary** – Displays the central tendency of salaries for selected filters
- **📈 Top Job Platform** - Displayes the platform used most to secure the job
- **👨‍💼 Job Count** – Number of jobs available for the chosen filters (role, country, type)

---

### 2. 🧮 Formulas & Functions 

#### 💲Median Salary by Job Titles
```excel
=MEDIAN(
     IF(
        (jobs[job_title_short]=A3)*
         (jobs[salary_year_avg]<>0)*
         ( jobs[job_country]=Country)*
         (ISNUMBER(SEARCH(Type,jobs[job_schedule_type]))),
         jobs[salary_year_avg]
     )
)
```
- Filters salaries based on **job title, country, and type**.
- Excludes **missing/blank salary values**
- Returns median salary tailored to user selection

#### Background Table
<img src="/Images/Salary_Dashboard_image/Job_dashboard_table.png" width="400" height="500" alt="Job Table">

#### Dashboard Output
<img src="/Images/Salary_Dashboard_image/Job_title.png" width="400" height="500" alt="Job dashboard">

#### 🔢 Count of Job Schedule Type
```
=FILTER(I2#,NOT((ISNUMBER(SEARCH("and",I2#))))*(I2#<>0))
```
- Generates a unique list of schedule types
- Removes invalid entries like “and” or “,”
- Supports filtered dropdowns in dashboard

#### Background Table
<img src="/Images/Salary_Dashboard_image/job_schedule_type_table.png" width="400" height="500" alt="Job Type Table">

#### Dashboard Output
<img src="/Images/Salary_Dashboard_image/Job_type.png" width="400" height="500" alt="Job type dashboard">

### ✅ Data Validation
- Implemented dropdown lists for Job Title, Country, and Schedule Type
- Ensures:
  - ✅ Valid entries only
  - 🚫 Prevents errors or inconsistencies
  - 🎯 Enhances user interaction

### 📌 Conclusion
This Excel Salary Dashboard highlights salary trends across different data roles and locations.
By combining charts, formulas, and data validation, the dashboard allows users to:
- Compare salaries by role, country, and type
- Understand global disparities
- Make informed career decisions

































