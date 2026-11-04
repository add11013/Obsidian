
Compax寫來部署環境用的

問題一
post-actions-pipeline卡住黃色很久時
可以點擊log裡面查看版本
如果版號不一致，並且沒有該版本image，可能會導致要問問看infra
像是圖中trunk deploy-shint 點擊後
下方Running helm upgrade with version 5.757.0a-COIN2679703
和左邊一致，代表版本沒問題
![[Pasted image 20261104160457.png]]


問題二
版本一致還是卡住
```sql
SELECT pid, pg_blocking_pids(pid) AS blocked_by, application_name, state,
       now() - xact_start AS xact_age, left(query, 120) AS query
FROM pg_stat_activity
WHERE cardinality(pg_blocking_pids(pid)) > 0
ORDER BY xact_start;
```

用這個可以查出鎖誰卡誰
然後找到源頭後，看是什麼sql卡住
如果是很長的白癡SELECT
用下面SQL送他下去
`SELECT pg_terminate_backend(3115453);`
