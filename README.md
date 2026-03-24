# D2ChannelBot

<img width="400" alt="Banner" src="https://github.com/user-attachments/assets/ee532630-a554-4a48-9e10-7440a777779d">

> A Diablo 2 channel bot that tracks Chaos and Baal runs. Built for use with d2bs/kolbot.

## Features

- **Automatic Channel Join** - Joins a specified channel on startup
- **Leader Verification** - Verifies leader identity via `!login` command
- **Run Tracking** - Tracks total runs completed by the leader
- **Game Announcements** - Posts current game name to channel
- **Milestones** - Announces achievements at configurable intervals
- **Scheduled Updates** - Periodic channel announcements with recent games list
- **Data Persistence** - Saves stats to JSON for session continuity

## Commands

| Command | Access | Description |
|---------|--------|-------------|
| `!runs` | Public | Display total runs completed |
| `!game` | Public | Show current/last game name |
| `!help` | Public | List available commands |
| `!login` | Leader | Authenticate as the run tracker leader |
| `!logout` | Leader | End leader session |
| `!reset` | Leader | Reset all run statistics |

## Configuration

Edit the config section at the top of `ChannelBot.dbj`:

| Variable | Description | Default |
|----------|-------------|---------|
| `CB_Channel` | Target channel name | `OP CHAOSBAAL` |
| `CB_LeaderAccount` | Leader account (format: `charname*accountname`) | - |
| `CB_MilestoneEvery` | Announce milestone every N runs | `3` |
| `CB_GameListInterval` | Game list announce interval (ms) | `3 minutes` |
| `CB_MaxGamesInList` | Recent games to keep in list | `5` |

## Requirements

- [d2bs](https://github.com/d2bs/d2bs) - Diablo 2 bot core
- [kolbot](https://github.com/kolton/d2bot-kolbot) - Automation framework

## Status

> **Note:** This is a work in progress.

### Tested Features ✓

- [x] Channel join
- [x] Leader `!login` verification
- [x] `!game` command
- [x] `!runs` tracking
- [x] `!reset` functionality
- [x] Periodic game announcements
- [x] Milestone notifications

### TODO

- [ ] `!help` command implementation
- [ ] Additional command polish

## License

MIT
