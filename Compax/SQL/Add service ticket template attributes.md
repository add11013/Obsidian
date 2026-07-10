
## Description
新增每個service ticket templates中的欄位
attribute 和 tempalte 
relationship 為150

## Script
``` sql
-- 增加新的attribute  
INSERT INTO aax2.s_attributes (id, attribute, field_type, rel_entity, notes, last_user, status, entity, is_unique, values_from_entity, minimum, maximum, mandatory, client, has_date_range, sort_order, values_label, parent_entity, parent_entity_id,  
                               default_provider_entity, values_filter, locked_with_wf, is_readonly, function, is_visible_for_csc)  
VALUES (960, 'Reschedule Reason', 8, 97, NULL, 1, 1, 689, 0, 2500, NULL, NULL, 1, NULL, NULL, 2, NULL, NULL, NULL, NULL, NULL, 0, 0, NULL, 0.00);  
  
-- 設定ticket template的attributes p=template(S_SERVICE_TICKETS), c=attribute(S_ATTRIBUTES)  
INSERT INTO aax2.s_relationships (relationship, id_p, id_c, end_dt, duplicate_with, notes, status, entity, role, last_user, tariff, campaign, workflow_setup, workflow_terminate, service_parent, sort_order, customer_process, charge_product_change, filter,  
                                  product_change_time_constraint, element_value, max_qty, description, client, even_uneven, external_id, range_from, range_to, min_qty, duration, fixed_quantity)  
VALUES (150, 101, 960, NULL, NULL, NULL, 1, 333, NULL, 1, NULL, NULL, NULL, NULL, NULL, 1, NULL, NULL, NULL, NULL, NULL, NULL, NULL, 45, NULL, NULL, NULL, NULL, NULL, NULL, NULL);  
INSERT INTO aax2.s_relationships (relationship, id_p, id_c, end_dt, duplicate_with, notes, status, entity, role, last_user, tariff, campaign, workflow_setup, workflow_terminate, service_parent, sort_order, customer_process, charge_product_change, filter,  
                                  product_change_time_constraint, element_value, max_qty, description, client, even_uneven, external_id, range_from, range_to, min_qty, duration, fixed_quantity)  
VALUES (150, 102, 960, NULL, NULL, NULL, 1, 333, NULL, 1, NULL, NULL, NULL, NULL, NULL, 1, NULL, NULL, NULL, NULL, NULL, NULL, NULL, 45, NULL, NULL, NULL, NULL, NULL, NULL, NULL);  
INSERT INTO aax2.s_relationships (relationship, id_p, id_c, end_dt, duplicate_with, notes, status, entity, role, last_user, tariff, campaign, workflow_setup, workflow_terminate, service_parent, sort_order, customer_process, charge_product_change, filter,  
                                  product_change_time_constraint, element_value, max_qty, description, client, even_uneven, external_id, range_from, range_to, min_qty, duration, fixed_quantity)  
VALUES (150, 103, 960, NULL, NULL, NULL, 1, 333, NULL, 1, NULL, NULL, NULL, NULL, NULL, 1, NULL, NULL, NULL, NULL, NULL, NULL, NULL, 45, NULL, NULL, NULL, NULL, NULL, NULL, NULL);  
  
  
-- 開新的表給新的reason code  
INSERT INTO aax2.k_entities (id, description, status, entity_type, alias_name, table_name, entity, java_object, notes, id_assignment_mode, sequence_name, master_db, report_group, page, renumbering_required, seq_id, object_type, handling_dev2, history,  
                             generate_id_trigger, shape_color, shape_figure, shape_group)  
VALUES (2500, 'S_RESCHEDULE_REASONS', 1, 2, 'S_RESCHEDULE_REASONS', 'S_RESCHEDULE_REASONS', 20, 'SRescheduleReason', 'reasons for reschedule', 'manuell', NULL, 'DEV', NULL, NULL, 0, NULL, 'FKO', 'stay', 0, 1, 'White', 'Database', NULL);  
  
CREATE TABLE s_reschedule_reasons  
(  
    id                BIGINT               NOT NULL  
        PRIMARY KEY,  
    reschedule_reason VARCHAR(400)         NOT NULL,  
    external_ref      VARCHAR(400),  
    entity            BIGINT  DEFAULT 2500 NOT NULL  
        CONSTRAINT s_reschedule_reasons_entity_check  
            CHECK (entity = 2500),  
    status            BIGINT  DEFAULT 1    NOT NULL,  
    description       VARCHAR(400),  
    client            BIGINT  
        REFERENCES k_clients (id)  
            DEFERRABLE INITIALLY DEFERRED,  
    restrict_customer INTEGER DEFAULT 0  
);  
  
ALTER TABLE s_reschedule_reasons  
    OWNER TO aax2;  
  
CREATE INDEX s_reschedule_reasons_client_idx  
    ON s_reschedule_reasons (client);  
  
-- 增加reschedule的reason code  
INSERT INTO aax2.s_reschedule_reasons (id, reschedule_reason, external_ref, entity, status, description, client, restrict_customer)  
VALUES (1, 'Customer Request - Reschedule', NULL, 2500, 1, 'Customer is no longer available at the original time', NULL, 0);  
INSERT INTO aax2.s_reschedule_reasons (id, reschedule_reason, external_ref, entity, status, description, client, restrict_customer)  
VALUES (2, 'Customer Error - Contact Info', NULL, 2500, 1, 'Customer provided an incorrect or inactive phone number', NULL, 0);  
INSERT INTO aax2.s_reschedule_reasons (id, reschedule_reason, external_ref, entity, status, description, client, restrict_customer)  
VALUES (3, 'Already In Transit', NULL, 2500, 1, 'Technician is on the way. Rescheduling is no longer possible', NULL, 0);  
INSERT INTO aax2.s_reschedule_reasons (id, reschedule_reason, external_ref, entity, status, description, client, restrict_customer)  
VALUES (4, 'Change Not Required', NULL, 2500, 1, 'Customer changed mind. No updates made.', NULL, 0);  
  
  
INSERT INTO aax2.s_relationships (relationship, id_p, id_c, end_dt, duplicate_with, notes, status, entity, role, last_user, tariff, campaign, workflow_setup, workflow_terminate, service_parent, sort_order, customer_process, charge_product_change, filter,  
                                  product_change_time_constraint, element_value, max_qty, description, client, even_uneven, external_id, range_from, range_to, min_qty, duration, fixed_quantity)  
VALUES (150, 13, 224, NULL, NULL, NULL, 1, 333, NULL, 99, NULL, NULL, NULL, NULL, NULL, 1, NULL, NULL, NULL, NULL, NULL, NULL, NULL, 45, NULL, NULL, NULL, NULL, NULL, NULL, NULL);
```

#service_ticket 