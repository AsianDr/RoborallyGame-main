# RoboRally Game  
*A JavaFX desktop board game where players program robots with movement cards and race to the finish.*

## 📖 Overview
This project implements a digital version of the RoboRally board game in Java. Multiple players control robots on a grid-based board, choose movement cards, and execute their actions over several phases until one robot reaches the end position.

The system separates the core game logic from the JavaFX controller flow, making it easier to manage player setup, starting positions, card selection, robot movement, and the winning screen.

The project is structured as a Maven-based Java application.

---

## 🚀 Features
- JavaFX desktop game flow with multiple scenes
- Player setup with selectable player count and player names
- Difficulty-based board creation using random generation or JSON map loading
- Programmable robot movement using action cards
- Board entities such as floors, pits, walls, lasers, conveyor belts, repair squares, springs, start positions, and end positions
- Turn-based card selection and five-card execution rounds
- Robot lives, damage, repair, respawn, collision, and push mechanics
- Background music support through JavaFX MediaPlayer

---


## 📁 Project Structure

```
RoborallyGame-main/
├── pom.xml                       # Maven project configuration
├── mvnw                          # Maven wrapper script for macOS/Linux
├── mvnw.cmd                      # Maven wrapper script for Windows
├── README.md
└── src/
    └── main/
        ├── java/
        │   └── roborally/
        │        ├── Board.java                  # Board creation and tile placement
        │        ├── Card.java                   # Movement-card deck logic
        │        ├── Game.java                   # Main game loop and win checking
        │        ├── Player.java                 # Player hand and robot setup
        │        ├── Position.java               # Robot position and orientation
        │        ├── Robot.java                  # Robot movement, lives, and collision logic
        │        ├── Square.java                 # Board tile types and interactions
        │        │
        │        └── controller/
        │             ├── Launch.java
        │             ├── RoboRallyController.java
        │             ├── PlayerAmountController.java
        │             ├── PlayerNameController.java
        │             ├── StartPosController.java
        │             ├── SelectCardsController.java
        │             ├── RobotController.java
        │             ├── NextTurnMechanicController.java
        │             ├── GameRulesController.java
        │             ├── GoldController.java
        │             └── MusicPlayerController.java
        │
        └── resources/                         # Expected runtime resources
             ├── maps/
             │    └── map1.json                # Expected predefined board maps
             │
             └── music/
                  └── medieval.mp3             # Expected background music file
```

### 📌 Key Components

**`Board.java`**  
Creates and manages the game board. It supports randomly generated boards and loading predefined maps from JSON based on the chosen difficulty.

**`Game.java`**  
Controls the main game flow. It executes five-card rounds, updates robot movement, and checks whether a player has reached the end position.

**`Robot.java`**  
Handles robot movement, orientation, lives, damage, repair, respawn, collision, and push behavior.

**`Square.java`**  
Defines the board tiles and their interactions, including floors, pits, walls, lasers, conveyor belts, repair squares, springs, start positions, and end positions.

**`Card.java`**  
Defines the movement-card system and shuffles a hand of movement cards for each player.

**`controller/`**  
Contains the JavaFX controllers that manage the game screens, including player amount selection, rule display, player names, starting positions, card selection, robot movement animation, and the winner screen.

---

## ⚙️ Requirements
- Java 22
- Maven or the included Maven wrapper
- JavaFX dependencies from `pom.xml`
- Required runtime resources such as maps and music files

---

## ▶️ Running the Project

The main launcher class is:

```text
dtu.roborally.controller.Launch
```

To run the project from an IDE, open the Maven project and run the `Launch` class.

If running through Maven, make sure the JavaFX Maven plugin points to the correct launcher class before using:

```bash
# Windows
mvnw.cmd javafx:run

# macOS/Linux
chmod +x mvnw
./mvnw javafx:run
```

---

## 📝 Notes
- The uploaded zip currently contains the main model and controller files.
- The code references additional packages such as `dtu.roborally.view`, `dtu.roborally.utilities`, and `dtu.roborally.Types_of_cards`.
- The code also references resource files such as `src/main/resources/maps/map1.json` and `src/main/resources/music/medieval.mp3`.
- Include these missing files if you want the full GUI project to compile and run correctly.

---
