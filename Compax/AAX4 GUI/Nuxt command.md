
put .env.dev
``` Dotenv
# Backend API Configuration

NUXT_BE_API_DOMAIN=https://rpdev-api.dev-vie.int.compax.at/backend-api

#NUXT_BE_API_DOMAIN=http://localhost:8080/backend-api

NUXT_BE_WS_API_DOMAIN=https://rpdev-api.dev-vie.int.compax.at/contactcenter-ws

  

# Authentication (OAuth2) - Full Configuration

NEXTAUTH_SECRET=aax4

AUTH_ORIGIN=http://localhost:3883/api/auth

NUXT_AUTH_SERVER_V2_TOKEN_URL=https://rpdev-api.dev-vie.int.compax.at/auth-server-v2/oauth2/token

NUXT_AUTH_SERVER_V2_WELL_KNOWN_URL=https://rpdev-api.dev-vie.int.compax.at/auth-server-v2/.well-known/openid-configuration

NUXT_AUTH_SERVER_V2_CLIENT_ID=aax4

NUXT_AUTH_SERVER_V2_CLIENT_SECRET=aax4

NUXT_AUTH_SERVER_V2_USER_INFO_URL=https://rpdev-api.dev-vie.int.compax.at/auth-server-v2/oauth2/userinfo

NUXT_AUTH_SERVER_V2_AUTHORIZE_URL=https://rpdev-api.dev-vie.int.compax.at/auth-server-v2/oauth2/authorize

NUXT_AUTH_SERVER_V2_URL=https://rpdev-api.dev-vie.int.compax.at/auth-server-v2

  

# Logging

NUXT_WRITE_LOG_FILE=false

  

# Server Configuration

PORT=3883

# NUXT_APP_BASE_URL=/aax4/

  

# Observability (OpenTelemetry)

OTEL_EXPORTER_OTLP_ENDPOINT=http://mon-opentelemetry-collector.monitoring:4317

  

# SIP/VoIP Configuration (for call center features)

NUXT_SIP_DOMAIN=vxi01.tb29.int.i-new.com

NUXT_SIP_USER_PREFIX=ccv_agent_

NUXT_SIP_SERVER=wss://vxi01.tb29.int.i-new.com:8089/ws

  

# AI Agent

NUXT_AI_AGENT_DOMAIN=http://localhost:1234/ai-assistant/api
```


Run dev locally
``` shell
#switch to package/aax4-sh
yarn install
yarn run dev
```

Run server locally
``` shell
yarn build
yarn start --dotenv .env.dev
```
