Problem Name: Second Highest Salary

Problem Number: LeetCode #176

Category: SQL

Difficulty: Medium

Problem Description: Write a solution to find the second highest distinct salary from the Employee table. If there is no second highest salary, return null (return None in Pandas).

Solution Logic: Select NULL if COUNT(distinct salary)<2 else max of salary where salary < max(salary).

Code:
```SQL
SELECT 
    CASE
        WHEN COUNT(DISTINCT salary) < 2 THEN NULL
        ELSE (SELECT MAX(salary)
              FROM Employee 
              WHERE salary < (SELECT MAX(salary) FROM Employee))
    END AS SecondHighestSalary
FROM Employee;
```
```PostGres
SELECT 
    (
        SELECT DISTINCT salary
        FROM Employee
        ORDER BY salary DESC
        OFFSET 1 LIMIT 1
    ) AS SecondHighestSalary;
```
Offset: the OFFSET clause is used to skip a specified number of rows at the beginning of a result set before starting to return data

Last visited: 5/7/25