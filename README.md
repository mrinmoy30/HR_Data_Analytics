# 📊 HR Data Analytics

This project aims to conduct a comprehensive analysis of employee attrition patterns within the company. The primary goal is to identify key drivers of turnover and provide actionable insights by utilizing various Key Performance Indicators (KPIs) and visualizations within Power BI.

---

### [▶️ View the Interactive Report (Link)](https://app.powerbi.com/view?r=eyJrIjoiZjg2ODY4ODQtYmRiYy00YmU1LTk3YmEtYjcyOGIxZWQ2ZmY1IiwidCI6ImEzMjAwOGMwLWRhZjgtNDc5Zi1hOTk1LTI4MTVlYThmMTVjZiJ9)

## Dashboard Preview 🖥️

![Dashboard Preview](https://github.com/mrinmoy30/HR_Data_Analytics/blob/main/HR%20Data%20Analytics%20Dashboard.jpg)

---

## 1. Business Requirements 🎯

The primary goal of this dashboard is to answer key business questions regarding employee turnover and provide actionable insights. The core objectives addressed are:

### KPI Requirements:

- **Total Employees:** The overall count of active and former employees in the dataset.
- **Attrition Count:** The total number of employees who have left the company.
- **Attrition Rate:** The percentage of the total workforce that has left.
- **Average Age:** The average age of the employees in the dataset.
- **Average Years at Company:** The average tenure of employees within the company.

## Analysis Requirements (Visualizations):

- Quantify the overall attrition rate and absolute number of leavers.
- Identify which departments experience the highest attrition rates.
- Pinpoint specific job roles with elevated turnover.
- Analyze how attrition rates vary across different employee age groups.
- Determine the attrition count based on marital status.
- Assess the impact of working overtime on the likelihood of leaving.
- Understand the relationship between employee-reported Work Life Balance and attrition counts.
- Compare the average monthly income of employees who left versus those who stayed, segmented by job role.
- Analyze the correlation between the number of years since an employee's last promotion and their attrition rate.

## 2. Data Processing & Transformation (ETL) 🛠️

The following data processing and transformation steps were performed, primarily using Power BI's Power Query and DAX:

- **Data Loading:** Imported the **HR Data.xlsx** - HR data.csv file into Power BI.
- **Data Type Verification:** Ensured columns were assigned appropriate data types (e.g., numeric, text).
- **Calculated Columns:** Utilized existing columns like **CF_age band** and **CF_attrition** label for analysis.

## 3. Data Modeling 🔗

Created key **DAX measures** to drive the **KPI** visuals and charts:

- **`Total Employees = SUM('HR Data'[Employee Count])`**
- **`Attrition Count = CALCULATE( [Total Employees], 'HR Data'[CF_attrition label] = "Ex-Employees" )`**
- **`Attrition Rate = DIVIDE( [Attrition Count], [Total Employees] ) (Formatted as %)`**
- **`Average Age = AVERAGE('HR Data'[Age])`**
- **`Avg Years at Company = AVERAGE('HR Data'[Years At Company])`**
- **`Avg Monthly Income = AVERAGE('HR Data'[Monthly Income])`**

- **Measure Table:** Grouped all created DAX measures into a dedicated **`_Measures`** table for better organization.

## 4. Dashboard Design & Visualizations 📊

The analysis is presented on a single-page Power BI dashboard. Interactive slicers allow for dynamic exploration of the data.

Here’s your HR dashboard **Visualizations Table**, formatted cleanly in the same Markdown style as before 👇

| **Visualization Type**   | **Purpose**                                            | **Data Fields Used**                                                                          |
| :----------------------- | :----------------------------------------------------- | :-------------------------------------------------------------------------------------------- |
| **Slicers**              | Filter the entire report dynamically                   | `Department`, `Job Role`, `Gender`, `CF_age band`                                             |
| **KPI Cards**            | Display key headline metrics                           | `Total Employees`, `Attrition Count`, `Attrition Rate`, `Average Age`, `Avg Years at Company` |
| **Horizontal Bar Chart** | Compare attrition rates across Departments             | **Y-axis:** `Department`, **X-axis:** `Attrition Rate`                                        |
| **Horizontal Bar Chart** | Rank Job Roles by attrition rate                       | **Y-axis:** `Job Role`, **X-axis:** `Attrition Rate`                                          |
| **Column Chart**         | Show attrition rate variation across Age Bands         | **X-axis:** `CF_age band`, **Y-axis:** `Attrition Rate`                                       |
| **Donut Chart**          | Show distribution of leavers by Marital Status         | **Legend:** `Marital Status`, **Values:** `Attrition Count`                                   |
| **Donut Chart**          | Show distribution of leavers based on Overtime status  | **Legend:** `Over Time`, **Values:** `Attrition Count`                                        |
| **Column Chart**         | Display attrition counts based on Work Life Balance    | **X-axis:** `Work Life Balance`, **Y-axis:** `Attrition Count`                                |
| **Clustered Bar Chart**  | Compare Avg. Income of Stayers vs. Leavers by Job Role | **Y-axis:** `Job Role`, **X-axis:** `Avg Monthly Income`, **Legend:** `CF_attrition label`    |
| **Line Chart**           | Analyze attrition rate trend by Years Since Promotion  | **X-axis:** `Years Since Last Promotion`, **Y-axis:** `Attrition Rate`                        |

## 5. How to Use This Dashboard 🤔

This interactive dashboard allows for flexible data exploration:

- **Open the `.pbix` file** in Power BI Desktop.
- **Overall View:** Start by observing the main KPIs (Attrition Rate, Count, etc.) at the top for a high-level summary.
- **Identify Problem Areas:** Use the "Attrition Rate by Department" and "Attrition Rate by Job Role" charts to quickly see which areas have the highest turnover percentages.
- **Demographic Focus:** Examine the "Attrition Rate by Age Band" and "Attrition Count by Marital Status" charts to understand which demographic groups are most affected.

### Explore Drivers:

- Analyze the "Attrition Count by OverTime" donut chart. Crucially, remember this shows counts; the underlying rate difference is the key insight.
- Examine the "Attrition Count by Work Life Balance" chart. Again, focus on the insight that the highest rate is for 'Bad' balance, even if the count is lower.
- Use the "Avg Monthly Income..." chart to compare compensation between those who left and stayed within specific roles.
- Interpret the "Attrition Rate by Years Since Last Promotion" line chart to see how career progression timing relates to leaving.
- Interactive Filtering: Use the Slicers (Department, Job Role, Gender, Age Band) at the top left to filter the entire dashboard. For example:
- Select "Sales" in the Department slicer to see specific attrition rates, age distributions, and income comparisons only for the Sales department.
- Select "Sales Representative" in the Job Role slicer to drill down into the data for this high-attrition group.
- Combine filters (e.g., "Sales" department and "0-25" Age Band) for highly specific analysis.

## 5. Data-Driven Insights 💡

- **KPI Summary:** The company has **1470** employees with an overall attrition count of **237**, resulting in a **16.12%** attrition rate. The average employee age is **36.92** years, staying **7.01** years on average.
- **Slicer Interactivity:** Allows filtering across **Departments (Sales, HR, R&D)**, specific Job Roles, Gender, and pre-defined **Age Bands (0-25, 25-34, etc.)**.
- **Departmental Rates:** **Sales (20.63%)** and **HR (19.05%)** show significantly higher attrition rates than **R&D (13.84%)**.
- **Job Role Rates:** **Sales** Representatives have an extremely high **39.76%** attrition rate. **Laboratory Technicians (23.94%)** and **Human Resources (23.08%)** also show elevated rates.
- **Age Band Rates:** The **0-25** age group has the highest attrition rate **(39.18%)**, followed by the **25-34** group **(20.22%)**. Rates decrease for older groups.
- **Marital Status Counts:** **Single** employees account for the largest number of leavers **(120, 50.6%)**, followed by **Married (84)** and **Divorced (33)**. (Rate analysis shows **Singles** also have the highest attrition rate).
- **Overtime Counts:** Slightly more leavers worked **Overtime (127)** than did not **(110)**. (Rate analysis shows **OverTime** dramatically increases attrition risk).
- **Work Life Balance Counts:** Most leavers rated WLB as **'3' (Better) (127)**. However, rate analysis indicates those rating **'1' (Bad)** have the highest probability of leaving, despite lower volume **(25)**.
- **Income Comparison:** Average Monthly Income for **Ex-Employees** is visibly **lower** than for **Current Employees** in key roles like **Research Scientist** and **Healthcare Representative**.
- **Promotion Timing Rates:** Attrition Rate is **highest** for those **0 years** or **7+ years** since their last promotion, suggesting issues with both **early and later career stagnation**.

## 6. Business Impact 🚀

The identified attrition patterns have direct financial and operational consequences:

- **Financial Drain:** Replacing **237** employees, especially the high volume from **R&D (133)** and high-rate roles like **Sales Reps (33)**, incurs substantial recruitment, onboarding, and lost productivity costs annually.
- **Talent Pipeline Risk:** Losing nearly **40%** of employees **under 25** undermines future leadership potential and ROI on early-career investments.
- **Operational Instability:** High turnover in **Sales (20.63% rate)** and key technical roles like **Lab Technicians (23.94% rate)** can disrupt customer relationships, project timelines, and innovation efforts.
- **Potential Burnout Culture:** The strong correlation between **Overtime (30.5% attrition rate)** and poor **Work-Life Balance ratings (31.3% attrition rate for 'Bad' rating)** suggests underlying issues affecting employee well-being and engagement.
