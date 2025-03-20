# Clue Game

A text-based adventure game where players navigate through rooms, interact with items and characters.

## Prerequisites

- GCC compiler
- Unix-like environment (Linux/MacOS)

## Installation

1. Clone the repository or download the source files:
   - adventure.c
   - rooms.c
   - items.c
   - characters.c

2. Open terminal in the project directory

## Compilation

To compile the game, use one of the following commands:

```bash
# Basic compilation
gcc adventure.c rooms.c items.c characters.c

# Compilation with custom output name
gcc adventure.c rooms.c items.c characters.c -o clue_game
```

## Running the Game

1. After compilation, run the game:
   ```bash
   # If compiled with default name
   ./a.out
   
   # If compiled with custom name
   ./clue_game
   ```

## Game Structure

### Room Layout
The game consists of 9 rooms arranged in a 3x3 grid:
```
0 | 1 | 2
3 | 4 | 5
6 | 7 | 8
```

### Room Connections
- Each room is connected to adjacent rooms (top, down, right, and left)
- Connections are implemented using pointers (north, south, west, and east)
- If no room exists in a direction, the pointer is NULL
- Rooms are randomly placed in the grid at the start of each game

### Game Elements
- 6 items distributed across different rooms
- 5 non-player characters
- Player character (named by the user)

## How to Play

1. When the game starts, you'll be prompted to enter your name
2. Navigate through rooms and interact with the environment using commands
3. Some commands require additional input (secondary commands)

### Command Structure
- Primary commands are entered first
- If a command requires additional information, you'll be prompted for secondary input
- Example: For picking up items
  ```
  Command: take
  Item name: key
  ```

### Input Validation
- The game provides instructions for correct input format
- Invalid commands or inputs will prompt you to retry
- Follow the in-game instructions for proper command formatting

Each of the 9 rooms were individually created with a name. They are then randomly put into each index in an array using a random number generator.
The layout of the building with 9 rooms: 0 | 1 | 2
                                         3 | 4 | 5
                                         6 | 7 | 8
Each room is connected to their top, down, right, and left room.
The rooms are connected through pointers. Each room has a pointer pointing to the north, south, west, and east room. 
If the room does not have a direction, the room in that direction is NULL.
Items are put into their designated rooms at the beginning of the game.
There is a total of 6 items in the game.
Also, besides the player, there are a total of 5 characters

For each of the input, there will be a scanf function to take the input and assign it to a variable. 
If a command has a secondary function, there will be another scanf to take its input.
For example, the take command has a secondary function to take the name of an item. There will be another scanf to take the name of the item and assign it to another variable. The scanf function would scan strings within the user input to look for matched command/target within the game. The game has instruction on how the user should type the input and such. Any other cases would be regard as invalid and prompt the user to retype.

The first user input would be their name to set as their avatar's name.
After that, the game would require commands as the user input.
As explained above, some commands require further user input.
If any commands or input is regard as invalid within the game, the user would have to retype the input.
