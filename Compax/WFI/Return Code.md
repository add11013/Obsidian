![[Pasted image 20260901153007.png]]

定義這個WFI有那些return code


## 如果WFI是subsystem在data selection裡面會有workflowitemClose
![[Pasted image 20260901175915.png]]
workflowitemClose中
targetFields代表會把外部的'status'欄位值，放到returnCode給當下的WFI
也就是說，設定的return code要跟外部傳進來status一樣


## 如果WFI是java code可以在裡面翻到
```java
return WorkflowItemServiceResult.ok("No device found");

return WorkflowItemServiceResult.builder().returnCodeRef(ReturnCodes.WaitSubWorkflow.getReturnCodeRef()).message("Create swap subworklfow for " + subWFs.stream().map(wf -> wf.getId().toString()).collect(Collectors.joining(","))).build();
```
