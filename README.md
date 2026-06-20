# Student Mental Health SQL Analysis

## Project Overview
This project analyzes mental health data for international students using SQL Server.  
The analysis focuses on the relationship between length of stay and mental health indicators.

## Dataset
The dataset contains information about students, including:
- Student type: international or domestic
- Length of stay
- Depression score
- Social connectedness score
- Acculturative stress score

## Tools Used
- SQL Server Management Studio
- T-SQL
- CSV dataset

## Main Question
How does the length of stay affect mental health scores among international students?

## SQL Analysis
The query groups international students by length of stay and calculates:
- Number of international students
- Average depression score
- Average social connectedness score
- Average acculturative stress score

## Query

```sql
SELECT TOP 9
    stay, 
    COUNT(inter_dom) AS count_int,
    ROUND(AVG(todep), 2) AS average_phq, 
    ROUND(AVG(tosc), 2) AS average_scs, 
    ROUND(AVG(toas), 2) AS average_as
FROM students
WHERE inter_dom = 'Inter'
GROUP BY stay
ORDER BY stay DESC;
