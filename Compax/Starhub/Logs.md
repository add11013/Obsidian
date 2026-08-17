
網址
https://starhub.splunkcloud.com/en-US/account/login?loginType=Splunk%20%5bstarhub.splunkcloud.com

語法

production
```
index="ra_cbgitx" k8s.namespace.name="compax-prod" k8s.container.name="aax-shop-webservice-v3" "your log messages"
```
```
index="ra_cbgitx" k8s.namespace.name="compax-prod" k8s.container.name="aax-sh-webservice"
```


non-prod
```
index="aax_non_prod" k8s.cluster.name="cbg_eks_aax_trn"  NOT WARN NOT otel.javaagent k8s.container.name="aax-starhub-utility-cron-jobs" ERROR

index="aax_non_prod" k8s.cluster.name="cbg_eks_aax_stg"  NOT WARN NOT otel.javaagent k8s.container.name="aax-starhub-utility-cron-jobs" ERROR
```

#log