---
title: RCON Discord Giveaway Bot
description: 
published: true
date: 2025-03-25T03:59:23.537Z
tags: 
editor: markdown
dateCreated: 2025-03-24T02:55:47.964Z
---

# RCON Discord Giveaway Bot

This bot is bound to blow your mind. The first of its kind, giveaways can now be automated through this Discord bot!

You are probably asking yourself, how? Well, the process is simple.

1. You connect your server to the bot via RCON in the settings
2. Your players link their steam and discord accounts via [Steamcord](https://steamcord.io/)
3. Your players just start playing and they get tickets for playing! No more plugin running on the server with a timer, taking up valuable resources!
4. Define the giveaways within the bot, and set how often they run.
5. Players then enter tickets into the giveaway
6. Giveaway ends automatically, however this time, the player can then type `/claim` in discord and it will run a raw RCON command to the server the player chooses. It will check that the player is online first.

Sounds pretty good right? No more manually giving out VIP packages or Skill Tree XP or Economy Cash.

## Installation Instructions

Here are a few ways you can install the discord bot.

### Vultr

You can use my [Vultr Affiliate Link](https://www.vultr.com/?ref=7206663) and get a small VPS (Virtual Private Server) to host your bot. This is the most advanced way as you have to install python, and be familiar with the linux OS. If you know what you're doing, consider supporting me by using this affiliate link.

### Host on a Panel

This is probably the most common. You can find all sorts of different Python Discord Bot Hosts out there. Ranging from as little at $1.00/month to as high as $5/month.

***Note:*** DO NOT use the free bot hosting options. Most of them want you to join with Discord, and if you look at the permissions that their Discord application wants, its an absolute security nightmare. 

### Host with ME!

Yep thats right, you can host your bot with me for $2.00/month. Invoices are through Paypal. Just open a ticket in my discord and I can set you up.

### Run on a Windows or Linux machine

Either OS you have to have python installed. You can find how to do that using the following documentation:

[Windows Python Installation](https://www.python.org/downloads/)

[Linux Python Installation](https://www.python.org/downloads/source/)

[Windows Youtube Installation Video](https://www.youtube.com/watch?v=28eLP22SMTA)

[Linux Youtube Installation Video](https://www.youtube.com/watch?v=IAco2SSuGms)

Then you can run in either Windows or Linux the following command in a terminal

```
python3 DOWNLOAD_LOCATION/main.py
```

The download location will be called the "root directory" of the bot. So where ever the root directory is, whether thats in your Downloads folder or somewhere else, you have to just run that command plus the `main.py` to start the bot up.

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
Some of these things are pretty obvious. Bot token, bot name, api keys, etc. Some of the things that aren't obvious are:

`Dev Guild ID` - This variable is mandatory **IF** `Sync Commands Globally` is `false`.
The variable will essentially "spawn" the bots slash commands in that guild. This is **ONLY** recommended for development. Setting it up this way and doing it live can result in unintended consequences. So, make sure that `Sync Commands Globally` is set to `true`, and you should (if you don't have a testing server) put your live discord server's guild ID in this field.

***TL;DR***

Set this to your testing discord's guild ID, or your main discord's guild id. Leave `Sync Commands Globally` alone. Change to `true` if needed.

## `./configs/scheduler.json`
```json
{
    "Schedules": [
        {
            "Hours In Between Giveaways": 0.05,
            "Winners Chosen Per Giveaway": 1,
            "Weights": {
                "100": [
                    "bronze",
                    "shop-cash-1",
                    "skill-tree-xp1",
                    "better-build"
                ],
                "75": [
                    "silver",
                    "shop-cash-2",
                    "skill-tree-xp2"
                ],
                "50": [
                    "gold",
                    "shop-cash-3",
                    "skill-tree-xp3"
                ],
                "25": [
                    "diamond"
                ],
                "10": [
                    "platinum"
                ]
            },
            "Last Schedule Run (DO NOT TOUCH)": 123456789
        }
    ]
}
```
The `Hours In Between Giveaways` can be a little deceiving. If I have a giveaway that is to be run every 48 hours, and I want to run the next giveaway 24 hours after that, then the `Hours In Between Giveaways` should be `72` and not `24`. I know thats confusing. Rewriting it will happen eventually but its an annoying rewrite so probably not soon TBH.

The `Weights` are pretty easy too, the higher the number the more chance of it being chosen, lower number lower chance. The names inside each weights list are the same as the filenames in `./giveaway`, AKA `giveaway_id`'s. Easy right?

## `./giveaways/*.json`

The reason it's `*.json` is because there can be an infinite number of combinations of giveaways you can put together. The file name is the `giveaway_id` for the `/giveaway start` command mentioned earlier.

It is suggested to have at least 15-20 different types of giveaways so that it doesn't choose the same giveaway again.


```json
{
    "Giveaway ID (DO NOT EDIT!)": "test",
    "Giveaway Enabled?": true,
    "Commands To Run": [
        "say Bot made by BippyMiester.dev"
    ],
    "Giveaway Length (Hours)": 0.05,
    "Number of Winners": 1,
    "Randomizer": 1.0,
    "Weight": 5.0,
    "Role To Tag On Start": 679128978534957096,
    "Embed": {
        "Title": "Test Giveaway",
        "Description": "*\"Whoa, hold up! This giveaways giving away… NOTHING! Thats right, zilch, zip, nada! But dont freak out, its just a test to keep the bot in tip-top shape! Think of it as a *totally tubular* tech workout. Youve got 1 hour to enter, but heres the kicker—its a ticket burner! Once you enter, those tickets are gone like last weeks mix tape. So if youre not down to say goodbye to those bad boys, no worries—just skip it! But hey, bot data doesnt gather itself, so thanks for helping out, tech warriors!\"*",
        "Embed Color": "#ff0000",
        "Conditions": [
            "You must have at least 1 Ticket",
            "You must have linked your Discord and Steam Accounts",
            "You must be an active member in the community"
        ],
        "Small Icon": "https://i.imgur.com/HL8Qebp.png",
        "Large Icon": "https://i.imgur.com/SYnEa2q.png",
        "Footer": "{server_network_name} | Made with <3"
    },
    "Active Giveaway IDs (DO NOT EDIT!)": [],
    "Past Giveaway IDs (DO NOT EDIT!)": []
}
```

`Giveaway Enabled` - set to false if you don't want it to be chosen during giveaway selection

`Commands To Run` - A list of raw RCON console commands to be run when a player redeems the prize with the `/claim` command

`Giveaway Length (Hours)` - How long the giveaway lasts in hours.

`Role To Tag On Start` - The Discord Role ID of the role that you want to tag when a giveaway starts.

Embed `Conditions`: These are the bulleted points in the embed that you can see on the example images on the Codefling Product Page.

No Touchy Touchy
```
"Active Giveaway IDs (DO NOT EDIT!)": [],
"Past Giveaway IDs (DO NOT EDIT!)": []
```

#### The Choose Winners Process
This final value will bias the winners of that giveaway to newer players or players with lower tickets.
```
Randomizer: A number between 0.0 and 1.0.
Weight: A weight factor. If -1, no bias is applied.
 - Weight > 1.0: Bias toward higher values.
 - 0.0 < Weight < 1.0: Bias toward lower values.
```
Players with lower tickets:
`Randomizer`: `0.25`
`Weight`: `0.5`

Players with higher tickets:
`Randomizer`: `0.8`
`Weight`: `1.75`

Completely Random:
`Randomizer`: `0.5`
`Weight`: `-1`

## `./servers/*.json`

Just like the `./giveaways` you are able to have infinite servers here as well.
```json
{
    "Server Enabled?": true,
    "Server Name": "Tired Dad's Rust",
    "Server IP": "127.0.0.1",
    "RCON Port": 28118,
    "RCON Password": "some password here",
    "Seconds Between Tickets Given": 60,
    "Number of Tickets Given Per Cycle": 0.5
}
```
If you have questions about this pop in the discord. Things seem to be pretty easy to set up in this file.