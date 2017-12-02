# Steamcord

> Steam to Discord. Because Steam's social features are genetically inferior.

Steamcord is an in-development Steam to Discord interface which replaces some basic functions of the Steam client, such as messaging, friends list management, notification counts, and key redemption. It is **not** a total client replacement, but offers significant enhancements to the chat experience of Steam.

## Install

### Prerequisites

* [Node.js](https://nodejs.org/)
* A dedicated Discord server created for the bot
  * A webhook URL created on the `#general` text channel in that server
    * **DO NOT** delete or rename the `#general` text channel; this channel is **required** for the bot to run
* A Discord application with associated bot user
  * If you aren't sure how to make one of these, go [here](https://discordapp.com/developers/applications/me)

### Installation

First, invite your bot user to your server by using a bot invite link like this: https://discordapp.com/oauth2/authorize?client_id=INSERT_CLIENT_ID_HERE&scope=bot&permissions=536890384

Replace `INSERT_CLIENT_ID_HERE` with your bot user's client ID.

Next, install the client:

```bash
$ npm install # Install all required dependencies
$ cp settings.json.example settings.json # Create a local config
$ $EDITOR settings.json # Add your config options here
$ node . # Run the client
```

### `settings.json` breakdown

* `steam` - Steam-related configuration options
  * `accountName` - Your Steam account username
  * `password` - Your Steam account password (**NOTE:** You will need to enter your Steam Guard code every time the bot is started. This is a limitation of Steam's 2FA method.)
* `discord` - Discord-related configuration options
  * `key` - Your **bot user** token
  * `hookID` - Your webhook ID (obtained from the webhook URL using the format `https://discordapp.com/api/webhooks/hookID/hookSecret`)
  * `hookSecret` - Your webhook secret
  * `master` - Your Discord ID (obtained by right-clicking on yourself and clicking "Copy ID" (**requires developer mode to be turned on in Appearance**))
  * `masterGuild` - Your dedicated Steamcord server ID (obtained by right-clicking on the server icon on the left)

## Usage

To run Steamcord, just `cd` into wherever you cloned or downloaded Steamcord and run `node .`. This will prompt you for a Steam Guard code if you have that enabled, and start once it's entered.

### Commands

**NOTE:** Commands must be run from the `#general` text channel, not in a chat channel.

* `!p <steamid> <message>` - Begin a conversation with someone
  * If you already have a conversation open with the user you want to talk to, just send a message in the channel with their Steam ID as its name. This command is only for initiating new conversations with users.
* `!f` - Display your friends list
* `!r <steamkey>` - Redeem a Steam CD key
* `!a <steamid>` - Add a user as a friend on Steam
* `!w` - Obtain your Steam Community session cookies
* `!p` - Enable PICS notifications. This will send you new changelists for all apps.
* `!q <appid>` - Enable PICS notifications for `<appid>`. This will send you changelists for apps that are on this list. Persistent across reboots.
* `!o <appid>` - Check if you own `<appid>`.
* `!b [bigpic|mobile|web|none]` - Sets your UI mode (the icon next to your name). Set to "none" to reset. Not persistent across reboots.
* `!l <appid>` - Obtain a free on demand/no cost license for `<appid>`. See [this](https://github.com/DoctorMcKay/node-steam-user#requestfreelicenseappids-callback) for more information.
* `!j <chatid>` - Join a group chat
* `!m <chatid>` - Leave a group chat

## Maintainers

* [antigravities](https://github.com/antigravities)

## Contribute

* Don't ask me questions about this.
* I'm not helping you set this up.
* You're free to make feature requests, but I'm also free to not consider them.

## License

[GPL v3](http://gnu.org/licenses/gpl-3.0) (yeah, that one)
