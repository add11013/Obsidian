
## Description
Workflow相關的sql

## Script
``` sql
-- add wfi for 472 438  
INSERT INTO aax2.w_items_2_workflows (id, workflow, scenario, workflowitem, description, sort_order, previous_item, autostart, history, status, entity, order_status, order_status_string, order_status_failure, order_status_string_failure, order_status_3, order_status_string_3, order_status_4, order_status_string_4, order_status_5, order_status_string_5, optional, resetable, data_selection_mode, handling_code, return_code_mandatory, title, changed_by, change_dt, last_user, position, close_via_batch, has_labels, instructions, required_function, alternate_returncode_communication, priority)  
VALUES (5000405900, 472, 644, 4515, null, 1, null, 1, 0, 1, 47, null, null, null, null, null, null, null, null, null, null, 'N', 1, 0, null, 0, null, null, '2026-08-05 08:30:20.092000', 148163069, '150.00 150.00', 0, 0, null, null, 0, 1000);  
INSERT INTO aax2.w_items_2_workflows (id, workflow, scenario, workflowitem, description, sort_order, previous_item, autostart, history, status, entity, order_status, order_status_string, order_status_failure, order_status_string_failure, order_status_3, order_status_string_3, order_status_4, order_status_string_4, order_status_5, order_status_string_5, optional, resetable, data_selection_mode, handling_code, return_code_mandatory, title, changed_by, change_dt, last_user, position, close_via_batch, has_labels, instructions, required_function, alternate_returncode_communication, priority)  
VALUES (5000408003, 438, 1, 4515, null, 1, null, 1, 0, 1, 47, null, null, null, null, null, null, null, null, null, null, 'N', 1, 0, null, 0, null, null, '2026-08-05 09:52:08.895000', 148163069, '0 0', 0, 0, null, null, 0, 1000);  
  
-- add return codes  
INSERT INTO aax2.w_wfitems_wf_return_codes (id, workflowitems_2_workflow, return_code, description, entity, status, return_code_ref, notes, return_code_group, is_default, communication_text, changed_by, change_dt, last_user, filter, required_function, alternate_returncode_communication)  
VALUES (5000405902, 5000405900, 1, 'Resolved', 388, 1, 'Resolved', null, null, 1, null, null, '2026-08-05 09:18:14.650000', 148163069, null, null, 0);  
INSERT INTO aax2.w_wfitems_wf_return_codes (id, workflowitems_2_workflow, return_code, description, entity, status, return_code_ref, notes, return_code_group, is_default, communication_text, changed_by, change_dt, last_user, filter, required_function, alternate_returncode_communication)  
VALUES (5000407400, 5000405900, 2, 'Escalate to SHINE', 388, 1, 'Escalate to SHINE', null, null, 0, null, null, '2026-08-05 09:19:04.610000', 148163069, null, null, 0);  
INSERT INTO aax2.w_wfitems_wf_return_codes (id, workflowitems_2_workflow, return_code, description, entity, status, return_code_ref, notes, return_code_group, is_default, communication_text, changed_by, change_dt, last_user, filter, required_function, alternate_returncode_communication)  
VALUES (5000407402, 5000405900, 3, 'Escalate to COP', 388, 1, 'Escalate to COP', null, null, 0, null, null, '2026-08-05 10:35:00.807000', 148163069, null, null, 0);  
INSERT INTO aax2.w_wfitems_wf_return_codes (id, workflowitems_2_workflow, return_code, description, entity, status, return_code_ref, notes, return_code_group, is_default, communication_text, changed_by, change_dt, last_user, filter, required_function, alternate_returncode_communication)  
VALUES (5000408004, 5000408003, 1, 'Resolved', 388, 1, 'Resolved', null, null, 1, null, null, '2026-08-05 10:11:49.270000', 148163069, null, null, 0);  
INSERT INTO aax2.w_wfitems_wf_return_codes (id, workflowitems_2_workflow, return_code, description, entity, status, return_code_ref, notes, return_code_group, is_default, communication_text, changed_by, change_dt, last_user, filter, required_function, alternate_returncode_communication)  
VALUES (5000408501, 5000408003, 2, 'Escalate to COP', 388, 1, 'Escalate to COP', null, null, 0, null, null, '2026-08-05 10:33:57.371000', 148163069, null, null, 0);  
  
--wfi scenarios  
INSERT INTO aax2.w_wfitems_wf_scenarios (id, workflowitems_2_workflow, scenario, return_codes, filter, checks, checks_yn, entity, status, parent, description, workflowitem_status, filterdefinition, last_user)  
VALUES (5000407403, 5000405900, 'Escalate to COP', '03', null, null, null, 756, 1, null, 'Escalate to OCP', null, null, 148163069);  
INSERT INTO aax2.w_wfitems_wf_scenarios (id, workflowitems_2_workflow, scenario, return_codes, filter, checks, checks_yn, entity, status, parent, description, workflowitem_status, filterdefinition, last_user)  
VALUES (5000407401, 5000405900, 'Escalate to SHINE', '02', null, null, null, 756, 1, null, 'Escalate to SHINE', null, null, 148163069);  
INSERT INTO aax2.w_wfitems_wf_scenarios (id, workflowitems_2_workflow, scenario, return_codes, filter, checks, checks_yn, entity, status, parent, description, workflowitem_status, filterdefinition, last_user)  
VALUES (5000405903, 5000405900, 'Resolved', '01', null, null, null, 756, 1, null, 'OK', null, null, 148163069);  
INSERT INTO aax2.w_wfitems_wf_scenarios (id, workflowitems_2_workflow, scenario, return_codes, filter, checks, checks_yn, entity, status, parent, description, workflowitem_status, filterdefinition, last_user)  
VALUES (5000408502, 5000408003, 'Escalate to COP', '02', null, null, null, 756, 1, null, 'Escalate to OCP', null, null, 148163069);  
INSERT INTO aax2.w_wfitems_wf_scenarios (id, workflowitems_2_workflow, scenario, return_codes, filter, checks, checks_yn, entity, status, parent, description, workflowitem_status, filterdefinition, last_user)  
VALUES (5000408005, 5000408003, 'Resolved', '01', null, null, null, 756, 1, null, 'OK', null, null, 148163069);  
  
-- add dependency ('put in queue' and so on)  
INSERT INTO aax2.w_items_dependencies (id, workflow_scenario_item, dependency, dependent_item, starting_rollback_option, description, status, entity, scenario, starting_rollback_option_witem, s_task, column_in_designer, filter, return_codes, workflow, workflowitem_status, call_pp6, changed_by, change_dt, last_user, checks, checks_yn, dependency_scenario, filterdefinition, feature, parent_wfi_return_code, scenario_action, subworkflow_module)  
VALUES (5000407500, 5000405900, 1, 5000307537, null, null, 1, 46, null, null, null, null, null, '01', null, null, 0, null, '2026-08-05 09:27:12.738000', 148163069, null, null, 5000405903, null, null, null, null, null);  
INSERT INTO aax2.w_items_dependencies (id, workflow_scenario_item, dependency, dependent_item, starting_rollback_option, description, status, entity, scenario, starting_rollback_option_witem, s_task, column_in_designer, filter, return_codes, workflow, workflowitem_status, call_pp6, changed_by, change_dt, last_user, checks, checks_yn, dependency_scenario, filterdefinition, feature, parent_wfi_return_code, scenario_action, subworkflow_module)  
VALUES (5000407501, 5000405900, 1, 5000307589, null, null, 1, 46, null, null, null, null, null, '03', null, null, 0, null, '2026-08-05 09:27:39.085000', 148163069, null, null, 5000407403, null, null, null, null, null);  
INSERT INTO aax2.w_items_dependencies (id, workflow_scenario_item, dependency, dependent_item, starting_rollback_option, description, status, entity, scenario, starting_rollback_option_witem, s_task, column_in_designer, filter, return_codes, workflow, workflowitem_status, call_pp6, changed_by, change_dt, last_user, checks, checks_yn, dependency_scenario, filterdefinition, feature, parent_wfi_return_code, scenario_action, subworkflow_module)  
VALUES (5000407502, 5000405900, 1, 5000307609, null, null, 1, 46, null, null, null, null, null, '02', null, null, 0, null, '2026-08-05 09:27:55.986000', 148163069, null, null, 5000407401, null, null, null, null, null);  
INSERT INTO aax2.w_items_dependencies (id, workflow_scenario_item, dependency, dependent_item, starting_rollback_option, description, status, entity, scenario, starting_rollback_option_witem, s_task, column_in_designer, filter, return_codes, workflow, workflowitem_status, call_pp6, changed_by, change_dt, last_user, checks, checks_yn, dependency_scenario, filterdefinition, feature, parent_wfi_return_code, scenario_action, subworkflow_module)  
VALUES (5000408503, 5000408003, 1, 5000070701, null, null, 1, 46, null, null, null, null, null, '02', null, null, 0, null, '2026-08-05 10:16:35.097000', 148163069, null, null, 5000408502, null, null, null, null, null);  
INSERT INTO aax2.w_items_dependencies (id, workflow_scenario_item, dependency, dependent_item, starting_rollback_option, description, status, entity, scenario, starting_rollback_option_witem, s_task, column_in_designer, filter, return_codes, workflow, workflowitem_status, call_pp6, changed_by, change_dt, last_user, checks, checks_yn, dependency_scenario, filterdefinition, feature, parent_wfi_return_code, scenario_action, subworkflow_module)  
VALUES (5000408700, 5000408003, 1, 5000122606, null, null, 1, 46, null, null, null, null, null, '01', null, null, 0, null, '2026-08-05 10:33:06.399000', 148163069, null, null, 5000408005, null, null, null, null, null);  
  
-- add actions  
INSERT INTO aax2.w_wfitems_wf_actions (id, workflowitems_2_workflow, action, description, entity, status, version, last_user, sort_order, changed_by, change_dt, statuses, return_codes, filter) VALUES (5000407102, 5000405900, 4038, null, 338, 1, 0, 148163069, 1, null, '2026-08-05 09:11:06.079000', '1', '01', null);  
INSERT INTO aax2.w_wfitems_wf_actions (id, workflowitems_2_workflow, action, description, entity, status, version, last_user, sort_order, changed_by, change_dt, statuses, return_codes, filter) VALUES (5000407201, 5000405900, 4041, null, 338, 1, 0, 148163069, 1, null, '2026-08-05 09:11:53.826000', '1', '01,02', null);  
INSERT INTO aax2.w_wfitems_wf_actions (id, workflowitems_2_workflow, action, description, entity, status, version, last_user, sort_order, changed_by, change_dt, statuses, return_codes, filter) VALUES (5000408600, 5000408003, 4041, null, 338, 1, 0, 148163069, 1, null, '2026-08-05 10:30:44.500000', '1', '01,02', null);  
INSERT INTO aax2.w_wfitems_wf_actions (id, workflowitems_2_workflow, action, description, entity, status, version, last_user, sort_order, changed_by, change_dt, statuses, return_codes, filter) VALUES (5000408601, 5000408003, 4038, null, 338, 1, 0, 148163069, 1, null, '2026-08-05 10:31:19.449000', '1', '01', null);  
  
  
  
SELECT * FROM w_order_status_config WHERE id IN (101422936, 5000407700, 5000408400);  
  
  
INSERT INTO aax2.w_order_status_config (id, workflow, scenario, order_status, order_status_string, starting_rollback_option, notes, type, filter, changed_by, change_dt, last_user, workflowitem_for_return_code, workflowitem_for_reasoncode, workflowitem_for_transaction, entity, status, sort_order, tasklist_action)  
VALUES (5000407700, 472, 644, 45024, 'Mobile Trouble Ticket', null, null, 0, null, null, '2026-08-05 09:35:25.214000', 148163069, null, null, null, 279, 1, null, null);  
INSERT INTO aax2.w_order_status_config (id, workflow, scenario, order_status, order_status_string, starting_rollback_option, notes, type, filter, changed_by, change_dt, last_user, workflowitem_for_return_code, workflowitem_for_reasoncode, workflowitem_for_transaction, entity, status, sort_order, tasklist_action)  
VALUES (5000408400, 438, 1, 45024, 'General Enquiries', null, null, 0, null, null, '2026-08-05 10:15:48.276000', 148163069, null, null, null, 279, 1, null, null);
```


resolution code如果要下拉選單要加這個，前端會拿這個去找下拉選單並顯示
``` sql
UPDATE aax2.w_wfitems_wf_return_codes
    SET communication_text='TicketResolutionCode'
    WHERE id=5000405902;
UPDATE aax2.w_wfitems_wf_return_codes
    SET communication_text='TicketResolutionCode'
    WHERE id=5000408004;
```