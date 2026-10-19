# Ascension Cricket V46 — deploy to GitHub Pages

## Easiest (phone or browser, no tools)
1. GitHub > New repository (e.g. `cricket-ascension`), Public.
2. Add file > Upload files: `index.html`, `sw.js`, `manifest.webmanifest`, `.nojekyll`, and the `icons` folder. Commit.
3. Settings > Pages > Source: **Deploy from a branch** > `main` / `(root)` > Save.
4. After ~1 minute open `https://<your-username>.github.io/cricket-ascension/`.

## Optional: auto-deploy on every push
Upload `.github/workflows/pages.yml` too (works best from a computer/git).
Then Settings > Pages > Source: **GitHub Actions**. Every push to `main` redeploys.

## Install / offline
Open the site once online, Chrome menu > Install app / Add to Home screen, then it plays offline.

## Updating
Bump `V` in sw.js (`cp-v50` > `cp-v51`) whenever files change; players get an "Update ready" prompt.

## Changelog V50
- SCORECARD (dashboard > SCORECARD): built from a log of every real ball in Quick, Chase, Super Over and IPL. Per innings: batting card (runs, balls, 4s, 6s, strike rate, dismissal), extras, dots, fall of wickets with partnership runs, and runs per over. SHARE IMAGE makes a PNG (share sheet on phones, download otherwise).
- ACHIEVEMENTS (dashboard > ACHIEVEMENTS): First Six, Half-Century, Century, Over of Sixes, First Wicket, Hat-trick, Ten Wins, First Match. Unlock toasts, gallery with locked/unlocked state.
- RECENT FORM on the dashboard: last 5 finished matches (W/L for chases, dash for other modes).
- Version V50, cache cp-v50.
- Not in V50: Run/Stay call, fielding AI, new teams, tournament, daily challenge, Player of the Match, art and audio upgrades.

## Test checklist V50
- Play a Chase to the end, open SCORECARD: totals match the match screen.
- Hit a six while batting: First Six unlocks. Check the gallery.
- SHARE IMAGE downloads or opens the share sheet.

## Changelog V49 (graphics finishing pass)
- LIGHTING GRADE by time of day: warm sun glow (Day), orange sky tint (Evening), cool tint plus floodlight glow (Night). Updates when the time of day changes.
- Vignette, horizon haze, and in BROADCAST style a top/bottom shade.
- Crowd camera flashes in the stands (Broadcast style, Medium/High quality, Evening/Night, off under Reduced Motion).
- AUTO QUALITY: if Graphics is AUTO and the average FPS stays under 45 for 5 seconds, quality drops one level with a toast.
- Settings > GRAPHICS STYLE: Classic / Broadcast and a FINISHING PASS on/off switch.
- Not changed: player bodies, bat and stump models, pitch cracks (still the V48 art).
- Version V49, cache cp-v49.

## Test checklist V49
- Start Practice in Day, Evening and Night: the look changes and the HUD stays readable.
- Settings: switch Classic/Broadcast and turn FINISHING PASS off/on.
- Play a few balls on a low-end phone: no stutter; with Graphics AUTO, a quality-lowered toast may appear.

## Changelog V48
- NEW DASHBOARD: hero with a big PLAY / CONTINUE IPL button (tinted by your IPL team), profile strip (matches, wins, career runs, wickets), level + XP bar, game-mode cards (Quick, Chase, Super Over, PvP, IPL, Practice, God, How to play), last-match card with REMATCH, and a bottom nav (Home, Play, Stats, Teams, Settings).
- QUICK PLAY SHEET: tapping Quick, Chase or Super Over opens one bottom sheet for overs, difficulty and time of day, then START.
- XP is computed from real data: career runs + 20 per wicket + 50 per win.
- BOWLING: a variation ball now needs 2 balls to recharge when you bowl (shows VARIATION RECHARGING).
- Version V48, cache cp-v48.

## Test checklist V48
- Home: every card opens its mode; PLAY MATCH opens the sheet; START begins the match.
- Bottom nav: Stats, Teams, Settings open and come back to the dashboard.
- Finish a chase: the last-match card shows WON/LOST and REMATCH works.
- Bowl in Chase: pick VARIATION twice in a row; the second shows VARIATION RECHARGING.
- Check at 360x640 portrait and landscape: no overlap, no sideways scroll.

