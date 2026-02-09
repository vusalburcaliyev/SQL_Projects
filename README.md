# Introduction
📊 Here is the global job market for data enthusiasts. The project focuses on different data analyst roles, explores 💰 top-paying jobs, 📈most in-demand skills, and 🔥more!

🔍 Check the SQL queries here: [Project_jobs](/Project_jobs/)

# Background
The divine purpose of this project is to help job seekers find their desired job, whether it is remote, most-paying, or have more benefits.

The data belongs to [Luke Barousse](https://lukebarousse.com/sql)

### The Questions Answered:
1. What are the top-paying data analyst jobs?
2. What skills are required for these top-paying jobs?
3. What skills are most in demand for a data analyst role?
4. Which skills are associated with higher salaries?
5. What are the most optimal skills to learn?

# What Tools Did I use?
For my analysis, I used the following tools:

- **SQL**: Used to query the database and discover critical insights.
- **PostgreSQL**: My database management system for this project
- **Visual Studio Code**: The place where I executed all my codings
- **Github**: Used to share my SQL scripts and analysis

# The Analysis
Each query for this project aimed at investigating specific aspects of the data analyst job market. Here’s how I approached each question:

### 1. Top 10 Most Paying Data Analyst Jobs

To identify the highest-paying roles, I filtered the data by data analyst roles and remote jobs. I also filtered out positions that did not mention salary. Then, I ordered the query by salary and put a limit to get only the top 10 values.
```sql
SELECT job_id,
    job_title,
    job_location,
    job_schedule_type,
    salary_year_avg,
    job_posted_date::date,
    name as company_name
FROM job_postings_fact
LEFT JOIN company_dim ON company_dim.company_id = job_postings_fact.company_id
WHERE job_title_short = 'Data Analyst'
    AND job_work_from_home = TRUE
    AND salary_year_avg IS NOT NULL
ORDER BY salary_year_avg DESC
LIMIT 10;
```

And here is the breakdown of the said query:

- Wide Salary Range: Top 10 paying data analyst roles span from $184,000 to $650,000, indicating significant salary potential in the field.
- Diverse Employers: Companies like SmartAsset, Meta, and AT&T are among those offering high salaries, showing a broad interest across different industries.

![Top paying jobs](assets/image.png)
*This is the bar graph of the mentioned SQL query for the top-paying jobs. I generated this using MS Excel*

# What I Learned

Throughout this project, I have improved my SQL skills and learned more databases. More importantly, I learned how to manipulate the data:

- With the power of WITH clauses, I can merge different tables!
- Using GROUP BY, I can turn aggregate functions into summarized data!
- Using Analytical thinking, I can turn questions into actionable, insightful SQL queries!
