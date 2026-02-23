[README.md](https://github.com/user-attachments/files/25475346/README.md)
# Pressure Protocol

A 2D career exploration game where you step into high-pressure professions and see if you can handle the heat. Navigate a cyberpunk hub world, choose a career, pick your difficulty, and survive your shift.

## Careers

### ER Doctor (Showcase Career)
Run a busy emergency room. Triage patients by severity (GREEN/YELLOW/RED), perform multi-step treatments with interactive micro-tasks (hold-stable, timing-tap, sequence), manage critical stabilization countdowns, and deal with random ER events like ambulance surges, equipment delays, and patient panic.

### Financial Analyst — Trading Floor
Execute trades on a fast-moving trading floor using a 3-step Confirm Chain system. Hit timing bars, manage risk checks, and chase the "IN THE ZONE" streak bonus. Watch out for curveballs like breaking news spikes and fakeout moves.

### Chef Rush
Run a top-down kitchen under pressure. Prep ingredients, cook dishes, plate them up, and serve orders before time runs out. Menus scale with difficulty — from burgers and fries up to sushi and steak.

### Lawyer — Objection Rush
Defend your client in a courtroom showdown. Pattern-match objections, build your case, and keep the pressure from overwhelming you.

## Features

- **3 Difficulty Levels** — Easy, Medium, and Hard for every career, each with unique settings for timers, spawn rates, penalties, and pressure curves
- **Shared Pressure System** — A universal stress meter that rises from pending tasks, mistakes, and patient/order failures. Push past Critical (70+) and you're in trouble. Hit 100 and it's game over
- **Shift Briefing** — Every run starts with a mission briefing showing objectives, win/fail conditions, controls, and pressure rules
- **Shift Report** — Post-game breakdown with 5 outcome tiers (Star Shift down to Shift Failed), performance metrics, highlights, and tips
- **Career Records Board** — Track your best outcomes across all 4 careers and 3 difficulties
- **Pause Menu** — ESC to pause anytime, with resume, restart, and return-to-hub options
- **Debug Overlay** — Press backtick (`) for live pressure/state readouts

## Tech Stack

- **Frontend:** React, TypeScript, Vite, Tailwind CSS, shadcn/ui
- **Rendering:** HTML5 Canvas (procedural — no sprites or external art)
- **Backend:** Node.js, Express, PostgreSQL, Drizzle ORM
- **State:** React hooks — all game logic runs client-side

## Getting Started

1. Install dependencies:
   ```
   npm install
   ```

2. Start the development server:
   ```
   npm run dev
   ```

3. Open the app at `http://localhost:5000`

## Controls

| Action | Keys |
|--------|------|
| Move (Hub) | WASD or Arrow Keys |
| Interact | Click / On-screen buttons |
| Pause | ESC |
| Debug Overlay | Backtick (`) |

## Project Structure

```
client/src/
  pages/game.tsx          — Main game component (all screens)
  components/
    er-game-module.tsx    — ER Doctor gameplay
    trading-floor-module.tsx — Financial Analyst gameplay
    chef-game-module.tsx  — Chef Rush gameplay
    lawyer-game-module.tsx — Lawyer gameplay
    SimulationSelect.tsx  — Difficulty selection screen
    PreBrief.tsx          — Shift briefing screen
    ShiftReport.tsx       — Post-game results screen
    CareerRecords.tsx     — Best outcomes tracker
    PauseMenu.tsx         — Pause overlay
    SharedHUD.tsx         — Pressure bar and timer HUD
  config/
    simulationConfig.ts   — Difficulty configs and scenarios
server/
  index.ts               — Express server entry point
  routes.ts              — API routes
  storage.ts             — Database storage interface
shared/
  schema.ts              — Drizzle ORM schema
```
