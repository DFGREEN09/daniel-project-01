# Gaffer '99: 1998/99 Premier League Season Simulator

A Championship Manager-style career simulator for the 1998/99 FA Carling Premiership. Manage any of the 20 clubs, select your starting XI and substitutes, simulate matches with a live match engine, conduct post-match press interviews, and read tabloid reports about your team's performance.

## Features

### 🏟️ Full Season Experience
- **All 20 Premier League clubs** from 1998/99 season with authentic:
  - Stadium names and capacities
  - Club managers and their formations
  - Team kits and colours
  - Squad rosters with real players

### ⚽ Match Simulation
- **Live Match Engine** with:
  - Real-time commentary and play-by-play action
  - Goal-scoring animations and celebration replays
  - Saves, shots on target, and goalkeeper heroics
  - Yellow and red card incidents
  - In-game tactical substitutions (up to 3 per match)
  - Weather conditions affecting play
  - Injury tracking and player fatigue

### 🔄 Transfer System
- **Pre-Season Transfer Window**
  - Browse available free agents
  - Receive transfer offers for your players
  - Make bids on rival clubs' players
  - Negotiate wages and contract lengths
  - View transfer rumours in tabloid

- **January Transfer Window**
  - Mid-season recruitment opportunities
  - Emergency loan signings
  - Squad depth management

### 🗣️ Post-Match Press Conferences
- Staged questioning system covering:
  - Player performance and individual ratings
  - Team form and tactical decisions
  - Next fixture preview and preparation
  - Transfer gossip and squad updates
  - Selection reasoning and injuries
- Your answers feed directly into tabloid headlines

### 📰 Tabloid Reporting
- **The Back Page** newspaper at your manager's desk
  - Headline stories based on your press answers
  - League gossip and rival club news
  - Player performance summaries
  - Transfer speculation and rumours
  - Match reports and statistics
  - Weekly manager quotes

### 📊 Management Tools
- **League Table** - Live standings updated after each fixture
- **Fixtures List** - Full season calendar with results
- **Squad Register** - Player stats, form, injuries, contracts
- **Team Sheet Selection** - Pick your XI and 5 substitutes before each match
- **Tactical Formation** - Adjust formation and playing style
- **Injury List** - Track player fitness and recovery times
- **Auto-Save** - Game state saved to browser localStorage

## Quick Start

### Installation

```bash
# Clone the repository
git clone https://github.com/DFGREEN09/daniel-project-01.git
cd daniel-project-01

# Install dependencies
npm install

# Start development server
npm run dev
```

The game will be available at `http://localhost:5173` (or the port shown in terminal).

### How to Play

1. **Select Your Club** - Choose from any of the 20 Premier League clubs
2. **Review Your Squad** - Check player stats, form, and positions
3. **Prepare for Match Day**
   - Select your first XI (11 players)
   - Choose your 5 substitutes
   - Set your formation (4-4-2, 4-3-3, 3-5-2, etc.)
   - Adjust team instructions (aggressive/defensive)
4. **Simulate the Match** - Watch the live match engine unfold
5. **Post-Match Press** - Answer questions from journalists
6. **Read the Back Page** - See how your comments appear in print
7. **Repeat** - Play the next fixture or use transfer window to strengthen squad

## Project Structure

```
premier-99/
├── src/
│   ├── components/
│   │   ├── ClubSelector.tsx          # Initial club selection screen
│   │   ├── TeamSheet.tsx             # XI and subs selection
│   │   ├── MatchEngine.tsx           # Live match simulation
│   │   ├── PressConference.tsx       # Post-match interview
│   │   ├── TransferWindow.tsx        # Buy/sell players
│   │   ├── LeagueTable.tsx           # Standings
│   │   ├── FixturesList.tsx          # Match calendar
│   │   ├── SquadRegister.tsx         # Player management
│   │   └── BackPage.tsx              # Tabloid newspaper
│   ├── data/
│   │   ├── clubs.ts                  # All 20 clubs data
│   │   ├── players.ts                # Player rosters
│   │   ├── fixtures.ts               # 38-game schedule
│   │   └── stadiums.ts               # Stadium information
│   ├── engine/
│   │   ├── matchSimulator.ts         # Match simulation logic
│   │   ├── playerRating.ts           # Performance calculation
│   │   ├── injurySystem.ts           # Injury management
│   │   └── transferLogic.ts          # Transfer mechanics
│   ├── state/
│   │   ├── gameState.ts              # Game state management
│   │   ├── playerStats.ts            # Player performance tracking
│   │   └── seasonProgress.ts         # Season progression
│   ├── types/
│   │   └── game.ts                   # TypeScript type definitions
│   ├── App.tsx                       # Main app component
│   └── main.tsx                      # Entry point
├── public/
│   ├── kits/                         # Club kit graphics
│   ├── stadiums/                     # Stadium images
│   └── badges/                       # Club badges
├── package.json
├── vite.config.ts
└── tsconfig.json
```

