# Telegram Bot Playground

![ci](https://github.com/catsoap/tg-bot-playground/workflows/ci/badge.svg)

Play project to interact with a Telegram Bot

## Requirements

You need to have the following tools installed:

- nvm (or please see `.nvmrc` for node version)
- firebase-tools (`npm install -g firebase-tools`)
- a bot see [official doc](https://core.telegram.org/bots#creating-a-new-bot)
- curl and jq (optional for some make targets)

## How it works?

A **Makefile** provides some shortcuts to help you. Just run

```bash
$ make
```

to see a help menu.

## Functions Dev

Install dependencies with `make install`

You need to login to firebase to be able to run functions locally.

To launch the functions, run `make run`.  
A watcher is also available, just run `make run-watch`.

Then to make your local webhook is reachable by Telegram, you need to expose your
localhost.  
You can use a free service for this: [localhost.run](http://localhost.run/),
there is no tool to install, just use SSH like this:

```bash
ssh -R 80:localhost:5001 ssh.localhost.run
```

Some Makefile targets have been made to ease interacting with Telegram.  
To be able to use them, fill-in your dev bot token in the `.env` file.

You can set the webhook on your bot like this: (given you filled-in the **BOT_TOKEN** variable in `.env`)

```bash
make tg-webhook URL=https://xxx-yyy.localhost.run/tgbotplayground/us-central1/webhook
```

## Useful links

https://firebase.google.com/docs/functions/config-env  
https://firebase.google.com/docs/functions/local-emulator  
https://firebase.google.com/docs/functions/unit-testing#testing_http_functions  
https://firebase.google.com/docs/reference/admin/node/admin.firestore  
https://medium.com/swlh/testing-guide-for-cloud-firestore-functions-and-security-rules-39d9f3c92d99  
https://medium.com/@moki298/test-your-firebase-cloud-functions-locally-using-cloud-functions-shell-32c821f8a5ce  
https://core.telegram.org/bots/webhooks  
https://core.telegram.org/bots/api
