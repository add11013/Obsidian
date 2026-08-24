在compax系統裡
一個user可以有很多個role
一個role可以有很多個function

因為我們沒有role group的概念
假設：
有一個A role，一個B role
C role要同時擁有A role + B role的功能
系統無法辦到

AAX4有個邏輯
會寫成
A (reference)
B (reference)

C的敘述裡面就會是A (reference) + B (reference)
當A有新function時，必須手動加入A role
並找出有A (reference)的role，同時加入function
SQL可以參考 [[Add user function and role]]

#aax4 #role #function 