---
title: RCON Discord Giveaway Bot
description: 
published: true
date: 2025-03-24T03:03:16.329Z
tags: 
editor: markdown
dateCreated: 2025-03-24T02:55:47.964Z
---

# RCON Discord Giveaway Bot

This bot is bound to blow your mind. The first of its kind, giveaways can now be automated through this Discord bot!

You are probably asking yourself, how? Well, the process is simple.

1. You connect your server to the bot via RCON
2. Your players link their steam and discord accounts via Steamcord
3. Your players just start playing and they get tickets for playing! No more plugin running on the server with a timer, taking up valuable resources!
4. Define the giveaways with in the bot, and set how often they run.
5. Players then enter tickets into the giveaway
6. Giveaway ends automatically, however this time, the player can then type /claim in discord and it will run a raw RCON command to that server.

Sounds pretty good right? No more manually giving out VIP packages or Skill Tree XP or Economy Cash.

## Definition of Directories

This bot is big and complex. So I'm going to break down the directory structure for you so that you can ignore some things while focusing on others.

The following directories have files in them that need configured:

```
./configs
./giveaways
./servers
```
Everything else, do **NOT** edit.

## Commands
There are absolutely no in-game commands. This bot is entirely run externally from your rust servers. So, all the following commands are in Discord only.

### Player Commands
`/claim` - Allows a player to claim a prize that they have won
`/link` - Links the player inside of the bots data. Pulls data from Steamcord when this is run. Players must "link" in discord as well as Steamcord.
`/giveaway join <giveaway_id> <ticket_amount>` - Joins a giveaway with the specified ID and the specified ticket amount.
`/ping` - Show bots latency

### Admin Commands
`/load`, `/unload`, `/reload` - All of these are "Cog" commands. You can load, unload, or reload a set of slash commands. Try doing this before restarting your bot if something goes wrong. The available "cogs" are listed in the `./cogs` directory.
`/giveaway start <giveaway_id>` - Manually starts a set giveaway.
`/unlink <discord_id>` - Deletes the user from the bots data. This includes all tickets and giveaway tracking, etc. Its gone. Once its gone, its not coming back unless you have a backup.
`/tickets (add|remove|set) <discord_id> <ticket_amount>` - Add's, Remove's, or Set's the users tickets to the specified amount.

## Configuration Files
The configuration files are a little bit confusing I will admit, however I will try to document them here to the best of my ability. I'm going to work on a rewrite of all the configuration files here sometime soon. For now, if you have questions come to the discord, open a ticket.
### `./configs/settings.json`
```json
{
    "Bot Settings": {
        "Bot Token": "BOT_TOKEN_HERE",
        "Command Prefix": ".",
        "Dev Guild ID": "123456789123456789",
        "Bot Name": "RCON Discord Giveaway Bot",
        "Debug Level": "verbose",
        "Sync Commands Globally?": true,
        "Server Network Name": "BippyMiester.dev",
        "Bot Manager Role IDs": [
            123456789123456789,
            12345678912345679
        ],
        "Steamcord.io API Key": "API_KEY_HERE",
        "Linking Website URL": "https://tireddadsrustcommunity.steamcord.link",
        "Giveaway Channel ID": "1316963395320418324"
    }
}
```
