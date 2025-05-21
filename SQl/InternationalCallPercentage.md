Problem Name: International Call Percentage

Problem Number: DataLemur

Category: SQL

Difficulty: Medium

Problem Description: A phone call is considered an international call when the person calling is in a different country than the person receiving the call. What percentage of phone calls are international? Round the result to 1 decimal.

Solution Logic: 
* Create a CTE with caller id, receiver id, caller country, reciever country by joining the phone calla with phone info on caller id (we get caller country), now join this expression with phone info on caller_id, receiver id from previously table (we get receiver country).
* Now select the count where country code of caller != receiver and divide by total count of rows.


Code:
```SQL
with caller_receiver as(
SELECT 
    caller.caller_id,
    caller.receiver_id, 
    pi.country_id as caller_country,  
    receiver.country_id as receiver_country
FROM 
    phone_calls caller 
join 
    phone_info pi on caller.caller_id = pi.caller_id
join 
    phone_info receiver on caller.receiver_id = receiver.caller_id
    )

select 
      round((count(*) * 1.0 /(select count(*) from caller_receiver)) * 100,1) as international_calls_pct
from 
      caller_receiver
where 
      caller_country != receiver_country
```

Last visited: 5/20/25