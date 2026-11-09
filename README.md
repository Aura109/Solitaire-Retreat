# Solitaire Retreat 🃏✨

Solitaire Retreat is a modern, feature-rich 2D mobile adaptation of the classic Klondike Solitaire built from the ground up for Android using **Godot 4.7.1**. 

Designed with an engaging progression loop, players complete daily tasks and unique challenges to earn coins, unlocking an array of aesthetic customizations—including unique card styles, custom borders, and dynamic card trail effects.

> 🔒 **Source Code Notice:** The source code for this project is private to protect production assets and proprietary logic. This repository serves as a public portfolio showcase, architecture breakdown, and testing portal.

---

## 🚀 Join the Closed Beta Test (Android)

Solitaire Retreat is currently in its official Google Play Closed Testing phase. Follow these steps to join the active testing track:

1. **Join the Tester Group:** [Click Here to Join the Google Group](https://groups.google.com/g/solitaire-retreat-closed-test) using the same Google Account associated with your Android device.
2. **Opt-in as a Tester:** Once joined, access the web opt-in link here: [Become a Tester on Google Play](https://play.google.com/apps/testing/com.sharmaprojectsgames.solitaireretreat)
3. **Download the App:** Download the game directly onto your Android device via the [Google Play Store](https://play.google.com/store/apps/details?id=com.sharmaprojectsgames.solitaireretreat).

*Found a bug or have feedback? Please open a GitHub Issue in this repository!*

---

## 🌟 Core Gameplay & Mechanics

* **Classic Klondike Engine:** Perfectly tuned drag-and-drop mechanics built around Godot's built-in `Control` nodes, `CollisionObject2D`, and precise viewport scaling.
* **Progression Loop:** Integrated dynamic Daily Tasks and Milestone Challenges providing continuous player retention.
* **Cosmetic Economy:** In-game currency system allowing players to purchase and apply:
  * Distinct card back skins and modern vector-art faces.
  * Custom glowing and styled card borders.
  * Specialized particle and shader-based card trail effects for satisfying card movements.

---

## ⚙️ Tech Stack & Mobile Architecture

* **Engine:** Godot Engine 4.7.1 (GDScript)
* **Target Platform:** Android (Mobile Portrait Orientation optimized)
* **Ad Monetization:** Implemented `Poing Studios AdMob Plugin` for seamless banner and interstitial test/production ad tracking without performance drops.
* **UI/UX Framework:** Adaptive rendering system leveraging `AtlasTexture` slicing and fluid structural scaling across modern display aspect ratios.
* **State Management:** Custom secure local save-state serialization handling game history, coin balances, unlocked shop assets, and daily challenge streaks.

---

## 📂 Architecture Overview

To maintain performance on lower-end mobile devices while executing heavy visual card movements, the node layout utilizes a decoupled state-and-view model:

```text
📦 SolitaireRetreat (Project Root)
 ┣ 📂 Scenes/
 ┃ ┣ 📄 Table.tscn          # Main game canvas and card stack layout manager
 ┃ ┣ 📄 Card.tscn           # Reusable card unit with custom collision & scaling
 ┃ ┗ 📄 MainMenu.tscn       # Profile shop UI, daily task tracker, settings
 ┣ 📂 Scripts/
 ┃ ┣ 📄 GameController.gd   # Solitaire rule validation engine (Klondike Logic)
 ┃ ┣ 📄 Card.gd             # Smooth lerping logic, trail triggers, drag tracking
 ┃ ┣ 📄 AdManager.gd        # Wrapper handling Poing AdMob lifecycle signals
 ┃ ┗ 📄 SaveSystem.gd       # JSON-based localized save/load system
 ┣ 📂 Shaders/
 ┃ ┗ 📄 CardTrail.gdshader  # Low-overhead canvas item shaders for custom paths
 ┗ 📄 project.godot
```

---

## 📈 Development Showcase & Visuals

### 📸 Gameplay Screenshots

| Main Game Board | Customization Shop | Daily Challenges |
| :---: | :---: | :---: |
| ![Board Placeholder](https://placeholder.com) | ![Shop Placeholder](https://placeholder.com) | ![Challenges Placeholder](https://placeholder.com) |

---

## 🛠️ Upcoming Roadmap
- [ ] Implement Google Play Games Services for cloud saves and global achievements.
- [ ] Add a performance toggle for dynamic card trails on legacy Android builds.
- [ ] Introduce a smart-solve engine to verify if a dealt deck is winnable.
