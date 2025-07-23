# IBM Analytics – Employee Attrition

## Table of Contents
- [Project Overview](#project-overview)
- [Objectives](#objectives)
- [Data Source](#data-source)
- [Tools](#tools)
- [Data Cleaning](#data-cleaning)
- [Data Exploratory Analysis](#data-exploratory-analysis)
- [Data Analysis](#data-analysis)
- [Core Insights](#core-insights)
- [Recommendations](#recommendations)

### Project Overview
This project explores the IBM HR Analytics Employee Attrition dataset using Power BI to identify patterns and insights related to employee turnover.


<img width="626" height="328" alt="sceen" src="https://github.com/user-attachments/assets/0dfaf3df-dc7e-4bc7-b362-fd7074168d6d" />
<img width="586" height="329" alt="Screenshot 2025-07-23 130643" src="https://github.com/user-attachments/assets/e3aea23d-1eb0-4273-a378-daaa53536acf" />


### Objectives
To explore patterns in employee turnover, calculate attrition rates by role,Gender,Age Group,Department,Work-life balance,Years at comapany,Monthly income and provide actionable insights using data visualization.


### Data Source
The dataset used in this project is the IBM HR Analytics Employee Attrition & Performance dataset, publicly available on Kaggle:

🔗 IBM HR Analytics Dataset on Kaggle

**Format**: CSV

**Rows**: 1,470 employees

**Columns**: 35 features including Age, Job Role, Department, Monthly Income, Years at Company, and Attrition status


### Tools 
- Power BI  
- DAX (Data Analysis Expressions)  
- Microsoft Excel (Data cleaning)


### Data Cleaning
- Removed Duplicates
- Renamed columns
- Data Type Formatting
- Created Conditional Columns
- Filtered Irrelevant Columns
- Reordered columns
- Replaced Values in columns


### Data Exploratory Analysis
- Analyze patterns and trends driving employee attrition across the organization
- Identify high-risk employee groups by department, age, gender, and job role
- Assess the impact of work-life balance on attrition rates
- Highlight roles with the highest and lowest turnover for targeted intervention


### Data Analysis
- Used Data Analysis Expression to create measures and new columns.
```Attrition Rate = DIVIDE(
    CALCULATE(COUNTROWS('WA_Fn-UseC_-HR-Employee-Attrition'),'WA_Fn-UseC_-HR-Employee-Attrition'[Attrition]="Yes"),COUNTROWS('WA_Fn-UseC_-HR-Employee-Attrition'))
Average Income = AVERAGE('WA_Fn-UseC_-HR-Employee-Attrition'[MonthlyIncome])
Average Years = AVERAGE('WA_Fn-UseC_-HR-Employee-Attrition'[YearsAtCompany])
Employee who left = CALCULATE([Total Employees],'WA_Fn-UseC_-HR-Employee-Attrition'[Attrition]="Yes" )
human resources rate = CALCULATE([Attrition Rate (%)],'WA_Fn-UseC_-HR-Employee-Attrition'[JobRole]="Human Resources")
laboratorytech attrition rate = CALCULATE([Attrition Rate (%)],'WA_Fn-UseC_-HR-Employee-Attrition'[JobRole]="Laboratory Technician")
Salesrep attrition rate = CALCULATE([Attrition Rate (%)],'WA_Fn-UseC_-HR-Employee-Attrition'[JobRole]="Sales Representative")
Total Employees = COUNT('WA_Fn-UseC_-HR-Employee-Attrition'[Age])
Attrition Rate (%) = DIVIDE([Employee who left],[Total Employees])
Age Bracket = 
IF('WA_Fn-UseC_-HR-Employee-Attrition'[Age]>=51,"51-60",
IF('WA_Fn-UseC_-HR-Employee-Attrition'[Age]>=41,"41-50",
IF('WA_Fn-UseC_-HR-Employee-Attrition'[Age]>=31,"31-40",
IF('WA_Fn-UseC_-HR-Employee-Attrition'[Age]>=21,"21-30",
"18-20"))))
```


### Core Insights
- Overall attrition rate is 16.1%, with significant variation across departments and roles.
- Male employees have a higher attrition rate (17%) compared to females (14.8%).
- Sales department records the highest attrition rate (20.6%), while Human Resources has the lowest (0.8%).
- Young employees (18–30) are most likely to leave, with 57% attrition in the 18–20 age group.
- Employees reporting a “better” work-life balance paradoxically show the highest attrition.
- Sales representatives and lab technicians are the most turnover-prone roles, with 39.8% and 23.9% attrition respectively.
- Research & Development has the highest number of exits, due to its size, despite a moderate attrition rate.
- Older employees (41–60) have the lowest attrition rates, indicating stronger retention in experienced workforce segments.


### Recommendations
***Targeted Retention Strategies***
- Focus on Sales Representatives, Laboratory Technicians, and HR Professionals—the top 3 roles with the highest attrition rates.

***Employee Engagement Programs***
- Introduce mentorship, flexible work options, and career development programs in high-risk departments.

**Review Compensation and Workload**
- Evaluate whether workload, salary satisfaction, or lack of growth opportunities are contributing to attrition in specific roles.

**Conduct Exit Interviews**
- Implement structured exit interviews to gather insights on reasons for leaving, especially in high-turnover roles.

**Data-Driven Monitoring**
- Use dashboards like this to regularly track attrition, tenure, and job satisfaction, enabling proactive HR intervention.


  ### Limitations
- The dataset is synthetic and may not reflect real-world HR dynamics.
- No time-based data—unable to track attrition trends over time.
- Limited context (e.g., no data on employee location or exit reasons).
- Attrition is binary (Yes/No), restricting deeper analysis.
- External factors like market or organizational changes are excluded.


  ### References
- IBM HR Analytics Employee Attrition & Performance Dataset. Kaggle.
🔗 https://www.kaggle.com/datasets/pavansubhasht/ibm-hr-analytics-attrition-dataset






