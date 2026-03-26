# D2ChannelBot
<img width="400" alt="Banner" src="https://github.com/user-attachments/assets/ee532630-a554-4a48-9e10-7440a777779d">
> A Diablo 2 channel bot that tracks Chaos and Baal runs. Built for use with **d2bs/kolbot**.

## Features
- **Automatic Channel Join** — Joins your specified channel on startup and stays there
- **Multi-Leader Support** — Any authorized leader can announce runs instantly (no `!login` required)
- **Run Tracking** — Counts total runs with persistent JSON storage
- **Game Announcements** — Automatically posts the next game name to the channel
- **Milestones** — Announces big milestones at configurable intervals
- **Periodic Updates** — Posts a list of recent games on a schedule
- **Data Persistence** — All stats are saved to `data/ChannelBotStats.json`

## Commands

| Command       | Access     | Description                                      |
|---------------|------------|--------------------------------------------------|
| `!runs`       | Public     | Display total runs completed                     |
| `!game`       | Public     | Show the last announced game                     |
| `!status`     | Public     | Show current total runs                          |
| `!help`       | Public     | List all available commands                      |
| `!leaders`    | Leader     | Show the list of authorized leaders              |
| `!reset`      | Leader     | Reset all run statistics (clears JSON file)      |

**Game Announcement Format:**  
Leaders simply type:  
`next game is GameName123`

## Configuration
Edit the config section at the top of **`ChannelBot.dbj`**:

| Variable                  | Description                                      | Default / Example                     |
|---------------------------|--------------------------------------------------|---------------------------------------|
| `CB_Channel`              | Target channel name                              | `"OP CHAOSBAAL"`                      |
| `CB_Leaders`              | Array of authorized leaders                      | `["charname*account", "MyMain*Acc"]` |
| `CB_MilestoneEvery`       | Announce milestone every N runs                  | `10`                                  |
| `CB_GameListInterval`     | How often to post recent games (ms)              | `3 * 60 * 1000` (3 minutes)           |
| `CB_MaxGamesInList`       | How many recent games to show                    | `5`                                   |
| `CB_AnnounceMilestone`    | Enable/disable milestone messages                | `true`                                |

> **Tip:** You can use just the character name or full `char*account` format in the leaders list.

## Requirements
- [d2bs](https://github.com/d2bs/d2bs)
- [kolbot](https://github.com/blizzhackers/kolbot)

## Status
**Fully updated and improved** — March 2026

### Current Features ✓
- [x] Multi-leader support (no `!login` / `!logout` needed)
- [x] Instant game announcements by any authorized leader
- [x] All commands working (`!help`, `!status`, `!leaders`, `!reset`, etc.)
- [x] Channel joining & staying in lobby chat
- [x] Data persistence (JSON)
- [x] Milestone announcements
- [x] Periodic recent games list
- [x] Clean prevention of game creation/joining

**No more login step** — trusted leaders can announce runs immediately.

## License
MIT

---

**Made with ❤️ for the Diablo 2 community**
