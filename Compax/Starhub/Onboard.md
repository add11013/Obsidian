# StarHub Development Environment Setup

## Network Setup

Before accessing internal environments, make sure the following are configured:

1. **WireGuard**
   - Setup Guide: https://confluence.compax.at/pages/viewpage.action?pageId=143127861

2. **SmartProxy** (Chrome / Firefox)
   - Installation Guide: https://confluence.compax.at/display/SH/Chrome%2C+Firefox

---

# Environment Endpoints

We mainly use the following AWS environments for testing:

- **AD UAT** (TRN)
- **HFD** (Staging)

## AD UAT (TRN)

| Service            | URL                                                                                                                                      |
| ------------------ | ---------------------------------------------------------------------------------------------------------------------------------------- |
| GUI                | https://gui.compax-trn.starhubsg.sh.inc/aax3/login.jsf                                                                                   |
| frontend-api-v2    | https://api.compax-trn.starhubsg.sh.inc/frontend-api-v2/swagger-ui/index.html?configUrl=/frontend-api-v2/api-docs/swagger-config#/       |
| shop-webservice-v3 | https://api.compax-trn.starhubsg.sh.inc/shop-webservice-v3/swagger-ui/index.html?configUrl=/shop-webservice-v3/api-docs/swagger-config#/ |
| Auth Server        | https://auth.compax-trn.starhubsg.sh.inc/auth-server/swagger-ui/index.html                                                               |

---

## HFD (Staging)

| Service | URL |
|---------|-----|
| GUI | https://gui.compax-staging.aws.starhubsg.sh.inc/aax3/login.jsf |
| frontend-api-v2 | https://api.compax-staging.aws.starhubsg.sh.inc/frontend-api-v2/swagger-ui/index.html?configUrl=/frontend-api-v2/api-docs/swagger-config#/ |
| shop-webservice-v3 | https://api.compax-staging.aws.starhubsg.sh.inc/shop-webservice-v3/swagger-ui/index.html?configUrl=/shop-webservice-v3/api-docs/swagger-config#/ |
| Auth Server | https://auth.compax-staging.aws.starhubsg.sh.inc/auth-server/swagger-ui/index.html |

---

## References

- Environment Documentation  
  https://confluence.compax.at/pages/viewpage.action?pageId=143106106

---

# Database Information

## AD UAT (TRN)

| Item | Value |
|------|-------|
| Database | `dbcompaxtraining1` |
| Endpoint | `db-compax-training1.ckerncv2jdvw.ap-southeast-1.rds.amazonaws.com` |
| Port | `5432` |
| Username | `postgrestrain` |
| Password | `CompaxTrainingPo$tGresSql` |

---

## HFD (Staging)

| Item | Value |
|------|-------|
| Database | `dbcompaxstaging` |
| Endpoint | `db-compax-staging.ckerncv2jdvw.ap-southeast-1.rds.amazonaws.com` |
| Port | `5432` |
| Username | `postgres` |
| Password | `CompaxStagingPo$tGres` |

---

## Database References

- RDS Details  
  https://confluence.compax.at/display/SH/Compax_RDS_Details

### Proxy Configuration for Database Tools

DB connections require proxy configuration.

- DBeaver  
  https://confluence.compax.at/display/SH/DBeaver

- IntelliJ / DataGrip  
  https://confluence.compax.at/display/SH/IntelliJ+-+DataGrip

---

# Internal Testing Database (Recommended)

For Compax internal testing, **SHINT2** is recommended because it provides better performance for users in Asia.

Website:

https://shint2.int.compax.at/

## SHINT2 Database

| Item | Value |
|------|-------|
| Database | `shint2` |
| Endpoint | `postgres-dev.tpe.int.compax.at` |
| Port | `5433` |
| Username | `aax2sh` |
| Password | `aax2sh` |