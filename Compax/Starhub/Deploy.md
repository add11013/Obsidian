
## COIN
[https://coin-gui.int.compax.at/projects/rp/tasks](https://coin-gui.int.compax.at/projects/rp/tasks "https://coin-gui.int.compax.at/projects/rp/tasks")

create new task
Task: post actions pipeline
branch: trunk
configuration: AAX2
action: deploy-shintta-k8s


## 環境說明

頻道會說有"trunk release"，標記日期為production上版日
code會在trunk release前幾個禮拜，從trunk branch -> SHPRE branch
DB config會從rpdev或konf(看table主表是根據哪一個) 同步到SHPRE環境

在第一次trunk -> SHPRE後，直到下次production上版，都不會有trunk -> SHPRE
所以所有的code change和