# 💖 Senorita — an all-in-one bot for moderation, music, tickets, giveaways, and server tools.

One Bot. Everything Your Server Needs.

![Node.js](https://img.shields.io/badge/Node.js-18%2B-339933?logo=node.js&logoColor=white)
![Discord.js](https://img.shields.io/badge/discord.js-v14-5865F2?logo=discord&logoColor=white)
![MongoDB](https://img.shields.io/badge/Database-MongoDB-47A248?logo=mongodb&logoColor=white)
![License](https://img.shields.io/badge/License-ISC-blue)

Senorita is an all-in-one Discord bot for moderation, music, tickets, giveaways, and server tools.

Senorita is a Node.js Discord bot built to help server owners and moderators manage day-to-day community operations from one place. It includes command groups for moderation, utilities, music, tickets, giveaways, invite tracking, welcome and leave automation, backups, economy, custom roles, and developer tooling.

---

## About Senorita

This project is designed as a general-purpose Discord server bot rather than a single-purpose utility. It is organized into command categories under `src/commands` and uses a central `Client` system to register commands, events, and database-backed settings.

The project currently targets:

- Node.js
- discord.js v14
- Mongoose + MongoDB
- Shoukaku for music playback integration
- Canvas and helper libraries in the project dependencies

---

## Key Features

- Moderation tools for bans, mutes, warns, role actions, lockdowns, and member management
- Music playback support with queue and playback controls
- Ticket system for support and staff workflows
- Giveaway management commands
- Server utilities such as embeds, sticky messages, announcements, and bot profile tools
- Auto responder and reaction responder tools
- Custom role and role trigger commands
- Invite tracking and leaderboard tools
- Welcomer and leave automation
- Backups and server configuration management
- Fun commands and information commands
- Developer controls for server management and bot administration

---

## Technology Stack

This project uses the following technologies based on the actual repository contents:

- Node.js
- JavaScript
- discord.js v14
- Mongoose
- MongoDB
- Shoukaku
- dotenv
- @napi-rs/canvas
- Axios
- lodash
- moment
- ms
- simply-djs

The bot boots from `index.js`, creates a custom Discord client in `src/structures/Client.js`, loads the command handlers from `src/commands`, and stores persistent config values using the database layer in `src/structures/Database.js`.

---

## Feature Sections

### Moderation
The moderation command group includes real command files such as:

- `ban`, `kick`, `mute`, `unmute`, `warn`, `warnlist`, `warnremove`
- `jail`, `unjail`, `tempban`, `tempmute`, `softban`, `hardban`
- `purge`, `purgebot`, `purgeuser`, `purgeimages`, `purgelinks`, `purgespam`
- `lock`, `unlock`, `lockall`, `unlockall`
- `roleall`, `massban`, `masskick`, `massunban`, `masswarn`
- `setmuterole`, `setlogschannel`, `resetserverconfig`, `serverupdate`

### Music
The music category contains playback and queue management commands, including:

- `play`, `pause`, `resume`, `skip`, `stop`, `queue`, `loop`, `shuffle`
- `join`, `leave`-style voice flow through the music system
- `nowplaying`, `lyrics`, `seek`, `volume`, `autoplay`, `filter` commands
- `skipto`, `jump`, `playnext`, `playprevious`, `clearqueue`, `remove`

### Tickets
Ticket commands include:

- `ticket`, `close`, `claim`, `unclaim`, `add`, `remove`, `rename`, `alert`

### Giveaways
Giveaway commands include:

- `gstart`, `gstop`, `gpause`, `gresume`

### Economy
Economy commands include:

- `bal`, `beg`, `dep`, `with`, `rob`

### Voice / Join-to-Create
Voice-related commands include:

- `tts`, `vcmute`, `vcunmute`, `vcdeafen`, `vcundeafen`, `vckick`, `vcmove`
- `vcmuteall`, `vcunmuteall`, `vcdeafenall`, `vcundeafenall`, `vckickall`, `vcmoveall`

### Utilities and Server Tools
Utility commands include:

- `embed`, `announce`, `autodelete`, `commandschannel`, `dmall`, `audit`, `auditmonitor`
- `botprofile`, `aichannel`, `chattranslate`, `boostcount`, `sticky`, `addemoji`
- `server configuration and channel management helpers`

### Auto Responder
Autoreponder commands include:

- `autoresponder`, `autoresponder-set`, `autoresponder-list`, `autoresponder-remove`
- reaction responders such as `react`, `react-set`, `react-list`, `react-remove`

### Custom Roles and Triggers
Custom role and role trigger commands include:

- `customrole`, `selfroles`, `roletrigger`, `roletriggeradd`, `roletriggerlist`, `roletriggerremove`

### Invite Tracker
Invite tracking tools include:

- `invites`, `invitecheck`, `inviteleaderboard`, `addinvites`, `invitetracker`

### Welcomer
Welcomer setup commands include:

- `welcome`, `leave`

### Backups
Backup-related commands include:

- `backup`

### Fun
Fun commands include:

- `coinflip`, `diceroll`, `rockpaperscissors`, `tictactoe`
- `guessthenumber`, `ship`, `marry`, `divorce`, `lovecalculator`, `friendshipcalculator`
- `animeActions` and related fun modules

### Information
Information commands include:

- `help`, `botinfo`, `stats`, `ping`, `invite`, `serverinfo`, `membercount`, `uptime`
- `userinfo`, `avatar`, `banner`, `roleinfo`, `channelinfo`, `serverbanner`, `servericon`
- `serverfeatures`, `serverboosters`, `serververification`, `servervoice`, `serverstickers`
- `developer`, `owner`, `profile`, `search`, `firstmessage`, `modstats`, `badges`

### Developer Tools
Developer commands include:

- `blacklist`, `unblacklist`, `globalban`, `globalwarn`, `reloadcmd`, `restart`, `status`
- `serverlist`, `servermanager`, `leaveserver`, `leavesmall`, `broadcast`, `execute`
- `noprefix`, `ownerbypass`, `dbbackup`, `cmdblwl`, `devrole`

---

## Installation

Install project dependencies:

```bash
npm install
```

Use the scripts defined in `package.json`:

```bash
npm run dev
npm start
```

The repository is a standard Node.js project; no Python environment or Python startup commands are required.

---

## Environment Configuration

The bot loads environment variables via `dotenv` from the project root `.env` file. The main environment variables used by the codebase include:

```env
DISCORD_TOKEN=
CLIENT_ID=
OWNER_IDS=
ADMIN_IDS=
PREFIX=+
DEFAULT_PREFIX=+
BOT_NAME=Senorita
MONGO_URI=
LAVALINK_HOST=
LAVALINK_PORT=
LAVALINK_PASSWORD=
LAVALINK_SECURE=false
EMBED_COLOR=#dc4aab
SUPPORT_URL=
INVITE_URL=
PORT=2010
NODE_ENV=production
WEBHOOK_JOIN=
WEBHOOK_LEAVE=
WEBHOOK_ALL_LOGS=
ERROR_WEBHOOK=
STATUS_WEBHOOK=
PING_WEBHOOK=
```

Notes:

- Do not commit `.env` to version control.
- Keep tokens and webhook URLs private.
- `MONGO_URI` is optional at runtime, because the project falls back to local persistent storage when MongoDB is unavailable.
- `PREFIX` and `DEFAULT_PREFIX` configure the default command prefix.
- `OWNER_IDS` and `ADMIN_IDS` configure server ownership and admin access.

---

## Database Setup

The project currently uses MongoDB through Mongoose.

The database layer is implemented in `src/structures/Database.js`, and the project includes the `mongoose` dependency in `package.json`.

If MongoDB is not reachable, the bot falls back to a local JSON-based persistent store at the project root:

- `Senorita-data.json`
- `critical_backup.json`

This fallback behavior is implemented in the database layer and is not a substitute for normal MongoDB setup.

---

## Running the Bot

From the repository root:

```bash
npm install
npm start
```

During local development:

```bash
npm run dev
```

The bot entry point is:

- `index.js`

The bot client is initialized in:

- `src/structures/Client.js`

---

## Project Structure

```text
Senorita/
├── .env
├── .gitignore
├── README.md
├── LICENSE
├── index.js
├── package.json
├── shard.js
├── critical_backup.json
├── Senorita-data.json
├── src/
│   ├── assets/
│   ├── commands/
│   │   ├── autoresponder/
│   │   ├── backups/
│   │   ├── customrole/
│   │   ├── dev/
│   │   ├── economy/
│   │   ├── fun/
│   │   ├── giveaway/
│   │   ├── information/
│   │   ├── invitetracker/
│   │   ├── j2csetup/
│   │   ├── moderation/
│   │   ├── music/
│   │   ├── ticket/
│   │   ├── utility/
│   │   ├── voice/
│   │   └── welcomer/
│   ├── events/
│   ├── models/
│   ├── structures/
│   ├── utils/
│   └── index.js
├── node_modules/
├── package-lock.json
└── ...
```

---

## Architecture

The bot follows a standard modular Discord bot architecture:

- `index.js` bootstraps the application and initializes the client.
- `src/structures/Client.js` creates the Discord client, configures intents, loads environment settings, and wires monitoring hooks.
- `src/commands/` contains the command groups used by the bot.
- `src/events/` contains event listeners for guild and client activity.
- `src/models/` contains model definitions for persistent data.
- `src/structures/Database.js` manages MongoDB access and fallback local storage.
- `src/structures/SlashRegistry.js` and related files manage command registration patterns.
- `src/utils/` contains helper and access-control logic, moderation utilities, ticket helpers, and other reusable functions.

---

## Hosting

The project is designed to run as a standard Node.js bot process. It can be hosted on:

- a VPS or dedicated server
- a containerized deployment environment
- a managed Node.js host
- a private Discord bot hosting platform that supports Node.js

The project includes a `shard.js` entry point and supports multi-shard startup behavior through the bot client configuration.

---

## Security

- Never commit `.env` files or secret values.
- Keep webhook URLs and bot tokens private.
- Restrict `OWNER_IDS` and `ADMIN_IDS` to trusted users only.
- Grant only the Discord permissions required for your server.
- Review monitoring and webhook configuration before deploying to production.

---

## Contributing

Contributions are welcome if they match the current project structure and align with the bot's existing architecture.

Before submitting changes:

1. Keep the project consistent with the existing command and event structure.
2. Do not add unsupported frameworks or database systems without updating the project setup.
3. Do not modify `.env` or expose secrets.
4. Check the command categories and keep changes scoped to the relevant feature area.

---

## Support

- Developer: [MR KRISHNA](https://discord.com/users/848781953284571137)
- Invite the bot: [Invite Senorita](https://discord.com/oauth2/authorize?client_id=1556653845809987654&permissions=8&integration_type=0&scope=bot+applications.commands)
- Support URL: configured through `SUPPORT_URL` in `.env` when available

---

## Credits

This project is maintained by **[MR KRISHNA](https://discord.com/users/848781953284571137)** and is built for community server management using the Discord.js ecosystem.

---

## License

This project is licensed under the ISC License.
