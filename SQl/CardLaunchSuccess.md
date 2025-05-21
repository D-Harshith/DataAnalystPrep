Problem Name: Card Launch Success

Problem Number: DataLemur

Category: SQL

Difficulty: Medium

Problem Description: Write a query that outputs the name of the credit card, and how many cards were issued in its launch month. The launch month is the earliest record in the monthly_cards_issued table for a given card. Order the results starting from the biggest issued amount.

Solution Logic: create a CTE with all the column along with rank() (over partition by card_name order by issue_year, issue_month). Now select the card_name, no.of issued cards where rank is 1.

Code:
```SQL
with ranked_months as(
select card_name, issued_amount, issue_month, issue_year,
rank() over(partition by card_name order by issue_year, issue_month) as rank
from monthly_cards_issued o
)

select card_name, issued_amount from ranked_months where rank =1
order by issued_amount desc
```

Last visited: 5/20/25