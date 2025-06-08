Problem Name: Patient Support Analysis
Problem Number: DataLemur

Category: SQL

Difficulty: Medium

Problem Description: These uncategorised calls are labeled as “n/a”, or are left empty when the support agent does not enter anything into the call category field. Write a query to calculate the percentage of calls that cannot be categorised. Round your answer to 1 decimal place. For example, 45.0, 48.5, 57.7..

Solution Logic: 
* Create a CTE with uncategorised calls with call_category IS NULL OR call_category = 'n/a'.


Code:
```SQL
-- SELECT (100.0 * (COUNT(case_id)/(SELECT COUNT(*) from callers))) AS uncategorised_calls
-- from callers WHERE call_category IS NULL
--     OR call_category = 'n/a'

WITH uncategorised_callers AS (
  SELECT COUNT(case_id) AS uncategorised_calls
  FROM callers
  WHERE call_category IS NULL
    OR call_category = 'n/a'
)

SELECT 
  ROUND(100.0 * uncategorised_calls 
    / (SELECT COUNT(*) FROM callers), 1) AS uncategorised_call_pct
FROM uncategorised_callers;
```

Last visited: 6/8/25