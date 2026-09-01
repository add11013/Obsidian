``` sql
-- 某一個subsystem的object
SELECT * FROM if_transaction_objects WHERE id = 1378;

-- 跟這個subsystem有關的
SELECT * FROM if_transaction_objects_types WHERE object = 1378;

-- 查出WFI相關的transaction
SELECT itdr.*  
FROM d_workflowitems dw,  
     if_transactions it,  
     if_transactions_data_resp itdr  
WHERE dw.id = it.entity_id  
  AND itdr.tran_id_ref = it.id  
  AND dw.id = '1839562002';
  
  
```