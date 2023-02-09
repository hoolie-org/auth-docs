---
title: "Hoolie Auth"
description: Multi app one click auth platform
hide_table_of_contents: true
---

# Hoolie Auth

There is authentication platform built specially for Hoolie (Alex Congritta's organization) projects. Hoolie auth allows
implement signs in and up via Telegram with easy.

## How it works

You can try Hoolie auth [here](https://demo.auth.hoolie.org).

There is:

- Auth bot (Telegram);
- Auth gateway (REST API);
- Your app backend;
- Your app frontend

You connect them app to Hoolie Auth (contact [@congritta](https://t.me/congritta)).
Every app has it's unique ID and REST API endpoint whereto auth bot sends request after successful authentication.

1. You make your app user to go to link
   like `https://t.me/hoolieAuthBot?start=NjNlNGZmNDhjYjhmNWI4YzYzZGZkYTMzOjgzSi1XMms1TVNncHlIaXJBQUFI`.<br />
   The `NjNlNGZmNDhjYjhmNWI4YzYzZGZkYTMzOjgzSi1XMms1TVNncHlIaXJBQUFI` is your app id and user's socket id base64
   encoded.
2. User follows the link and sends `/start` command to auth bot;
3. The bot gets your app info from database by it's ID and sends user's ID to your app by it's API endpoint;
4. Your API sends user's ID to Hoolie Auth gateway to get user data (or verify it);
5. You send user data to your app frontend via WebSocket

After this, you can add additional data about user in your app backend if you need. If you need to update user data from
bot, make user to perform authentication again
