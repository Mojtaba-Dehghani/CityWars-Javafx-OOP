# ⚔️ City Wars: Tokyo Reign — JavaFX Edition

<div align="center">

[![Java Version](https://img.shields.io/badge/Java-17%2B-ED8B00?style=for-the-badge&logo=openjdk&logoColor=white)](https://www.oracle.com/java/)
[![JavaFX](https://img.shields.io/badge/JavaFX-21-FF6F00?style=for-the-badge&logo=java&logoColor=white)](https://openjfx.io/)
[![Architecture](https://img.shields.io/badge/Architecture-MVC%20%2F%20OOP-00599C?style=for-the-badge)](https://en.wikipedia.org/wiki/Model%E2%80%93view%E2%80%93controller)
[![Sharif University](https://img.shields.io/badge/Sharif%20University-CE%20Department-003366?style=for-the-badge)](http://ce.sharif.edu/)
[![License](https://img.shields.io/badge/License-MIT-green?style=for-the-badge)](LICENSE)

**A high-stakes, cyberpunk tactical card battler implemented with pure Object-Oriented Programming and modern JavaFX UI.**

[Key Features](#-key-features) • [Game Modes](#-game-modes) • [Architecture](#-architecture--oop-design) • [Installation](#-installation--running) • [Card System](#-card--spell-mechanics) • [Admin Console](#-admin-management-system)

</div>

---

## 📖 Overview

**City Wars: Tokyo Reign** is an advanced tactical card battle game built from the ground up as a comprehensive term project for the **Object-Oriented Programming (OOP)** course at **Sharif University of Technology**. 

The project demonstrates clean OOP principles, design patterns, separation of concerns (MVC architecture), interactive graphical user interfaces (JavaFX + Scene Builder), persistent data management, real-time animation loops, and intelligent bot algorithms.

Originally engineered as a robust command-line interface (Phase 1) and subsequently transformed into an immersive, cyberpunk-themed desktop application (Phase 2), the game delivers strategic duel mechanics, multi-mode gameplay, an in-game card marketplace, player progression systems, and complete administrator capabilities.

---

## ✨ Key Features

### 🎮 Dynamic Tactical Combat
* **21-Slot Dual-Track Board:** Battle across parallel tracks with cards spanning customizable duration widths ($1$ to $5$ slots) and targeted lane placements [cite: 3, 4].
* **Synergy & Character Buffs:** Selecting one of the 4 specialized characters yields character-card type synergies, boosting Player Damage and providing strategic advantages [cite: 3, 4].
* **Simultaneous Timeline Sweeper:** Animated timeline sweeps sequentially across the board at the end of each combat round, resolving card clashes, dealing player damage, and dynamically recalculating HP bars in real-time [cite: 3, 4].
* **Interactive Hit-Bar Mini-Game:** Precision-based timing reflex bar (Progress/Ring indicator) triggers dynamically during combat, granting critical bonus damage when timed perfectly [cite: 3].
* **Dynamic Board Destruction:** Block destruction hazards, hole manipulation, and lane repair mechanics keep matches unpredictable [cite: 4].

### 👤 Account & Player Economy
* **Secure Authentication:** Regex validation, strong password requirements, math-based & ASCII-art noise CAPTCHAs, and security question password recovery [cite: 4].
* **Brute-Force Defense:** Exponential lock-out countdown penalty timer ($5 \times n$ seconds cooldown) upon repeated failed login attempts [cite: 3, 4].
* **Progression System:** Level-up curve, XP milestones, coin rewards, starter pack gifting ($20$ random cards upon first login), and dynamic maximum HP scaling [cite: 3, 4].
* **Combat History & Leaderboard:** Detailed match analytics (date, rival name, level, outcome, rewards/penalties) featuring pagination and multi-column sorting (date, win/loss, level, alphabetically) [cite: 3, 4].

### 🛒 Card Marketplace & Upgrade Engine
* **Deck Exploration:** Live inventory categorized into *Unlocked* (owned) and *Locked* (available for purchase) cards with visual badges [cite: 1, 3].
* **Multi-Tier Card Upgrades:** Upgrade card stats (Attack, Defense, Duration, Player Damage) using accumulated coins, governed by player level prerequisites and compounding cost multipliers ($1.25\times$) [cite: 3, 4].

### 🛠️ In-Game Content Management (Admin CMS)
* **Custom Card Creator:** Add regular cards on the fly by defining custom attributes (Name, ATK/DEF values, Duration, Player Damage, Upgrade Level & Cost) [cite: 3, 4].
* **Asset Uploader:** Upload custom card artwork directly from local storage or select from curated cyberpunk asset presets [cite: 1, 3].
* **Real-time Card Editing & Deletion:** Live in-place attribute modification with input validation, plus safety confirmation dialogues for card deletion [cite: 3, 4].
* **Player Analytics Monitor:** Global player overview tracking user levels, wealth, and statistics [cite: 3, 4].

---

## 🕹️ Game Modes

```
+-----------------------------------------------------------------------+
|                              GAME MODES                               |
+-------------------+-------------------+---------------+---------------+
| 👥 1v1 PvP Duel   | 💰 High-Stakes    | 🤖 Campaign   | 🛡️ Clan Wars  |
| Local turn-based  | Wager coin pots   | 5-Stage Story | Form clans,   |
| character battles | Winner takes all  | 4 Bots + Boss | group battles |
+-------------------+-------------------+---------------+---------------+
```

### 1. 👥 Local 2-Player Versus (PvP)
* Local hot-seat multiplayer where Player 2 logs into the match session [cite: 3, 4].
* Character selection screen with unique card decks and aesthetic profiles [cite: 3, 4].
* Flexible card placement controls: **Drag-and-Drop**, **Click-to-Place**, or **Coordinate Text Input** [cite: 1, 3].
* Automatic hand replenishment with guaranteed spell-to-attack card ratio balancing [cite: 4].

### 2. 💰 High-Stakes Wager Mode (Betting)
* Competitive mode requiring identical coin buy-in from both contenders [cite: 3, 4].
* Balance validation before match initiation [cite: 2, 4].
* **Winner Takes All:** The victor claims the entire consolidated coin pool upon victory [cite: 3, 4].

### 3. 🤖 Single-Player Campaign (AI & Boss Fight)
* **Interactive Level Map:** Visual stage roadmap tracking player progression through 5 distinct tiers [cite: 3].
* **State Persistence (Save & Resume):** Automatically saves campaign progress; players can return and `Continue Last Game` at any time [cite: 3, 4].
* **Challenging AI Bots:** 4 tiered AI opponents with contextual spell casting and placement heuristic algorithms [cite: 2, 4].
* **Unique Boss Encounter:** The final boss features a pre-filled, high-density card board. In each turn, rather than deploying cards, the boss randomly buffs two cards on its board while concealing individual card damage [cite: 3, 4].

### 4. 🛡️ Clan Warfare (Phase 1 Logic)
* Clan creation, invitation code generation, and member management [cite: 4].
* Inter-clan group tournaments matching members in 1v1 duels, concluding with Clan Leader tie-breakers [cite: 2, 4].

---

## 🪄 Card & Spell Mechanics

Alongside standard combat units, specialized **Spell Cards** manipulate the field without consuming board duration [cite: 4]:

| Spell Type | Icon | Tactical Effect |
| :--- | :---: | :--- |
| **Shield (سپر)** | 🛡️ | Instantly breaks and nullifies any opposing card regardless of incoming damage [cite: 4]. |
| **Heal (شفا)** | 💖 | Restores player HP; immune to enemy breaking spells [cite: 4]. |
| **Power Buff (افزایش قدرت)** | ⚡ | Randomly buffs the attack/defense rating of one deployed card [cite: 4]. |
| **Hole Mover (تغییر مکان حفره)** | 🕳️ | Relocates destroyed block hazards on both lanes without altering occupied cards [cite: 4]. |
| **Repairer (تعمیر کننده)** | 🔧 | Repairs destroyed blocks, restoring full track availability [cite: 4]. |
| **Round Reducer (کم کننده راند)** | ⏳ | Decreases total match rounds, accelerating match termination [cite: 4]. |
| **Card Steal (حذف کارت حریف)** | 🎴 | Steals a random card from the opponent's hand for the active round [cite: 4]. |
| **Card Weaken (تضعیف کارت)** | 📉 | Randomly reduces damage on one opponent card and defense on another [cite: 4]. |
| **Duplicator (کپی کننده)** | 📑 | Clones an existing card in hand, granting temporary 6-card hand advantage [cite: 4]. |
| **Cloak / Hider (مخفی کننده)** | 🌫️ | Conceals and shuffles the opponent's card hand for the following round [cite: 4]. |

---

## 🏛️ Architecture & OOP Design

The project enforces clean separation of concerns and industry-standard Object-Oriented principles:

```
src/
├── model/                  # Pure Business Logic & Domain Entities
│   ├── auth/               # User, Admin, Security, Credentials
│   ├── card/               # Card (Normal/Spell), Deck, Character, CardType
│   ├── game/               # GameBoard, Block, RoundState, Timeline, HitBar
│   ├── campaign/           # LevelMap, BotAI, BossFight
│   └── economy/            # Shop, Inventory, Wallet, LevelManager
├── controller/             # Event Handlers & State Management
│   ├── AuthController.java
│   ├── MainMenuController.java
│   ├── BattleController.java
│   ├── ShopController.java
│   ├── AdminController.java
│   └── HistoryController.java
├── view/                   # JavaFX FXML Views & Styling
│   ├── fxml/               # Login, MainMenu, BattleArena, Shop, Admin, Map
│   ├── css/                # Cyberpunk theme stylesheets, Neon accents
│   └── assets/             # Card arts, Character sprites, SFX, BGM
└── util/                   # Helpers: CaptchaGenerator, DatabaseManager, SoundManager
```

### Applied Design Patterns
* **MVC (Model-View-Controller):** Strict decoupling between graphical presentation (`FXML/CSS`), user input handling (`Controllers`), and game state rules (`Models`).
* **Factory Pattern:** Polymorphic creation of regular combat cards, special spells, and AI bot profiles.
* **Strategy Pattern:** Interchangeable decision-making behaviors for AI bots across campaign tiers.
* **Observer Pattern:** Event-driven UI updates for real-time timeline motion, HP reduction animations, and sound triggers.
* **Singleton Pattern:** Centralized management for `SoundManager`, `DatabaseConnection`, and `CurrentSession`.

---

## 🚀 Installation & Running

### Prerequisites
* **Java Development Kit (JDK):** Version 17 or higher
* **JavaFX SDK:** Version 21+ (if not using Maven/Gradle plugins)
* **Build Tool:** Maven 3.8+ or Gradle 8.0+

### 1. Clone the Repository
```bash
git clone https://github.com/<your-username>/city-wars-tokyo-reign.git
cd city-wars-tokyo-reign
```

### 2. Build & Run with Maven
```bash
# Clean and run the JavaFX application
mvn clean javafx:run
```

### 3. Build & Run with Gradle
```bash
# Run using Gradle wrapper
./gradlew run
```

---

## 🎨 UI Showcase & Polish

* **Adaptive Audio Engine:** Dynamic background music (BGM) selector, sound effect volume control, and mute toggle [cite: 1, 3].
* **Cyberpunk Aesthetics:** Neon glows, dark-mode styling, dynamic progress indicators, and customizable UI themes [cite: 1, 3].
* **Responsive Dialogs:** Toast alerts, error tooltips, countdown overlays, and reward fanfare popups [cite: 3].

---

## 👥 Authors & Academic Context

Developed as the Final Term Project for the **Object-Oriented Programming (OOP)** Course:
* **Instructors:** Dr. Hashemi, Dr. Vosooghi Vahdat [cite: 3, 4]
* **Institution:** Department of Computer Engineering, **Sharif University of Technology** [cite: 3, 4]

---

<div align="center">
  <sub>Engineered with ❤️ and Java by Sharif University CE Students.</sub>
</div>
