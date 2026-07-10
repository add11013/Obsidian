
## Description
新增Category
像是Inbound call/Outbound call等彈窗中的Category

## Script
``` sql
-- 增加Category 父節點  
INSERT INTO aax2.s_ticket_subjects_detail (id, subject_detail, notes, last_user, status, entity, selection_level, client, instructions, template, pictogram, external_ref, hide_from_customer)  
VALUES (900891, 'Appointment', NULL, 1, 1, 467, 1, 45, NULL, NULL, NULL, NULL, 0);  
INSERT INTO aax2.s_ticket_subjects_detail (id, subject_detail, notes, last_user, status, entity, selection_level, client, instructions, template, pictogram, external_ref, hide_from_customer)  
VALUES (900892, 'Modifications', NULL, 1, 1, 467, 1, 45, NULL, NULL, NULL, NULL, 0);  
  
-- 增加Category 葉節點, level_x拿來分層的  
INSERT INTO aax2.s_ticket_subjects (id, subject, valid, sort_order, entity, status, level_1, level_2, level_3, level_4, level_5, client, instructions, template, tasklist, function, external_ref, pictogram, workdays, priority, customer_type)  
VALUES (900973, 'Service Request | Appointment | Modifications', 1, 19, 331, 1, 900822, 900891, 900892, NULL, NULL, 45, NULL, NULL, NULL, NULL, NULL, NULL, NULL, NULL, NULL);  
```

#service_ticket 