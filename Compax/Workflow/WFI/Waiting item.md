![[Pasted image 20260825175357.png]]

Provides for input of external system是在等外部系統的input
所以要等到收到後才會觸發outgoing WFI
以這例子為例，條件符合NotResolvedYet，會rollback 3196然後繼續開著3196等
然後無條件觸發7860

當第二次進來這個3196 WFI，如果沒有Rollback on completion
系統不會執行7860，因為他會覺得這個WFI的status是Completed
