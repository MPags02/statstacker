# StatStacker Roadmap

## Priority 1 — Head to Head
- Generate a shareable game link encoding the puzzle seed (teams, years, stat category)
- Both players get the identical puzzle, fill it independently
- Compare scores side-by-side at the end
- Needs: URL-based puzzle encoding, results storage (localStorage or lightweight backend)

## Priority 2 — Animations
- Stat counter roll-up animation when a player is submitted
- Tier color reveal (flash white → fade to tier gradient)
- Confetti/particle burst on 90%+ final score
- Smooth expand/collapse for top answers dropdown
- Subtle pulse on "add player" buttons to draw attention
- End-of-game conclusion panel entrance animation (scale up + fade in)

## Priority 3 — More Stat Categories
### NFL (current: pass_yds, pass_td, rush_yds, rush_td, rec_yds, rec, rec_ypg, rush_ypg, scrim_yds, tot_td)
- Add: sacks, interceptions (defensive), fumble recoveries, kick/punt return yards, passer rating, fantasy points (non-PPR)
- Verify ESPN category mapping exists for each

### NBA (current: pts_pg, ast_tot, three_tot, ftp)
- Add: rebounds, steals, blocks, PER, double-doubles, minutes per game, field goal percentage, free throws made
- ESPN has all of these in their leaders endpoint

## Priority 4 — Shareable Results
- "Share" button after game completion
- Generates a text/emoji grid summary (like Wordle):
  ```
  StatStacker 🏈 Pass Yards
  🟧⬛🟨🟩🟩
  Score: 18,432 (87% of best)
  ```
- Tier emojis: 🟩 legendary, 🟦 diamond, 🟨 gold, ⬜ silver, ⬛ default
- Copy to clipboard for pasting to social/messages
- Optional: generate a shareable image (canvas-based)

## Priority 5 — More Sports (deferred — needs domain expertise to verify)
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
- **Challenge mode** — Timed rounds, 60 seconds per pick
- **Streak tracking** — Consecutive games above a score threshold
- **Achievements/badges** — "Perfect game", "Found a diamond in the rough"
- **Sound effects** — Buzzer beater on great picks, crowd noise
- **User accounts + leaderboards** — Daily/weekly high scores
- **Theme nights** — "Legends only (pre-2000)", "One conference", "Rookies only"
- **Mobile-first redesign** — Swipe navigation, bottom sheet search
