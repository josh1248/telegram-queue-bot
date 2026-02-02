# nusc-queue-bot
Implements a Telegram bot for small to medium-scale events that involve queueing, such as for photobooths. Meant for NUSC events, but can be used in any other queue setting.

Upstream inspiration: This is a fork and used the following deprecated queue bot written in Python for NUSC's predecessor:
https://github.com/kwokyto/usp-queue-bot

(Note: The queuebot is in the processing of being ported over to a native Telegram mini app at https://github.com/josh1248/nusc-queuebot-miniapp - no more feature commits will be made.) 

# how to set up

## Clone this repo

## Register Your Bot on Telegram
*Accurate as of Apr 2024*
https://core.telegram.org/bots/tutorial
- Find @BotFather through Telegram global search
- Set up a bot with a desired name
- Obtain your top-secret API key from BotFather to control your bot by
- Test that you have established a link to your bot using this link, replacing "YOUR_BOT_TOKEN" with the API key
`https://api.telegram.org/bot<YOUR_BOT_TOKEN>/getMe`
- If you are un-successful, you will receive a 404 response. Check that you have entered the correct bot API token provided by BotFather, which should be in the form "XXXXX:YYYY", where X are numbers only and Y are alphanumeric.
  
    ![404 reponse!](./images/setup_unsuccessfulAPItoken.png)

- If you are successful, you will receive an OK response with some basic information about your bot in JSON.
  
    ![200 OK reponse!](./images/setup_successfulAPItoken.png)

- :warning: **Important:** Duplicate the .envSETUP key in this folder. Rename this file to ".env", and place in your API token after "BOT_TOKEN". This ".env" file is ignored (by Git) and not committed to GitHub to keep your API secret. (Don't pass this key around, or else people can control your bot!)

## Local deployment - Install Go and Postgres

Install the Go parser at https://go.dev/doc/install
Install a relatively up-to-date PostgreSQL runner at https://www.postgresql.org/download/windows/. For Mac users, I use https://postgresapp.com/, which may be considered.
Within your coding environment (e.g. VSCode), run `go run cmd/server/main.go`. If any errors result, do check that you have updated your `.env` file appropriately (instructions above), that you have Postgres running, and that your bot token is valid.

This app was built in consideration of use in context of a cloud provider. However, if you trust the reliability of your gadgets, feel free to run this on an internet-connected Raspberry or something
as long as it listens and polls to the telegram-provided endpoint!

## Remote deployment - Railway

I have chosen Railway as my cloud provider because of ease of connecting with preset postgres containers. If you wish to use this method, take note that the `.env` file variables will need to be separately injected since the secrets are of course not present in the public github repo code.

Extra setup required for less friendly main providers like AWS EC2 / Google Cloud run, which I would not claim to be proficient in for now.


# running the server (local)
Cook your computer and keep it running

# running the server (remote)
Heroku or AWS or other services? not sure yet.
