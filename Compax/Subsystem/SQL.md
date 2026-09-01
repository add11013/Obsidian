``` sql
-- 某一個subsystem的object
SELECT * FROM if_transaction_objects WHERE id = 1378;

-- 跟這個subsystem有關的
SELECT * FROM if_transaction_objects_types WHERE object = 1378;


SELECT * FROM d_workflowitems WHERE id = '1839562002'
SELECT * FROM if_transactions WHERE id = 1886193450;  
SELECT * FROM if_transactions_data_resp where tran_id_ref = 1886193450;
```