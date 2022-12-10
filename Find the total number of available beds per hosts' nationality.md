/*

https://platform.stratascratch.com/coding/10187-find-the-total-number-of-available-beds-per-hosts-nationality?code_type=1

*/
```sql

select sum(n_beds) beds , nationality
from airbnb_apartments a
join airbnb_hosts h
on a.host_id = h.host_id
group by 2
order by 1 desc ;
```
