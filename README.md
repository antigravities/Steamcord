# Steamcord

I'm releasing this because other people have found it neat and have asked me to.

## So:
* Don't ask me questions about this.
* I'm not helping you set this up.
* You're free to make feature requests, but I'm also free to not consider them.

## Setup
```
npm install
cp settings.json.example settings.json
$EDITOR settings.json
node index.js
```

### For clarification:
* Webhook URLs look like this: ``https://discordapp.com/api/webhooks/hookid/hooksecret``
* You need to create a new Discord server and add a bot to it. It needs to have "manage channels" and "webhooks" permissions to work right.
* Enter its secret as `settings.discord.key`.
* `settings.discord.master` is your discord ID.
* `settings.discord.masterGuild` is the ID of the Discord server you made for the bot.

## License
[GPL v3](http://gnu.org/licenses/gpl-3.0) (yeah, that one)