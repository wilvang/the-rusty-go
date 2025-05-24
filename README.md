# Lab 14: The Game of Go

# Haskell and Rust

This is an open task, where your creativity is the key element.
Which language to choose? Your choice.
If you pick Haskell, GUI is optional. Use your experience from Lab 10.
You can focus on terminal interactions only, and the logic of the game if you want in Haskell.
If you pick Rust, GUI would be expected with the use of `Iced.rs` library.

# About Go

[Go](<https://en.wikipedia.org/wiki/Go_(game)>) is an ancient board game that originated in China over 2,500 (some say 4000) years ago.
It is played on a grid of 19x19 lines, where two players (Black and White) take turns placing stones on the intersections.
The objective is to control more territory than your opponent by surrounding empty areas and capturing their stones.
Despite its simple rules, Go is renowned for its strategic depth and complexity, making it a fascinating challenge
for players and AI developers alike.

The game teaches critical thinking, patience, and foresight, as players must balance local tactics with global strategy.
Go has also been a benchmark for AI research, with milestones like AlphaGo demonstrating the potential of
machine learning in solving complex problems.

This project aims to create a Go game engine that reads [SGF](https://en.wikipedia.org/wiki/Smart_Game_Format) (Smart Game Format) files,
maintains the internal state of the game, enforces the rules of Go (including the KO rule), and plays against
a human opponent using a simple AI strategy.

# Project Specification

SGF Reader and Go Game Engine.

## 1. **SGF File Reader**

- The program should be able to read and parse [SGF](https://en.wikipedia.org/wiki/Smart_Game_Format) files, which are the standard format for storing Go games.
- The SGF reader should extract the following information:
  - Board size (default is 19x19, but smaller sizes like 9x9 or 13x13 should be supported).
  - Initial game state should be taken from SGF file.
  - Sequence of moves played in the game.

#### 2. **Internal Game State Representation**

- The program should maintain an internal representation of the game state, including:
  - All the current board positions (which intersections are occupied by Black, White, or empty).
  - The number of stones captured by each player.
  - The current player to move (Black or White).
- The representation should be efficient and allow for easy manipulation (e.g., placing stones, removing captured stones, checking legal moves).

#### 3. **Move Validation**

- The program should distinguish between legal and illegal moves based on the rules of Go:
  - A move is illegal if it violates the rule of liberty (a stone or group of stones must have at least one adjacent empty intersection).
  - The KO rule: A move is illegal if it recreates the previous board position.
- The program should provide clear feedback when an illegal move is attempted.

#### 4. **Basic AI Player**

- The program should be able to play as an AI opponent against a human player.
- For example, the AI could follow a simple strategy of placing legal moves such that they always improve its own liberties while removing liberties of the oponent.
- Or, combinig several heuristics, eg.:
  - **Random Moves (20% of the time):** The AI should choose a random legal move on the board.
  - **Maximizing Freedom (80% of the time):** The AI should prioritize moves that maximize the freedom (liberties) of its own groups.
  - **Minimizing the Number of Groups:** The AI should aim to minimize the number of separate groups on the board, favoring moves that connect its stones.
- The AI should respect all Go rules, including the KO rule.

#### 5. **User Interface**

- Display the current board state (e.g., using ASCII art or a graphical grid).
- Allow the human player to input moves (e.g., by specifying coordinates like "A1" or "K10"), or by clicking on the UI.
- Show the AI's moves and update the board accordingly.
- The interface should indicate when a move is illegal and prompt the player to try again.

#### 6. **Testing and Validation**

- The program should be tested with a variety of SGF files to ensure correct parsing and move validation.
- The AI's behavior should be tested to verify that it follows the specified strategy and respects the rules of Go.

---

### Learning Outcomes

By completing this project, you will:

- Gain experience in parsing and processing file formats (SGF).
- Develop a deep understanding of the rules and strategies of Go.
- Learn how to represent and manipulate complex game states programmatically.
- Explore basic AI techniques for decision-making in games.

This project is a great opportunity to combine algorithmic thinking with game design,
while exploring one of the most intellectually stimulating games in history. Good luck!