## Changelog V47
- BOWLER STAMINA: bowlers tire as a spell goes on (and across a long over). Tired bowlers lose accuracy and pace and bowl loose balls (marked LOOSE). Live stamina bar shown while you bowl or in PvP.
- DEW: at night in the second innings, bowlers lose grip (less accuracy, less turn) and balls are marked DEW.
- PREDICTABILITY PENALTY: playing the same shot 3+ times in a row cuts its power (PREDICTABLE banner). Mix your shots.
- CAREER STATS (Settings > CAREER STATS): runs, balls, SR, 4s, 6s, dots, wickets, economy, from real ball results (solo modes; not PvP/Practice). Reset button included.
- Settings: FPS COUNTER, REDUCED MOTION (stops screen shake).
- Version label V47, service-worker cache cp-v47.

## Test checklist V47
- Settings: toggles work; CAREER STATS opens and BACK returns.
- Bowl a Chase match: stamina bar falls over the over; LOOSE balls appear when low.
- Hit the same shot 4 times: PREDICTABLE banner shows and the ball travels less far.
- Quick, Chase, Super Over, PvP, IPL, Practice, God Mode still start and finish.

## Changelog V46
- NEW TEAM: Chennai Super Kings (CSK, yellow kit) joins SRH and RCB. On the Player vs Player screen pick each player's team (SRH / RCB / CSK); picking a team the other player has swaps them. Kits, scoreboards, labels and AI bowlers follow the choice and it is remembered.
- NAME PROMPT: every batter who walks in (both openers and each new batter after a wicket) gets a "Change player name?" card. Save, Keep, Enter or Esc. The match freezes while it is open and the name is stored in Teams & Players. Untick "Ask for every new batter" (or use Settings > Name prompt) to turn it off.
- Milestones: 25 (short games), 50 and 100 banners, 30/50/100 partnership banners, crowd cheer and LED flash.
- Haptics on four, six and wicket (Settings > Haptics).
- Team-colour accent bar across the top for the batting side.

## Changelog V45
- PAUSE (Ⅱ / ▶) and EXIT (✕) buttons, top-right under the score bar, visible during every match. Exit asks for confirmation. Esc or P also pauses.
- PvP fix: the bowler shown (top bar and stadium scoreboard) now always comes from the fielding team, so RCB batting shows SRH bowlers and SRH batting shows RCB bowlers.

## Changelog V44
- Stadium scoreboard: a white board in the stands showing the batting team, score/wickets, overs, both batters (runs, balls, SR), the bowler's figures, this over's balls, and CRR or NEED-OFF in a chase.
- `CP.V44.show(false)` hides it, `CP.V44.show(true)` shows it again.

## Changelog V43
- Crowd camera flashes in the stands (more at night and after boundaries).
- Kits get a side stripe down both flanks.
- Projected score chip when batting first (from the 2nd over).
- Chase tension: "NEED x OFF y" banner each ball in the last two overs.
- `CP.V43.flash()` triggers the flashes for testing.

## Changelog V42
- Boundary impact: sixes and fours kick the screen, flash the LED ribbon, pulse a gold glow and fire the crowd.
- Wickets give a short screen kick and LED flash.
- Over summary after every over (runs, dots, wickets) and a team milestone banner every 50 runs.
- `CP.V42.kick(true)` fires the six effect for testing.

## Changelog V41
- Players: waistband, rim light, collar, chest logo, back numbers, red grip tape, bat toe shading and sticker.
- Stadium: roof canopy with lit lip, animated LED ribbon along the rope, horizon haze, anamorphic floodlight streaks at night.
- Batting view: lower, closer, tighter camera with a gentle push-in while the bowler delivers.
- Gameplay: RHYTHM combo (3 well-timed attacking shots in a row = small contact bonus), PRESSURE meter (3 dots in a row, then a well-timed shot is rewarded). Resets on a wicket or mistimed shot.
- `CP.V41.set(rhythm,dots)` exists for testing.

## Changelog V40
- Graphics: softer sight-screens (no more glaring white block), soft glow halo around the ball so it reads against crowd and sky.
- HUD: momentum meter moved to the top-right (no longer hidden under the joystick); pitch/field info strip fades after 2 balls.
- Gameplay: timing feedback on every shot (PERFECT / GOOD / OKAY / MISTIMED) with boundary distance.
- Gameplay: FOCUS meter. Three perfect-timed attacking shots arm a POWER SHOT: your next attacking shot is guaranteed to fly. Resets on a mistimed shot or a wicket.
- `CP.V40.setFocus(pips, armed)` exists for testing.

## Test checklist
- Quick match: hit with good timing, see the label + FOCUS pips fill; after 3, "POWER SHOT READY"; next attacking shot is a six.
- Mistime a shot: pips reset. Lose a wicket: pips reset.
- Chase, Super Over, Practice, PvP, IPL career, God Mode still start.
