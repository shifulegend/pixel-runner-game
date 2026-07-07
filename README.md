# Pixel Runner

A browser-based endless runner game built with vanilla JavaScript and HTML5 Canvas — no external dependencies or libraries. All visuals (character, enemies, barrel, bushes) are original artwork drawn procedurally in code.

## Play It

Open `index.html` directly in any modern browser (Chrome recommended), or enable GitHub Pages on this repo (Settings → Pages → Deploy from `main` branch) to play it live at a public URL.

## Gameplay

- **Auto-run**: The main character continuously runs to the right with an animated leg-swing, rendered at a closer, larger camera view for better visibility.
- **Jump control**: Tap/click or press Space to jump. A short tap gives a short hop; holding longer (up to ~320ms) gives a longer, higher jump.
- **Enemies**: Small enemies (half the main character's height) approach from the right. Jump on top to squash them for **+100 score**; colliding into them sideways ends the run.
- **Pits**: Gaps appear in the ground that must be jumped over — falling into one is an instant game over.
- **Bushes**: Stationary bushes block the path. Getting stuck on one (failing to clear it) triggers the chasing spiked barrel, which kills the player if not freed in time.
- **Spiked barrel chaser**: Visible at ~1/3 size on the far-left edge of the screen at all times, rolling continuously. It only surges forward and catches the player if they get stuck on a bush.
- **Score**: Starts at `00000` (top-right HUD) and increases continuously over time, scaled to the current speed multiplier, plus a flat +100 bonus per enemy killed.
- **Difficulty scaling**: Game speed ramps smoothly from 1x to 2x over the first 5 minutes, then from 2x to 3x over the next 5 minutes, and holds at 3x indefinitely afterward. Score accrual rate scales proportionally with speed.

## Tech Notes

- Pure HTML/CSS/JavaScript, single self-contained file (`index.html`) — no build step, no npm install, no server required.
- Rendering via HTML5 Canvas 2D API; all sprites (player, enemy, barrel, bush) are original, procedurally drawn shapes — not licensed third-party assets.
- Physics: simple gravity + variable-height jump via hold-duration sampling.
- Fully responsive — canvas resizes to the browser window on load and on resize events.

## Repository Structure

This repo was bootstrapped from the [golden-template](https://github.com/shifulegend/golden-template) and follows its documentation-first, AI-agent-friendly conventions (see `docs/ai/` for project memory, `CLAUDE.md`/`AGENTS.md`/`gemini/GEMINI.md` for cross-tool AI instructions).

| Path | Purpose |
|------|---------|
| `index.html` | The complete game — open this file to play |
| `docs/ai/` | Canonical project memory (overview, architecture, decisions, mistakes log) |
| `docs/SETUP.md` | First-time setup guide |
| `.github/` | Copilot instructions, CI workflow, Dependabot config |
| `.claude/`, `.agents/`, `gemini/` | Cross-tool AI agent instructions (Claude Code, Antigravity, Copilot) |

## License

MIT — see `LICENSE`. All game assets are original works created for this project.
