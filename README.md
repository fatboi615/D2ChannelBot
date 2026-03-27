# D2ChannelBot

> A clean and simple Diablo 2 channel bot that tracks Chaos Sanctuary and Baal runs.  
> Built for **d2bs / Kolbot**.

## Features
- **Automatic Channel Join** — Joins your chosen channel on startup and stays there
- **Multi-Leader Support** — Any authorized leader can announce runs instantly (no `!login` needed)
- **Leader Profile Integration** — Reads run count directly from a leader's profile JSON file
- **Run Tracking** — Counts total runs with persistent JSON storage
- **Game Announcements** — Posts the next game name to the channel
- **Milestones** — Announces every X runs (configurable)
- **Stats Tracking** — Best streak, average run time, session stats
- **Periodic Updates** — Automatically posts recent games list
- **Data Persistence** — Saves everything to `data/ChannelBotStats.json`
- **Response Delay** — 2 second delay on bot responses to avoid spam

## Commands

| Command       | Access     | Description                                      |
|---------------|------------|--------------------------------------------------|
| `!runs`       | Public     | Display total tracked runs + leader profile runs |
| `!game`       | Public     | Show the last announced game                     |
| `!stats`      | Public     | Show detailed stats (streak, avg time, session)  |
| `!help`       | Public     | List all available commands                      |
| `!reset`      | Leader     | Reset all run statistics (clears JSON file)     |

**How to announce a game:**  
Leaders just type:  
`next game is GameName123`

## Installation
1. Copy `ChannelBot.dbj` into your Kolbot folder:  
   `d2bs/kolbot/bots/`
2. Add the bot in **D2Bot#** as a normal profile
3. Set the script to **`ChannelBot.dbj`**
4. Edit the config at the top of the file (leaders + channel + leader profile)

## Configuration
Edit the config section at the top of **`ChannelBot.dbj`**:

| Variable                  | Description                                      | Default / Example                     |
|---------------------------|--------------------------------------------------|---------------------------------------|
| `CB_Channel`              | Target channel name                              | `"OP CHAOSBAAL"`                      |
| `CB_Leaders`              | Array of authorized leaders                      | `["charname*account", "MyMain*Acc"]` |
| `CB_LeaderProfileName`    | Name of leader's profile data file               | `"CBRUNZ"`                            |
| `CB_MilestoneEvery`       | Announce milestone every N runs                  | `50`                                  |
| `CB_GameListInterval`     | Recent games announce interval (ms)              | `3 * 60 * 1000` (3 minutes)           |
| `CB_MaxGamesInList`       | How many recent games to show                    | `5`                                   |
| `CB_AnnounceMilestone`    | Enable/disable milestone messages                | `true`                                |

> **Tip:** You can match leaders by character name, account name, or full `char*account` format.

### Example Config Snippet
```js
var CB_Channel = "OP CHAOSBAAL";

var CB_Leaders = [
    "YourLeader1*Account1",
    "YourLeader2*Account2",
    "MyMainChar"                    // just char name also works
];

var CB_LeaderProfileName = "CBRUNZ";        // reads data/CBRUNZ.json for run count
var CB_LeaderDataFile    = "data/" + CB_LeaderProfileName + ".json";
```

## Requirements

- d2bs
- Kolbot

## Status
<img width="372" height="330" alt="image" src="https://github.com/user-attachments/assets/8d3b753d-3b14-454c-818d-6db994e92082" />

Fully updated and improved — March 2026

### Current Features ✓
- Multi-leader support (no !login / !logout required)
- Leader profile run count integration
- Instant game announcements by any authorized leader
- Detailed stats (!stats) with streak, avg time, session info
- Reliable channel joining
- Data persistence (JSON)
- Milestone + periodic announcements
- Response delay (anti-spam)
- Safe (never creates or joins games)

## Changelog

**2026-03-26** — Added response delay, leader profile integration, detailed !stats command, run time tracking, and session tracking

**2026-03-26** — Major update: Removed !login system, added full multi-leader support, added !status and !leaders, improved !help, cleaned up code and README

## License

MIT

Made with for the Diablo 2 community
