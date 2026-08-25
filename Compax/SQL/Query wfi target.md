
## Description
找出哪一個WFI有用這個target

## Script
``` sql
select wiw.workflow, wiw.workflowitem, wiw.scenario, wwwd.*
from w_wfitems_wf_dataselections wwwd
join w_items_2_workflows wiw on wwwd.workflowitems_2_workflow = wiw.id
join w_workflows ww on ww.id = wiw.workflow
join w_workflowitems wwi on wwi.id = wiw.workflowitem
where wwwd.config like '%storeServiceTicketNoteFromWfo%'
```

