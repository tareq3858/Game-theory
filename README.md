# Nuclear Standoff — Game Theory

A 9-player round-robin Prisoner's Dilemma. You face 8 anonymous nations, each running a hidden strategy. 5 rounds per nation, 36 matchups total. Highest score wins.

Built as a single-file React app (no build step) so it can be hosted on GitHub Pages with zero setup.

## Play locally

Open `index.html` in any modern browser. That's it — no install, no server.

## Publish to GitHub Pages

Once published, anyone can play at `https://<your-username>.github.io/<repo-name>/`.

1. Create a new repository on GitHub (e.g. `nuclear-standoff`).
2. From this folder, push the files:
   ```bash
   git init
   git add .
   git commit -m "Initial commit"
   git branch -M main
   git remote add origin https://github.com/<your-username>/<repo-name>.git
   git push -u origin main
   ```
3. On GitHub: **Settings → Pages**.
4. Under **Build and deployment**, set:
   - **Source:** Deploy from a branch
   - **Branch:** `main` / `/ (root)`
5. Save. Wait ~1 minute. The page URL will appear at the top of the Pages settings.
6. Share the URL with anyone. No login required to play.

## How to play

1. Pick your nation and type your name.
2. Each round, choose **Trade** (cooperate) or **Strike** (attack) against the current opponent.
3. Scoring (Prisoner's Dilemma):
   - Both Trade → +3 / +3 — mutual prosperity
   - You Strike, they Trade → +5 / 0 — sucker punch
   - You Trade, they Strike → 0 / +5 — betrayed
   - Both Strike → +1 / +1 — mutual ruin
4. Bot opponents appear under random country names. Real strategy names are revealed only after the tournament ends.
5. Opponents rotate randomly between rounds, so you can't fingerprint a strategy by playing 10 straight against the same agent.
6. Live leaderboard updates every round. Background nation-vs-nation matchups also advance with each move you make.
7. ~10% of all moves misfire — even loyal hawks. Reputations form after three observed moves and are noisy.

## Hidden agents

Behind the country names, the 8 strategies are: Suspicious Tit for Tat, Tit for Tat, Prober, Hawk, Random, Grudger, Pavlov, Generous Tit for Tat. Identities are revealed on the final results screen.

## Files

- `index.html` — entire game (React + Tailwind via CDN, no build tools)
- `.nojekyll` — tells GitHub Pages to serve files as-is
- `README.md` — this file
