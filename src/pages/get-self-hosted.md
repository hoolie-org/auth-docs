---
title: "Get self hosted"
description: Get Hoolie Auth self hosted
hide_table_of_contents: true
---

# Get self hosted

You can run Hoolie auth in your server.

Hoolie Auth is written in NodeJS and uses MongoDB and Redis to store data. Also install yarn.

## Run auth gateway

Auth gateway is small REST API to get user info saved by bot by user's ID.

1. Clone this repo: https://github.com/hoolie-org/auth-gateway;
2. Copy _src/config.example.ts_ to _src/config.ts_ and fill it as you (want|need);
3. Provide reversed proxy to this running HTTP Server. You can use Nginx reverse proxy

## Run auth bot

1. Clone this repo: https://github.com/hoolie-org/auth-bot;
2. Copy _src/config.example.ts_ to _src/config.ts_ and fill it as you (want|need);

Also bot saves users avatars to your server file system. Make a static HTTP server for get available to downloading user
avatars.<br />
Also you can do not this. Read avatars from file system directly by your app backend

---

To connect your app see [here](./connect-your-app)
