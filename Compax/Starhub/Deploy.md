
## COIN
[https://coin-gui.int.compax.at/projects/rp/tasks](https://coin-gui.int.compax.at/projects/rp/tasks "https://coin-gui.int.compax.at/projects/rp/tasks")

create new task
Task: post actions pipeline
branch: trunk
configuration: AAX2
action: deploy-shintta-k8s


## 環境說明

### Compax maintain
SHINT, SHINT2, SHINTTA, SHINTTA2環境都是吃code: trunk branch 和db: rpdev
可用COIN上版

### SH maintain
ADUAT(TRN), HFD(STAGING)都是吃code: SHPRE branch和db:shpre
必須用COIN包版完，請SH人員幫忙上版

## 上版流程
頻道會說有`trunk release`也就是上production，標記日期為production上版日
code會在trunk release前幾個禮拜，從trunk branch到SHPRE branch
DB config會從rpdev或konf(看table主表是根據哪一個) 同步到SHPRE環境

在production上版前，不會再有trunk -> SHPRE
如果需要上版到UAT/HFD，必須通知SH
頻道也會有通知`patch release`，並且有發車日期
所以
* 所有的DB config必須在SHPRE改動
* 所有的code change必須改動到SHPRE
* 透過COIN包版，請SH人員幫忙上版到UAT/HFD

在要上production前會從SHPRE切出一個STABLE

版號b結尾為stable