# TSUBASA RIVALZ BOT

## BOT FEATURE

- Multi Account With Proxy Support
- Support Telegram Sessions and Telegram Query (Query May Expired)
- Auto Tap
- Auto Complete Some Missions
- Auto Upgrade Random Card
- Auto Upgrade Booster

## Setup & Configure BOT

### Linux & MAC OS

1. clone project repo
   ```
   git clone https://github.com/vinskasenda/tsubasa-rivalz-bot.git
   ```
   and cd to project dir
   ```
   cd tsubasa-rivalz-bot
   ```
2. Run
   ```
   npm install
   ```
3. Run
   ```
   npm i telegram@2.22.2
   ```
4. Run
   ```
   mkdir -p accounts
   ```
5. Run
   ```
   cp config/config_tmp.js config/config.js && cp config/proxy_list_tmp.js config/proxy_list.js
   ```
6. (If You Use Telegram Sessions) To configure the app, run
   ```
   nano config/config.js
   ```
   and add your telegram app id and hash there.
7. (If You Use Proxy) To configure the app, run
   ```
   nano config/proxy_list.js
   ```
   and add your proxy list there, use http proxy
8. to start the app run
   ```
   npm run start
   ```
9. if any error regarding `config.js` not found, or `proxy_list.js` not found, try to copy `config` folder to `app` folder. make sure you have those file inside `config` folder.

## Setup Accounts

1. Run bot `npm run start`
2. Choose option `1` to create account
3. Choose account type `Query` or `Sessions`
4. `Session` Type
   1. Enter Account Name
   2. Enter your phone number starting with countrycode ex : `+628xxxxxxxx`
   3. You will be asked for verification code and password (if any)
   4. Start The bot Again after account creation complete
5. `Query` Type
   1. Enter Account Name
   2. Enter Telegram Query (you can get query by opening bot app on browser > inspect element > storage / application > session storage > telegram init params > copy tg web app data value)
   3. Start The bot Again after account creation complete
6. after bot started choose option 3 start bot

## Session Troubleshoot

If you asked to enter phone number again after sessions creation, it mean session not initialized correctly, try to delete the created sessions.

Example Case

- example you already have 1 session (sessionA) and all good when you run bot. After that you create another session, but when you run bot, the bot asked to enter phone number again, so the problem is on (sessionB), to fix it just remove the `accounts/sessionB` folder and re create it or just delete all folder inside `accounts` directory with prefix `sessions-`.

## Query Troubleshoot

if your bot get eror, with some error code `401` it mean your query expired, go get new query and run bot again and choose option `4` for query modification.

## Note

Config files is adjustable, modify the `config/config.js`, there some adjustable parameter 
```js
static USEAUTOUPGRADEBOOST = true; //USE AUTO UPGRADE OR NO (DEFAULT TRUE)
static USEAUTOTAP = true; //USE AUTO TAP OR NO (DEFAULT TRUE)
static USEAUTOCOMPLETEMISSIONS = true; //USE AUTO COMPLETE MISSIONS OR NO (DEFAULT TRUE)
static USEAUTOLEVELUPRANDOMCARD = true; //USE AUTO LEVELUP RANDOM CARD OR NO (DEFAULT TRUE)
static CUSTOMDELAY = undefined; //CUSTOM DELAY AFTER EXECUTION IN SECOND EX : 60 MEANS 60 SECONDS (DEFAULT DYNAMIC TIME + DELAY RANDOM)
```

Don't use bot with `session` type if you using telegram account that bought from someone because it can make your telegram account deleted. instead of using `session` type, use `query` type.

This bot can use Telegram Query and Telegram Sessions. if you want to use sessions, and ever use one of my bot that use telegram sessions, you can just copy the `accounts` folder to this bot. Also for the telegram APP ID and Hash you can use it from another bot. If you want to use Telegram Query, get your query manually.

if you got error `Invalid ConstructorId` try to run this `npm i telegram@2.22.2`