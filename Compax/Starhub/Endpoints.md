**Network and common used endpoints**

1. Check if you have set up WireGraud  
2. 
    [Setup for WireGuard Proxy Connection](https://confluence.compax.at/pages/viewpage.action?pageId=143127861)


    Check if you have installed SmartProxy in your browser(Chrome, Firefox) [SmartProxy Installation](https://confluence.compax.at/display/SH/Chrome%2C+Firefox)
    

we are using AD UAT (AKA TRN) and HFD (AKA Staging) envs on AWS for testing.  
**AD UAT common used endpoint**:  
[GUI](https://gui.compax-trn.starhubsg.sh.inc/aax3/login.jsf)  
[frontend-api-v2](https://api.compax-trn.starhubsg.sh.inc/frontend-api-v2/swagger-ui/index.html?configUrl=/frontend-api-v2/api-docs/swagger-config#/)  
[shop-webservice](https://api.compax-trn.starhubsg.sh.inc/shop-webservice-v3/swagger-ui/index.html?configUrl=/shop-webservice-v3/api-docs/swagger-config#/)  
[auth server](https://auth.compax-trn.starhubsg.sh.inc/auth-server/swagger-ui/index.html)

**HFD common used endpoint**:  
[GUI](https://gui.compax-staging.aws.starhubsg.sh.inc/aax3/login.jsf)  
[frontend-api-v2](https://api.compax-staging.aws.starhubsg.sh.inc/frontend-api-v2/swagger-ui/index.html?configUrl=/frontend-api-v2/api-docs/swagger-config#/)  
[shop-webservice-v3](https://api.compax-staging.aws.starhubsg.sh.inc/shop-webservice-v3/swagger-ui/index.html?configUrl=/shop-webservice-v3/api-docs/swagger-config#/)  
[auth server](https://auth.compax-staging.aws.starhubsg.sh.inc/auth-server/swagger-ui/index.html)

Refence:  
[https://confluence.compax.at/pages/viewpage.action?pageId=143106106](https://confluence.compax.at/pages/viewpage.action?pageId=143106106)

**DB info**  
AD UAT:

- database: dbcompaxtraining1
- End Point: [db-compax-training1.ckerncv2jdvw.ap-southeast-1.rds.amazonaws.com](http://db-compax-training1.ckerncv2jdvw.ap-southeast-1.rds.amazonaws.com)
- Port: 5432
- Username: postgrestrain
- Password : CompaxTrainingPo$tGresSql

HFD:

- Database: dbcompaxstaging
- Endpoint: [db-compax-staging.ckerncv2jdvw.ap-southeast-1.rds.amazonaws.com](http://db-compax-staging.ckerncv2jdvw.ap-southeast-1.rds.amazonaws.com)
- Port: 5432
- UserName: postgres 
- Password: CompaxStagingPo$tGres

Reference: [https://confluence.compax.at/display/SH/Compax_RDS_Details](https://confluence.compax.at/display/SH/Compax_RDS_Details)

You also need to set proxy for DB connection, can refer the following pages for your DB tool  
[DBeaver](https://confluence.compax.at/display/SH/DBeaver)  
[IntelliJ - DataGrip](https://confluence.compax.at/display/SH/IntelliJ+-+DataGrip)

For Compax internal testing, I suggest using [shint2](https://shint2.int.compax.at/) which is more faster in Asia

SHINT2 DB:

- database: shint2
- End Point: [postgres-dev.tpe.int.compax.at](http://postgres-dev.tpe.int.compax.at)
- port: 5433
- Username: aax2sh
- Password : aax2sh

