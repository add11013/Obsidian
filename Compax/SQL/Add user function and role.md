
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




AAX4有個邏輯
舉例`select * from u_roles where role = 'AAX4 team Viewer (reference)';`
有(reference)代表他是基本款

然後他更上面的role可以找
```sql
select * from u_roles where description like '%AAX4 team Viewer (reference)%';
-- 會找到像是
-- role = 'OS Outbound Agents'
-- description = 'AAX4 team Viewer (reference) + Service support AAX4 team member (reference) + SH Ops Team AAX4 (reference) + Livechat Agent AAX4 (reference)')
```

因為`AAX4 team Viewer (reference)`是基本，所以更新`AAX4 team Viewer (reference)`的function，要連他上面的role都更新

可以用下面的SQL
```sql
INSERT INTO u_functions_2_roles (entity, "function", "role", status)  
SELECT DISTINCT 40, 170296, ufr."role", 1  
FROM u_functions_2_roles ufr  
WHERE (ufr."role" IN (SELECT id FROM u_roles WHERE description LIKE '%AAX4 team Viewer (reference)%')  
    OR  
       ufr."role" IN (SELECT id FROM u_roles WHERE role = 'AAX4 team Viewer (reference)'))  
  AND NOT EXISTS (SELECT 1 FROM u_functions_2_roles x WHERE x."role" = ufr."role" AND x."function" = 170296);
```
#aax4