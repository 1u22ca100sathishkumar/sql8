# sql8
SELECT
    Department_ID,
    Employee_Name,
    Salary,
    SUM(Salary) OVER (PARTITION BY Department_ID) AS Dept_Total_Salary,
    MAX(Salary) OVER (PARTITION BY Department_ID) AS Dept_Max_Salary,
    MIN(Salary) OVER (PARTITION BY Department_ID) AS Dept_Min_Salary,
    RANK() OVER (PARTITION BY Department_ID ORDER BY Salary DESC) AS Salary_Rank
FROM Employees;
Explanation
SUM() OVER() → total salary per department

MAX() OVER() → highest salary per department

MIN() OVER() → lowest salary per department

RANK() OVER() → ranking employees by salary within each department
