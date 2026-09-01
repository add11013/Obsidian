![[Pasted image 20260901151358.png]]

![[Pasted image 20260901151445.png]]

如同[[Process]] 敘述
subsytem 相關的WFI 進出會路過`rp-subsystem-service`

``` sql
-- 查這個WFI的設定
SELECT * FROM w_wfitems_wf_dataselections WHERE workflowitems_2_workflow = 105373005;

-- 查target是在哪一個workflow使用
SELECT wiw.workflow, wiw.workflowitem, wiw.scenario, wwwd.*  
FROM w_wfitems_wf_dataselections wwwd  
         JOIN w_items_2_workflows wiw ON wwwd.workflowitems_2_workflow = wiw.id  
         JOIN w_workflows ww ON ww.id = wiw.workflow  
         JOIN w_workflowitems wwi ON wwi.id = wiw.workflowitem  
WHERE wwwd.config LIKE '%storeServiceTicketNoteFromWfo%'
```

target程式碼在`rp-subsystem-service` repo中
舉例target `storeFsmStarhubAppointmentUpdates`可以到class `storeFsmStarhubAppointmentUpdatesTarget`看

當有request進來target會執行