---
title: Product Documentation
description: All the documentation for the various products that BippyMiester has created, sold, or given away for free.
published: true
date: 2025-03-25T03:59:55.853Z
tags: codefling, products, product documentation
editor: markdown
dateCreated: 2025-03-22T08:00:20.781Z
---

# Documentation

All of the products listed here are have been created by BippyMiester alone or in conjuction with others where specified. All files fall under the following [legal terms & policies](/legal).

## [RCON Discord Giveaway Bot](/documentation/RCONDiscordGiveawayBot)

This bot is bound to blow your mind. The first of its kind, giveaways can now be automated through this Discord bot!

You are probably asking yourself, how? Well, the process is simple.

- You connect your server to the bot via RCON in the settings
- Your players link their steam and discord accounts via Steamcord
- Your players just start playing and they get tickets for playing! No more plugin running on the server with a timer, taking up valuable resources!
- Define the giveaways within the bot, and set how often they run.
- Players then enter tickets into the giveaway
- Giveaway ends automatically, however this time, the player can then type /claim in discord and it will run a raw RCON command to the server the player chooses. It will check that the player is online first.

Sounds pretty good right? No more manually giving out VIP packages or Skill Tree XP or Economy Cash.

## EasyVotePro

EasyVotePro is a plugin designed to integrate player voting into gaming servers, seamlessly supporting several popular voting sites such as Rust-Servers.net and GamesFinder.net. This plugin facilitates rewarding players for their votes, with a system that allows for customizable reward tiers based on the number of votes received. Players can view vote links directly from the chat, enhancing user interaction without the need for additional notes or permissions. The plugin simplifies reward management by utilizing commands for rewarding players, which can be tailored to suit the needs of each server.

Additionally, EasyVotePro offers a set of useful commands for maintaining and understanding player vote status, such as clearing or setting vote counts. Notification features can be enhanced through optional plugins like UINotify/Notify and Discord Embeds, providing players with timely reminders and updates about their voting activities. The plugin is currently in beta, so users are encouraged to test its functionalities in a controlled environment to ensure smooth operation.

## Better Suggestions Bot

The suggestion bot is designed to streamline and organize the suggestion process within your community, fostering active engagement among players and staff. It facilitates detailed discussions by automatically attaching threads to each suggestion, allowing for comprehensive dialogue before a decision is reached. Once a suggestion is either approved or denied, the corresponding thread is locked for a specified time and subsequently deleted to maintain a clean channel environment. This bot also keeps track of user statistics, monitoring the number of suggestions made and their respective approval or denial rates.

Admins can efficiently manage suggestions using commands such as /approve or /deny, ensuring a seamless process. The suggestion channel remains uncluttered, as direct posting is restricted, encouraging discussions to take place within the designated threads. Upon finalizing a decision, the user who submitted the suggestion is tagged to inform them of the outcome, thereby enhancing transparency. The bot requires self-hosting with Python 3.10, and users must possess basic knowledge of Discord bot setup and JSON file editing. Future updates promise additional features to further enrich the suggestion process.

## Battlemetrics Ban Approval Bot

The Discord bot is tailored for organizations requiring ban approvals from Trial Admins or Admins in training, ensuring effective ban management and promoting correct practices to prevent false bans. By utilizing the bot, organizations can verify that bans meet the required standards with sound evidence before enforcement. It serves as a valuable training aid for new staff, helping them align with the organization’s operational procedures. The bot integrates seamlessly with the Battlemetrics API, automating the collection of ban details.

Installation requires uploading the bot files to a Python-compatible host, configuring environment variables in the `.env` file, and running `main.py` to initiate. Key settings include API tokens and role IDs without quotes unless specified, ensuring smooth functionality. The bot provides commands like `/ping` for latency checks and `/ba` for submitting bans for approval. Future updates plan to enhance usability, including features for editing bans directly from Discord, enriching approval queue details, and customizable embeds. This tool is designed for efficient and structured ban approval processes, with a setup that can be completed swiftly.

## Easy Armored Trains Config

The Armored Train configuration offers a comprehensive setup for both above-ground and below-ground operations in gaming environments. It includes 16 varied train cars such as loot cars, Bradley cars, and SAM Site cars, categorized into easy, medium, hard, and expert levels. Locomotives are also adjustable across these difficulty tiers. For testing purposes, the "atrainstart testing" command spawns a train with all car types, offering clear visibility of the configuration.

NPC models are integrated through kits that assign specific gear depending on the difficulty level, ranging from easy to expert settings. The health and kit specifications are set for each NPC type, with the easy and medium levels having 150 health, escalating to 200 for expert NPCs. SAM Site and Bradley cars each come with predefined health and turret specifications, allowing for tactical adjustments. The loot cars utilize the AlphaLoot plugin by default, with configurations allowing for custom loot table integrations. This setup supports dynamic gameplay through its structured yet flexible configuration, ensuring both challenge and engagement across various difficulty levels.

## Raidable Bases Packs & Singles

**Raidable Bases Packs & Singles** offer a variety of challenges and experiences with different difficulty levels across multiple base packs. Each pack contains a set of bases pre-equipped with essentials like boxes, furnaces, lockers, drop boxes, vending machines, and more, eliminating the need for users to manually populate these loot locations. The bases are categorized into easy, medium, and hard levels, providing diverse options for enhancing gameplay. Additionally, there is a Nightmare base featuring "The Castle," rich in unique elements, designed to maximize player engagement with numerous turrets.

Installation is straightforward and involves extracting files into the `oxide/data/copypaste` directory and using simple console commands to integrate them into the Raidable Bases plugin. Each base file has a distinct name, making it unnecessary to rename files, even if you own multiple packs. Players can quickly get started by following these instructions to experience various base setups and challenges immediately. For a more in-depth understanding of utilizing these bases, users are encouraged to view the instructional content available through Rust Admin Academy's YouTube resources.

## 180 Kits Profiles for NPC's

This comprehensive collection of kits is designed for the Kits plugin by Mevent, ideal for enhancing NPC characters on roleplaying servers. Each kit offers variations in clothing and weapons to provide diversified roleplay scenarios. The kits are compatible with NPCKits and BotReSpawn, making them particularly suited for servers emphasizing intricate character roles. The system allows for extensive customization—each kit can feature multiple clothing styles and weapon skins, ensuring visually distinct NPC profiles.

Installation involves downloading and placing the file within the `oxide/data/Kits/Kits.json` directory. This package includes a variety of roles, such as bandit guards, shipmates, scientists, miners, and more, each with unique clothing and weapon variations. For instance, the "Roughneck" kit includes three clothing and seven weapon variations, resulting in various potential combinations to enrich gameplay. This assortment is perfect for servers seeking to expand their NPC diversity and create an immersive player environment.