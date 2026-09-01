![[Pasted image 20260901153104.png]]

用來設定
Outgoing (決定下一個WFI要去哪)
Incoming (顯示哪些WFI在什麼情況會進這個WFI)

Puts in the queue: 直接放進去queue代表直接進行 target WFI
Makes obsolete: 刪除target WFI (通常是前面WFI放進去queue的)
Rollback on completion: 當前WFI跑完後，會rollback target WFI，讓他下次可以繼續跑 [[Waiting item]]
Provides for input of external system: 當前會停住，等外面的request進來