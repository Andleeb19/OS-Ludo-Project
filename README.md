# 🎲 Multithreaded Ludo Game – Operating Systems Final Project 

## 👨‍💻 Course
**Operating Systems**  
FAST-NUCES Islamabad 

## 📌 Project Description

This project implements a **multithreaded simulation of the Ludo board game** using POSIX Threads (pthreads) in C++. The project focuses on key Operating Systems concepts like:

- Semaphores
- Condition Variables
- Thread Synchronization
- Mutual Exclusion
- Shared Resource Management

Each player in the game is a separate thread and competes in a turn-based system with randomized dice rolls and dynamic board interaction.

---

## 🕹️ Features

### ✅ Phase I
- Initializes and displays the Ludo board grid
- Creates four threads (players)
- Uses semaphores for mutual exclusion of shared resources (dice and board)

### ✅ Phase II
- Fully playable Ludo logic with turn-based system
- Randomized dice values and player turns
- Hit/move rules implemented
- Tokens controlled using semaphores
- Master thread monitors:
  - Player elimination (after 20 turns without a six)
  - Player victory
- Handles safe spots, exact finishing rolls, and block formations
- Dynamic board rendering using ASCII art

---

## 🧵 Threads & Synchronization

- **Player Threads (4)**: Each represents one player and simulates their dice roll and token movement.
- **Master Thread**: Monitors hit rate and token completion. Cancels threads on disqualification or victory.
- **Dice & Grid Semaphores**: Ensure only one thread can access these resources at a time.
- **Token Semaphores & Condition Variables**: Manage player token safety, sequence of actions, and race conditions.

---

## 📁 File Structure

| File                  | Description |
|-----------------------|-------------|
| `main.cpp`            | Game setup, main thread logic, token count input, game loop |
| `player.h`            | Player and token class definitions |
| `playerThread.h`      | Thread function logic for players |
| `masterThread.h`      | Master thread logic |
| `victim.h`            | Token collision detection and hit handling |
| `drawgrid.h`          | Grid display and rendering logic |
| `Makefile` *(optional)* | To compile all files |

---

## 🔧 System Specifications

- **CPU**: Intel Core i5 (4 cores, 8 threads, 2.5–3.5 GHz)
- **RAM**: 8 GB
- **Storage**: 256 GB SSD
- **Compiler**: GCC (via g++)
- **Environment**: Linux preferred / WSL / MinGW (for Windows)

---

## 🚀 Running the Project

1. Clone the repo or extract the ZIP folder.
2. Open a terminal and navigate to the project directory.
3. Compile using:

```bash
g++ main.cpp -o ludo -lpthread
Run using:

./ludo
