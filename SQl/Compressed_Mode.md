Problem Name: Compressed Mode

Problem Number: Data Lemur

Difficulty: Medium

Problem Description: give all the elements who have the most frequency

Solution Logic: Create a CTE with max(occurance). In the SQL statement find the order_id or item_count where the occurance = max(occurance).

Code:
```SQL
with max_freq as(
select max(order_occurrences) as max_order_occurrences from items_per_order 
)

select item_count as mode
from items_per_order where order_occurrences = (select max_order_occurrences from 
max_freq) 

Last visited: 5/7/25