# 🏭 SmokeStack ReIgnited

![Version](https://img.shields.io/badge/Minecraft-1.20.1-brightgreen) ![Loader](https://img.shields.io/badge/Forge-47.2.0+-orange) ![Status](https://img.shields.io/badge/Status-Active-blue)

**A cooperative expert survival experience featuring a dynamic world border, stage-locked progression, and industrial automation.**

SmokeStack ReIgnited is designed to shatter the "rush-to-endgame" meta. This pack forces players to collaborate to expand their world, unlock technology through distinct eras, and survive an environment that grows more hostile over time.

---

## 📂 Repository Structure

This repository is organized into two distinct environments to ensure separation of client-side visuals and server-side logic.

```text
smokestack-reignited/
├── client-pack/       # Client-side overrides (Shaders, Maps, Keybinds)
├── server-pack/       # Server-side logic (Scripts, Properties, KubeJS)
└── README.md          # Documentation
```

*   **`client-pack/`**: Contains the mods, configs, and resource packs intended for the player. Includes performance mods (Embeddium/Oculus) and visual tweaks (JourneyMap).
*   **`server-pack/`**: Contains the dedicated server files. This includes the heavy logic scripts (KubeJS) for the death system and progression locks, as well as server-optimized configs.

---

## 🎮 Key Features

### 🌎 Dynamic World Border
The world begins as a **500x500 block** area.
*   **Expansion:** The border radius increases by **1,000 blocks** for every unique player that joins.
*   **Goal:** Forces cooperation and neighborhood building.

### 💀 "Checkpoint" Death System
A custom **KubeJS** script inspired by *Dark Souls*.
1.  **Save:** Right-click a bed to save your inventory as a "Checkpoint."
2.  **Die:** You instant-respawn with your saved gear.
3.  **Risk:** Any *new* items found since your last sleep are dropped on your corpse.

### 🔒 Era-Based Progression
Progression is gated using **Game Stages** and **FTB Quests**.
*   **Stone Age:** Vanilla survival. No Nether. No Diamond gear.
*   **Industrial Age:** Unlocked via quests. Grants access to **Create** machinery and the Nether.
*   **Exploration Age:** Unlocks the End and Elytra travel.

---

## 🛠️ Installation Guide

### For Players (Client)
1.  **Prerequisites:** Install Minecraft Forge 1.20.1 (Version 47.2.0 or higher).
2.  **Import:**
    *   Copy the contents of the `client-pack/` folder into your Minecraft '.minecraft/mods/' folder.
3.  **Java:** Ensure you are running Java 17.

### For Server Admins
1.  **Setup:**
    *   Install a standard Forge 1.20.1 Server.
    *   Copy the contents of `server-pack/` into the server root.
2.  **Pre-Generation (Crucial):**
    *   Before allowing players to join, run the console command: `chunky start`
    *   *Note:* The server comes with **Chunky** installed to prevent lag during border expansion.
3.  **Java Arguments:**
    *   We recommend using **GraalVM Enterprise (Java 17)** for maximum performance with **Create** and **MineColonies**.

---

## 📝 Custom Scripts & Logic

This modpack relies heavily on custom scripts found in `server-pack/kubejs/`.

*   **`death_mechanic.js`**: Handles the NBT data storage for the inventory checkpoint system.
*   **`progression.js`**: Manages dimension entry events (locking Nether/End) and item usage restrictions.
*   **`dynamicborder-common.toml`**: Configures the player-count scaling math.

---

## 📜 License & Credits

*   **Modpack Assembly:** [Your Name/Username]
*   **Scripts:** Custom KubeJS scripts provided in this repo are open for use/modification.
*   **Mods:** All mods belong to their respective authors. Please support them on CurseForge/Modrinth.

**Server Origin:** dedicated to the "Smoke Stack" PC that burned down, giving this project its name.
