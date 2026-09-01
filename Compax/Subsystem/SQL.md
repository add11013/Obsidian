``` sql
-- 某一個subsystem的object
SELECT * FROM if_transaction_objects WHERE id = 1378;

-- 跟這個subsystem有關的
SELECT * FROM if_transaction_objects_types WHERE object = 1378;
```