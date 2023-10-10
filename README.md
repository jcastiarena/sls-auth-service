# Serverless Authorization Service

This service is part of a system to place bids on auctions for selling online books. It uses the serverless framework and various AWS services including DynamoDB, SQS, SES and S3. Its responsibility is to authenticate requests that want to use the auction-service.

## Install

```
git clone git@github.com:jcastiarena/sls-auth-service.git
cd sls-auth-service
npm i
sls deploy --verbose
```

## Usage

```
curl --location 'https://YOUR_AUTH0_APP_DOMAIN.auth0.com/oauth/token' \
--header 'Content-Type: application/x-www-form-urlencoded' \
--header 'Cookie: __cf_bm=SPJBSWa_RHbKz8HVcQrrq0wUCs8w5cAhbyKzzy70bzI-1696423712-0-AWQNM3gdoniSANF1/nReroqyuMLwJ8Efqd6w0ms3L3xqKIz7yzMy7pTmSahI1vzyq/YktyXu1Qr6qrfn15j31AY=; did=s%3Av0%3A97b72bb0-50e9-11ee-84c1-b9f908d5cd92.shUo401vvu%2FolhOhbICzdjyXp0pOxAFBDAIRAMClcG8; did_compat=s%3Av0%3A97b72bb0-50e9-11ee-84c1-b9f908d5cd92.shUo401vvu%2FolhOhbICzdjyXp0pOxAFBDAIRAMClcG8' \
--data-urlencode 'client_id=YOUR_CLIENT_ID' \
--data-urlencode 'username=YOUR_USERNAME' \
--data-urlencode 'password=YOUR_PASSWORD' \
--data-urlencode 'grant_type=password' \
--data-urlencode 'scope=openid'
```
And save the TOKEN_ID obtained in the response.

Work based on @arielweinberger's course