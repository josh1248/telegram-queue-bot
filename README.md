# nusc-queue-bot
Implements a Telegram bot for small to medium-scale events that involve queueing, such as for photobooths. Meant for NUSC events, but can be used in any other queue setting.

Inspired by deprecated queue bot counterparts written in Python here:
https://github.com/kwokyto/usp-queue-bot

(Note: The queuebot is in the processing of being ported over to a native Telegram mini app at https://github.com/josh1248/nusc-queuebot-miniapp - no more feature commits will be made.) 

# how to set up

## :warning: A cautionary note 
- Local server setup in this repo will require your API keys and passwords to be placed within a .env file. Unless you modify this code to use secret manager applications instead (or other means), you should not locally host this bot if your computer is shared!.
- This is obviously a hobby project with ssl-mode off and no passwords required - security is not considered since my database storage is low-value.

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

## Local deployment - Install Go (what version) and Postgres (what version)

Install the Go parser at https://go.dev/doc/install
Install a relatively up-to-date PostgreSQL runner at https://www.postgresql.org/download/windows/. For Mac users, I use https://postgresapp.com/, which may be considered.
Within your coding environment (e.g. VSCode), run `go run cmd/server/main.go`. If any errors result, do check that you have updated your `.env` file appropriately (instructions above), that you have Postgres running, and that your bot token is valid.

## Remote deployment - Heroku


# running the server (local)
Cook your computer and keep it running

# running the server (remote)
Heroku or AWS or other services? not sure yet.
