# 🌍 Guess the Country

A fun and interactive C++ console-based geography guessing game where players test their knowledge of world countries and their capitals. Built with binary search trees for data organization and featuring multiple difficulty levels, game modes, and a high score system.

---

## 📋 Table of Contents

- [Features](#features)
- [Game Modes](#game-modes)
- [Difficulty Levels](#difficulty-levels)
- [Installation](#installation)
- [How to Play](#how-to-play)
- [Project Structure](#project-structure)
- [Screenshots](#screenshots)
- [Technologies Used](#technologies-used)
- [Team](#team)
- [License](#license)

---

## ✨ Features

- 🎮 **Single Player & Two Player Modes** — Play solo or challenge a friend
- 📊 **Three Difficulty Levels** — Easy, Medium, and Hard with different country sets
- 🌎 **Six Continents** — Asia, Europe, Africa, North America, South America, Oceania
- ⏱️ **Timer System** — 3-minute timer per question to keep the game exciting
- ❤️ **Lives System** — Start with 10 lives, lose one per wrong answer
- 🏆 **Scoring System** — +15 points for correct answers, -5 points for wrong answers
- 🥇 **High Score Tracking** — Persistent high score storage in `score.txt`
- 🔄 **Replayability** — Random continent and country selection for endless fun
- 🚫 **No Repetition** — Countries won't repeat within a single game session
- 🎨 **Emoji Support** — Enhanced console UI with emoji characters
- 📝 **Rules & Credits** — In-game help and team credits sections

---

## 🎮 Game Modes

### Single Player Mode 🧍
Play alone and try to achieve the highest score possible. Compete against your own best scores!

### Two Player Mode 👬
Challenge a friend in a head-to-head competition:
- Players take turns guessing countries
- Both start with 10 lives and 0 points
- The player with the highest score when lives run out wins
- Draws are possible if scores are tied

---

## 📊 Difficulty Levels

| Level | Description | Countries per Continent |
|-------|-------------|------------------------|
| **Easy** 🤙 | Well-known countries with famous capitals | 8-10 countries |
| **Medium** 😨 | Moderately known countries | 6-8 countries |
| **Hard** 😡 | Lesser-known countries and tricky capitals | 5-7 countries |

---

## 🚀 Installation

### Prerequisites
- Windows OS (uses `windows.h` for console features)
- C++ Compiler (g++, MSVC, or Clang)
- [Visual Studio Code](https://code.visualstudio.com/) (recommended)

### Build & Run

```bash
# Clone the repository
git clone https://github.com/yourusername/guess-the-country.git
cd guess-the-country

# Compile with g++
g++ -o guess_country main.cpp

# Run the game
./guess_country.exe
```

### Visual Studio Code Setup
1. Open the project folder in VS Code
2. Install the **C/C++ extension** by Microsoft
3. Press `Ctrl+Shift+B` to build
4. Press `F5` to run with debugging

---

## 🎯 How to Play

### Main Menu
```
GUESS THE COUNTRY 🌏 ✈

1. Start Game ▶
2. How to play 🤔
3. Display Highscore ✨
4. Credits 😎
0. To Quit (Mid-Game too) 🥺
```

### Game Flow
1. **Select Mode** — Choose Single Player or Two Player
2. **Select Difficulty** — Pick Easy, Medium, or Hard
3. **Guess the Country** — A random continent and capital hint will be shown
4. **Enter Your Answer** — Type the country name and press Enter
5. **Score Points** — Correct answers give +15 points, wrong answers cost -5 points and 1 life
6. **Survive** — Game ends when you lose all 10 lives

### Controls
| Input | Action |
|-------|--------|
| `1-4` | Menu selection |
| `0` | Quit game (works anytime) |
| `y/n` | Restart confirmation |
| `b` | Go back to main menu |

### Scoring Rules
- ✅ **Correct Guess**: +15 points
- ❌ **Wrong Guess**: -5 points (minimum 0), -1 life
- 💀 **Game Over**: When lives reach 0
- ⏰ **Idle Timeout**: Game exits after 3 minutes of inactivity

---

## 📁 Project Structure

```
guess-the-country/
│
├── main.cpp              # Main game source code
├── score.txt             # High scores storage (auto-generated)
│
└── README.md             # Project documentation
```

### Code Architecture

```
main.cpp
│
├── Game State (Global Variables)
│   ├── livesPlayer1, livesPlayer2
│   ├── pointsPlayer1, pointsPlayer2
│   ├── currentPlayer
│   └── usedCountries (set for no repetition)
│
├── Node Class
│   └── Binary Tree Node (countryName, capital, left, right)
│
├── Menu Functions
│   ├── gamePage()
│   ├── modeSelection()
│   ├── levelSelection()
│   ├── displayRules()
│   ├── displayHighscore()
│   └── displayCredits()
│
├── Game Logic
│   ├── doublePlayerGame()
│   ├── selectCountry()
│   ├── displayGuessQuestion() [Single Player]
│   ├── displayGuessQuestion() [Two Player - Overloaded]
│   ├── checkRepetition()
│   └── convertToLower()
│
├── Level Controllers
│   ├── playEasyLevel()
│   ├── playMediumLevel()
│   └── playHardLevel()
│
├── Data Trees (18 Binary Trees)
│   ├── Easy:   Asia, Europe, Africa, N.America, S.America, Oceania
│   ├── Medium: Asia, Europe, Africa, N.America, S.America, Oceania
│   └── Hard:   Asia, Europe, Africa, N.America, S.America, Oceania
│
└── Utility Functions
    ├── inOrderTraversalOfNodes()
    ├── displayContinent()
    └── setValues()
```

---

## 🖥️ Screenshots

> *Screenshots will be added here showing:*
> - Main menu with emoji decorations
> - Gameplay with capital hint and lives display
> - Two-player mode with score tracking
> - High score display
> - Game over screen with restart option

---

## 🛠️ Technologies Used

- **C++** — Core programming language
- **Binary Search Trees** — Data structure for country-capital storage
- **STL Containers** — `vector`, `set`, `string`, `algorithm`
- **Windows API** — Console encoding (`SetConsoleOutputCP` for UTF-8 emoji support)
- **File I/O** — Persistent high score storage (`fstream`)
- **Time/Random Libraries** — `ctime`, `cstdlib` for randomization and timers

---

## 👥 Team

**Development Team** 😎

| Name | Role | ID |
|------|------|-----|
| Cybil Fatima 👩🏻 | Developer | SP23-BAI-013 |
| Eman Butt 👩🏻 | Developer | SP23-BAI-014 |
| Esha Alvi 👩🏻 | Developer | SP23-BAI-015 |
| Muhammad Ibtihaj 🧑🏻 | Developer | SP23-BAI-037 |

---

## 📝 Notes

- The game uses **UTF-8 encoding** for emoji display. Ensure your terminal supports it.
- On Windows, the game calls `SetConsoleOutputCP(CP_UTF8)` automatically.
- The `score.txt` file is created automatically in the same directory as the executable.
- Country names are case-insensitive and spaces are ignored during comparison.

---

## 🔮 Future Improvements

- [ ] Add sound effects and music
- [ ] Implement graphical user interface (GUI) using SFML or Qt
- [ ] Add more countries and continents
- [ ] Online multiplayer support
- [ ] Leaderboard with player names
- [ ] Difficulty-based time limits
- [ ] Hints system (reveal first letter, country flag, etc.)
- [ ] Mobile port (Android/iOS)

---

## 📄 License

This project is created for educational purposes. Feel free to use, modify, and distribute with proper attribution.

---

## 🙏 Acknowledgments

- Thanks to our instructors for guidance and support
- Inspired by classic geography quiz games
- Emoji icons enhance the console gaming experience

---

<p align="center">
  <b>Made with ❤️ and lots of ☕</b><br>
  <i>Happy Guessing! 🌍✈️</i>
</p>
