# PLAYVERSE 2.0 — FULL MULTIPLAYER GAMING PLATFORM

Welcome to **PLAYVERSE 2.0**, a complete, vibrant, and professional browser-based multiplayer gaming platform. PLAYVERSE features 10 distinct, fully-playable mini-games, real-time multiplayer lobbies with custom room codes, intelligent AI bots (Easy, Normal, Hard), persistent player profiles, competitive MMR rankings, unlockable cosmetics, and mobile/laptop responsive controls.

---

## 🎮 10 PLAYABLE MINI-GAMES

1. **Battle Arena**: Colorful top-down gladiatorial arena battle. Slash attacks, ranged plasma bolts, energy shields, obstacles, team scoring (Blue vs Red or 1v1).
2. **Mini Football**: Fast-paced arcade soccer. Ball physics with velocity, bounce, friction, player kicking mechanics, goal net celebrations, and kickoff restarts.
3. **Turbo Racing**: High-octane arcade drift racing. Car steering, acceleration, braking, track boundaries, 3 laps, checkpoints, minimap, and AI rivals.
4. **Jump Masters**: Competitive platformer race. Double jumping, floating and moving platforms, golden coin grabs, falling respawns, and finish line flag.
5. **Tank Clash**: Tactical neon tank battle. Hull steering, rotating turrets, bouncing plasma shells with wall ricochets, destructible crates, and team scores.
6. **Air Hockey**: Ultra-responsive arcade air hockey table. Realistic frictionless puck bounce physics, mallets, goal slots, first to 7 points, and local shared-device 2P mode.
7. **Smart Battle**: Speed trivia quiz arena with randomized questions across science, games, and culture in Uzbek (default), English, and Russian with combo streak bonuses.
8. **Obstacle Rush**: Multiplayer wipeout obstacle course. Giant swinging sledgehammers, rotating laser beams, checkpoints, and sprint to the finish banner.
9. **Target Masters**: Precision arcade shooting gallery with moving drones, golden bonus targets, hazard bombs, accuracy tracking, and combo multipliers.
10. **Last Player Standing**: Battle Royale survivor arena with shrinking toxic storm zone, powerup crates (speed boost, medkit, blasters), and final survivor victory royale!

---

## 🚀 TECHNOLOGY STACK

- **Frontend**: React 19, TypeScript, Vite, HTML5 Canvas game engines, Socket.IO client, Web Audio API sound synthesizer, Lucide icons, Canvas-Confetti.
- **Backend**: Node.js, Express, TypeScript, Socket.IO, Prisma ORM with SQLite (zero-setup local run) and PostgreSQL production ready, bcryptjs password hashing, JWT session authentication.
- **Audio**: Built-in Web Audio API sound engine providing clicks, jump, shoot, goal, powerup, victory fanfare, defeat, level up, and ambient synth loops with 0 external download dependencies.
- **Localization (i18n)**: Uzbek (`uz`, default), English (`en`), and Russian (`ru`).

---

## 📂 DIRECTORY STRUCTURE

```
PLAYVERSE/
├── package.json              # Root script orchestration
├── .env.example              # Environment variables template
├── README.md                 # Full project documentation
├── server/
│   ├── package.json
│   ├── tsconfig.json
│   ├── prisma/
│   │   ├── schema.prisma     # Prisma database schema
│   │   └── seed.ts           # Demo players & stats seeder
│   └── src/
│       ├── index.ts          # Express + Socket.IO server entry
│       ├── config.ts         # Environment settings
│       ├── db.ts             # Prisma client instance
│       ├── routes/           # Auth, Users, Friends, Leaderboards, Inventory
│       ├── socket/           # RoomManager, room codes, lobbies, chat, reconnects
│       ├── services/         # Match processing, XP & MMR Elo calculation
│       ├── types/            # Shared TypeScript definitions
│       └── __tests__/        # Unit and multiplayer E2E test suites
└── client/
    ├── package.json
    ├── tsconfig.json
    ├── vite.config.ts
    ├── index.html
    └── src/
        ├── main.tsx
        ├── App.tsx           # Application shell & router
        ├── index.css         # Cyberpunk neon arcade styling & design system
        ├── types/            # Client models & contracts
        ├── i18n/             # Uzbek (default), English, Russian translations
        ├── utils/            # Web Audio API sound synthesizer engine
        ├── context/          # Auth, Socket, Settings, Toast contexts
        ├── components/
        │   ├── layout/       # TopHeader, Sidebar, MobileNav
        │   ├── common/       # VirtualControls (joystick + buttons), AuthModal
        │   ├── game/         # GameHUD, GameOverModal, InstructionsModal
        │   └── lobby/        # LobbyView, RoomCode, TeamSelect, RoomChat
        ├── pages/            # Home, AllGames, PlayOnline, PlayOffline, Friends, Profile, Rankings, Inventory, Settings
        └── games/            # 10 Interactive Canvas Game Implementations
```

---

## ⚙️ INSTALLATION & SETUP

### 1. Prerequisites
- Node.js v18+ or v20+ or v24+
- npm v9+

### 2. Install Dependencies
Run from the root directory:
```bash
npm --prefix server install
npm --prefix client install
```

### 3. Database Setup & Seeding
Initialize the SQLite database and seed demo leaderboards and cosmetics:
```bash
cd server
npx prisma db push
npx tsx prisma/seed.ts
cd ..
```

---

## 🏃 RUNNING THE APPLICATION

### Development Mode (Both Frontend & Backend)
Run simultaneously with one command from the project root:
```bash
npm run dev
```

Or run individually:
- **Server**: `cd server && npm run dev` (Runs on `http://localhost:4000`)
- **Client**: `cd client && npm run dev` (Runs on `http://localhost:5173`)

Open `http://localhost:5173` in your browser.

---

## 🧪 TESTING

### Unit & Integration Tests
Run Vitest tests in the server directory:
```bash
cd server
npm test
```
Tests cover:
- Room creation and distinct code generation
- Joining rooms and rejection of invalid codes
- Room capacity limits
- Reconnection token recovery within grace period
- XP calculations for matches and level progression
- Competitive MMR Elo ratings
- Cosmetic unlock level validation

---

## 📱 CONTROLS GUIDE

### Laptop / Desktop Keyboard:
- **Movement**: `W`, `A`, `S`, `D` or `Arrow Keys`
- **Action 1 (Attack / Kick / Jump / Shoot)**: `SPACE`
- **Action 2 (Shield / Dash / Brake)**: `SHIFT`
- **Pause**: `P`
- **Air Hockey Local 2P**: Player 1 uses `WASD`, Player 2 uses `Arrow Keys`

### Mobile / Tablet Touch:
- **Analog Joystick**: Drag the virtual joystick on the lower left of the screen for 360-degree analog control.
- **Action Buttons**: Tap on-screen action buttons (`SHOOT`, `SHIELD`, `KICK`, `GAS`, `JUMP`) on the lower right.
