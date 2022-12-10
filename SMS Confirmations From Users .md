/*

https://platform.stratascratch.com/coding/10291-sms-confirmations-from-users?code_type=1

*/
```sql
select (count(c.phone_number)  / count(s.phone_number)) *100 as percentage
from fb_sms_sends s
left join fb_confirmers c
on c.phone_number = s.phone_number and c.date = s.ds
where  s.ds = '08-04-2020' and s.type = 'message' ;
```