## Game Mechanics

### Match Rating System
- **Player Ratings** (1-10 scale):
  - Determined by actions during match (goals, assists, tackles, saves)
  - Affected by player's base ability and current form
  - Form can improve/decline based on performance
  - Injuries reduce available player pool

### Fixture Scheduling
- Full 38-game season (home and away vs each opponent)
- Realistic fixture congestion
- Cup competition overlap tracking
- Play matches in any order (or auto-simulate non-selected matches)

### Transfer Market
- **Player Values** based on:
  - Age and experience
  - Current form and ratings
  - Contract length remaining
  - Position rarity
  - Big club premium

- **Budget System**:
  - Starting transfer budget varies by club
  - Income from match day revenue
  - Sponsorship deals
  - Player sales add to budget

### Injury System
- Random injury chance during matches
- Injury severity (minor, moderate, severe)
- Recovery time varies (1-8 weeks typically)
- Players return to form gradually

## Data Sources

- **Clubs & Managers**: Historical 1998/99 season records
- **Players**: Authentic squad rosters from that season
- **Fixtures**: Official Premier League schedule
- **Statistics**: Real stadium data and historical records

## Browser Compatibility

- Chrome/Edge 90+
- Firefox 88+
- Safari 14+
- Mobile browsers (iOS Safari, Chrome Mobile)

Game data persists locally using browser `localStorage` - no account required.

## Development

### Build for Production
```bash
npm run build
```

### Run Tests
```bash
npm run test
```

### Debug Mode
```bash
npm run dev -- --debug
```

## Roadmap

- [ ] Cup competitions (FA Cup, League Cup, European competitions)
- [ ] Assistant manager advice system
- [ ] Fan morale and supporter satisfaction
- [ ] Academy system for youth development
- [ ] Staff hiring and backroom team
- [ ] Board interference and owner objectives
- [ ] Multiplayer league mode (cross-browser)
- [ ] Detailed statistics and historical records
- [ ] Replay saving and match highlights
- [ ] Commentary language options

## Keyboard Shortcuts

| Key | Action |
|-----|--------|
| `Space` | Play/Pause match |
| `→` | Next match event |
| `←` | Previous match event |
| `S` | Save game |
| `L` | Load game |
| `T` | Open transfer window |
| `P` | Press conference |
| `Esc` | Return to main menu |

## Tips & Tricks

1. **Squad Rotation** - Use the transfer window to build depth for specific positions
2. **Form Tracking** - Pay attention to player form ratings before selecting your XI
3. **Tactical Flexibility** - Adjust formation based on opponent difficulty
4. **Press Diplomacy** - Diplomatic answers boost morale; harsh answers cause tension
5. **Youth Integration** - Don't overlook young players with high potential
6. **Financial Planning** - Don't spend all your budget early in the season
7. **Injury Management** - Keep squad depth to handle injuries
8. **Reading Gossip** - Tabloid rumours often hint at transfer targets

## Known Limitations

- Match simulation is based on player ratings, not real match statistics
- Historical accuracy prioritized over perfect realism
- Some lesser-known players may have placeholder stats
- Mobile UI optimized but best on desktop

## Credits

- Historical data sourced from official Premier League records
- Match engine inspired by classic Championship Manager games
- UI design influenced by retro sports management games

## License

MIT License - See LICENSE file for details

---

**Gaffer '99** © 2024 - Made for fans of classic football management games and the legendary 1998/99 Premier League season.

**Play now**: Clone, install, and run `npm run dev` to take charge of your club!
