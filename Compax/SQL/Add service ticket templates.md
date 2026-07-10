
## Description
新增service ticket template
category 和 ticket template
relationship 為153

## Script
``` sql
-- 增加 ticket template  
INSERT INTO aax2.s_service_tickets (id, service_ticket, subject, description, ticket_segment, ticket_category, ticket_group, create_date, change_date, last_user, client, entity, status, priority, workflow, due_date_offset, workflow_scenario,  
                                    service_required, reopenable, create_function, read_function, lifespan_in_minutes, due_date)  
VALUES (101, 'Modification of NLT Appointment', 'Modification of NLT Appointment', 'User wants to reschedule NLT for timeslot', 6, 11, 6, '2026-04-01 03:47:17.386000', '2026-04-01 03:47:17.386000', 66, 45, 98, 1, 2, NULL, NULL, NULL, NULL, NULL, NULL,  
        NULL, NULL, NULL);  
INSERT INTO aax2.s_service_tickets (id, service_ticket, subject, description, ticket_segment, ticket_category, ticket_group, create_date, change_date, last_user, client, entity, status, priority, workflow, due_date_offset, workflow_scenario,  
                                    service_required, reopenable, create_function, read_function, lifespan_in_minutes, due_date)  
VALUES (102, 'Modification of WFO Appointment', 'Modification of WFO Appointment', 'User wants to reschedule WFO for timeslot', 6, 11, 6, '2026-04-01 03:47:17.799000', '2026-04-01 03:47:17.799000', 66, 45, 98, 1, 2, NULL, NULL, NULL, NULL, NULL, NULL,  
        NULL, NULL, NULL);  
INSERT INTO aax2.s_service_tickets (id, service_ticket, subject, description, ticket_segment, ticket_category, ticket_group, create_date, change_date, last_user, client, entity, status, priority, workflow, due_date_offset, workflow_scenario,  
                                    service_required, reopenable, create_function, read_function, lifespan_in_minutes, due_date)  
VALUES (103, 'Modification of NLT and WFO Appointment', 'Modification of NLT and WFO Appointment', 'User wants to reschedule NLT and WFO for timeslot', 6, 11, 6, '2026-04-01 03:47:18.070000', '2026-04-01 03:47:18.070000', 66, 45, 98, 1, 2, NULL, NULL,  
        NULL, NULL, NULL, NULL, NULL, NULL, NULL);  
  
  
-- 設定category的ticket template p=template(s_service_tickets), c=category(s_ticket_subjects)  
INSERT INTO aax2.s_relationships (relationship, id_p, id_c, end_dt, duplicate_with, notes, status, entity, role, last_user, tariff, campaign, workflow_setup, workflow_terminate, service_parent, sort_order, customer_process, charge_product_change, filter,  
                                  product_change_time_constraint, element_value, max_qty, description, client, even_uneven, external_id, range_from, range_to, min_qty, duration, fixed_quantity)  
VALUES (153, 101, 900973, NULL, NULL, NULL, 1, 333, NULL, 66, NULL, NULL, NULL, NULL, NULL, 1, NULL, NULL, NULL, NULL, NULL, NULL, NULL, 45, NULL, NULL, NULL, NULL, NULL, NULL, NULL);  
INSERT INTO aax2.s_relationships (relationship, id_p, id_c, end_dt, duplicate_with, notes, status, entity, role, last_user, tariff, campaign, workflow_setup, workflow_terminate, service_parent, sort_order, customer_process, charge_product_change, filter,  
                                  product_change_time_constraint, element_value, max_qty, description, client, even_uneven, external_id, range_from, range_to, min_qty, duration, fixed_quantity)  
VALUES (153, 102, 900973, NULL, NULL, NULL, 1, 333, NULL, 66, NULL, NULL, NULL, NULL, NULL, 1, NULL, NULL, NULL, NULL, NULL, NULL, NULL, 45, NULL, NULL, NULL, NULL, NULL, NULL, NULL);  
INSERT INTO aax2.s_relationships (relationship, id_p, id_c, end_dt, duplicate_with, notes, status, entity, role, last_user, tariff, campaign, workflow_setup, workflow_terminate, service_parent, sort_order, customer_process, charge_product_change, filter,  
                                  product_change_time_constraint, element_value, max_qty, description, client, even_uneven, external_id, range_from, range_to, min_qty, duration, fixed_quantity)  
VALUES (153, 103, 900973, NULL, NULL, NULL, 1, 333, NULL, 66, NULL, NULL, NULL, NULL, NULL, 1, NULL, NULL, NULL, NULL, NULL, NULL, NULL, 45, NULL, NULL, NULL, NULL, NULL, NULL, NULL);  
```

#service_ticket 