/*

https://platform.stratascratch.com/coding/10300-premium-vs-freemium?tabname=question

*/

```sql
with paying_CTE as ( 
select
    f.date,
    sum(case 
    when a.paying_customer = 'yes' then downloads
    end) as paying,
    sum(case 
    when a.paying_customer = 'no' then downloads
    end) as non_paying 
from 
    ms_download_facts f,
    ms_acc_dimension a,
    ms_user_dimension u
where 
    u.acc_id = a.acc_id
    and
    f.user_id = u.user_id
group by 
    f.date 
)
select * from 
paying_CTE
where non_paying > paying
order by date 
```
