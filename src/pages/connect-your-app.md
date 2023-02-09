---
title: "Connect your App"
description: How to connect your app to Hoolie Auth
---

# Connect your app to Hoolie Auth

You can connect your app to Hoolie AUTH main node or [host it by yourself](get-self-hosted)

## Register your app

Contact [@congritta](https://t.me/congritta) to register your app in Hoolie Auth.
App are being moderated manually because initially Hoolie Auth is made only for Hoolie projects. We are not ready to
support many apps

## Make your app frontend to use web sockets

Make your app frontend and backend connected to each other using web sockets

## Make endpoint in your app REST API

It should be available to receive HTTP POST requests with user ID and web socket ID as request body parameters.
See [this file](https://github.com/hoolie-org/auth-demo-app-backend/blob/master/src/handlers/onProvideAuth.ts) or
contact [@congritta](https://t.me/congritta)
if you have questions.

You can get user's data by `https://auth.hoolie.org/getUser?userId=<user id>`.<br />
For example: https://auth.hoolie.org/getUser?userId=63e4f30fd354357204054052

If all is good, send user data (or what your want) via web socket to your app frontend

## Make a button (or link) in your app frontend

Link should be like this:<br />
`https://t.me/hoolieAuthBot?start=NjNlNGZmNDhjYjhmNWI4YzYzZGZkYTMzOjgzSi1XMms1TVNncHlIaXJBQUFI`

You can make this link using script below:

```javascript
const appId = ''; // Given by Alex Congritta;
const socketId = ''; // Socket ID. Read your web socket librery documentation to learn how to get socket id;
const authBotUsername = 'hoolieAuthBot';

const link = `https://t.me/${authBotUsername}?start=${btoa(`${appId}:${socketId}`)}`;
```

## To get user avatar from Telegram:

You can get user avatar by: https://avatars.auth.hoolie.org/5854364204.jpg where `5854364204` is user's Telegram ID

---

If you did good, it should work
