
## Description
新增user可用的function
綁定role和function

## Script
``` sql
-- 增加function  
INSERT INTO aax2.u_functions (id, function, description, status, entity, image, is_new, parent, client, aax_version)  
 VALUES (26050600, 'reports', 'reports for AAX4', 1, 39, null, 4, null, null, 4);  
  
-- 設定function給role  
INSERT INTO aax2.u_functions_2_roles (role, function, status, entity) VALUES (1, 26050600, 1, 40);  
INSERT INTO aax2.u_functions_2_roles (role, function, status, entity) VALUES (99, 26050600, 1, 40);  
INSERT INTO aax2.u_functions_2_roles (role, function, status, entity) VALUES (127, 26050600, 1, 40);  
  
-- 增加function  
INSERT INTO aax2.u_functions (id, function, description, status, entity, image, is_new, parent, client, aax_version)  
VALUES (26050601, 'downloadReport', 'download reports for AAX4', 1, 39, null, 4, null, null, 4);  
  
-- 設定function給role  
INSERT INTO aax2.u_functions_2_roles (role, function, status, entity) VALUES (1, 26050601, 1, 40);  
INSERT INTO aax2.u_functions_2_roles (role, function, status, entity) VALUES (99, 26050601, 1, 40);  
INSERT INTO aax2.u_functions_2_roles (role, function, status, entity) VALUES (127, 26050601, 1, 40);  
  
-- 增加function  
INSERT INTO aax2.u_functions (id, function, description, status, entity, image, is_new, parent, client, aax_version)  
VALUES (26050602, 'scheduleReport', 'schedule reports for AAX4', 1, 39, null, 4, null, null, 4);  
  
-- 設定function給role  
INSERT INTO aax2.u_functions_2_roles (role, function, status, entity) VALUES (1, 26050602, 1, 40);  
INSERT INTO aax2.u_functions_2_roles (role, function, status, entity) VALUES (99, 26050602, 1, 40);  
INSERT INTO aax2.u_functions_2_roles (role, function, status, entity) VALUES (127, 26050602, 1, 40);
```

#function #role