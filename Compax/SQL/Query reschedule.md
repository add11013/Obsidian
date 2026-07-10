
## Description
查詢可以reschedule的人

## Script
``` sql
select * from d_nlt_appointments dfa where dfa.sign_up in (select sign_up from d_workflows where id in (select workflow from d_workflowitems where workflowitem = 2680 and status = 8)) order by create_date desc;
```
