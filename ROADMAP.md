# StatStacker Roadmap

## Shipped
- Animations (countup, confetti, row slide-in)
- Shareable results (emoji grid + clipboard)
- More stat categories (NFL: 12, NBA: 10)
- Era filter (2015+ default, configurable to 1980+)
- Full ESPN data migration (offense + defense, retired + active)
- Mobile layout optimization
- Custom domain (statstacker.com)
- Feedback (Google Form)
- Ad placements (ready for AdSense)

## No Backend Required (GitHub Pages)

### Timer Mode
- Optional countdown timer per pick (e.g., 30s, 60s, 90s)
- Toggle on/off — casual players can ignore it
- Timer visible in the UI, auto-submits or skips on expiry
- Adds competitive pressure without requiring accounts
- Timer setting included in shared puzzle links

### Async Matchups (Challenge Links)
- Encode puzzle seed (league, stat, teams, years, era) into a URL
- Player completes the puzzle, gets their score
- "Challenge a Friend" button generates the link
- Friend opens link, gets the exact same board
- After completing, friend sees their own score
- No backend — puzzle is deterministic from the seed
- Future enhancement: encode score in URL so friend can see both

## Backend Required (Vercel + Supabase migration)

### Accounts
- Sign up / login (email, Google OAuth)
- Persistent identity across devices
- Required foundation for match history, leaderboards, and sync play
- Free tier: Supabase auth + Vercel serverless

### Match History (depends on accounts)
- Save completed games: puzzle config, picks, score, percentage
- Personal stats dashboard: games played, average %, best scores
- History of challenge matchups and results
- Storage: Supabase Postgres, ~1KB per game

### Leaderboards / Rankings (depends on accounts)
- Global leaderboards by stat category and league
- Weekly/monthly/all-time filters
- Percentile ranking ("Top 5% of all players")
- Anti-cheat: server-side score validation
- Storage: Supabase with indexed queries

### Sync Matchups (depends on accounts)
- Real-time head-to-head with a shared timer
- Both players see the same board simultaneously
- Live score comparison as each player submits picks
- Needs: WebSocket or Supabase Realtime for live state sync
- Lobby system: create room → share code → opponent joins
- Most complex feature — build last

## More Sports (deferred — needs domain expertise to verify)

### MLB
- Stat categories: HRs, RBI, batting average, ERA, strikeouts, stolen bases, WAR, OPS
- ESPN has MLB team leaders endpoints
- Team/division structure similar to NFL

### NHL
- Stat categories: goals, assists, points, saves, GAA, plus/minus
- ESPN has NHL endpoints
- 32 teams, conference/division structure

### College Football / Basketball
- Would significantly expand audience
- More complex: hundreds of teams, roster turnover
- ESPN has NCAAF and NCAAB endpoints

## Future Ideas (unprioritized)
- **Difficulty modes** — Easy (shows team history), Hard (no year selector)
- **Daily challenge** — One fixed puzzle per day, seeded from date, everyone gets the same board
- **Streak tracking** — Consecutive games above a score threshold
- **Achievements/badges** — "Perfect game", "Found a diamond in the rough"
- **Sound effects** — Buzzer beater on great picks, crowd noise
- **Theme nights** — "Legends only (pre-2000)", "One conference", "Rookies only"
