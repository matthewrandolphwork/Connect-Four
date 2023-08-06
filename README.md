# Connect-Four

## Table of contents

- [Task List](#Task-List)
- [BoardState (Class)](#BoardState-(Class))
  - [board](#board-(Field))
  - [valid_moves](#valid_moves-(Accessor))
  - [game_status](#game_status-(Accessor))
  - [current_turn](#current_turn-(Accessor))
  - [display_board](#display_board-(Accessor))
  - [Constructor](#Constructor)
  - [update](#update-(Mutator))
- [Player (Class)](#Player-(Class))
  - [player_type](#player_type-(Field))
  - [make_move](#move_process-(Field))
- [Game (Class)](#Player-(Class))
  - [board_state](#board_state-(Field))
  - [player_one](#player_one-(Field))
  - [player_two](#player_two-(Field))
  - [game_history](#game_history-(Field))
  - [do_display](#do_display-(Field))
  - [replay](#replay-(Accessor))
  
## Operations Concept
- Start Game
- Choose Player One 
- Choose Player Two
- Choose Visualization
- Player 1 moves
- Update Board
- Check Game Status
- If Continues, Player 2 moves
- If Ended (Tie or Winner), Exit Interface
- 
- Exit Interface
- Write Game History to File?
- Replay the Game History
- Play Again?


## Task List
- [ ] Create Flow Diagram 
- [ ] Document BoardState
- [ ] Document Bot 
- [ ] Document GenValidMove 
- [ ] Document Move Format
- [ ] Document ChkValidMove
- [ ] Document GenNextBoardState 
- [ ] Document BoardStateEvaluator
- [ ] Document Flow Diagram


## BoardState (Class)

### board (Field)
The Connect Four Board is a two dimensional integer list of 7 columns and 6 rows.  The lower left corner has coordinates (0,0) and the upper right corner has coordinates (6,5).  Each (x,y) coordinate can have one of the following: 0 = empty square, 1 = "X" or Player 1, and 2 = "O" or Player 2.

### valid_moves (Accessor)
This returns an integer list of which columns (0 to 6) are valid moves. For example, if a column is full, it will not appear in the valid moves list. 

### game_status (Accessor)
This returns an integer that is the current state of the game. -1 represents that the game is still in progress. 0 represents that the game has ended in a tie. 1 represents that Player 1 ("X") has won. 2 represents that Player 2 ("O") has won. 

### current_turn (Accessor)
This returns an integer that represents the player who would place next. 1 represents that Player 1 ("X") is to play while 2 represents that Player 2 ("O") is to play.

### display_board (Accessor)
This will return some sort of graphical representation of the current board state.

### Constructor
For our constructor we probably want to initialize the board to all 0s, valid_moves to [0,1,2,3,4,5,6], game_status to -1 and current_turn to 1.

### update (Mutator)
For our mutator we want to accept an integer move from [0,1,2,3,4,5,6] as a parameter. If we are given a move that is not in valid_moves we want to throw some sort of error. Otherwise we update the board with where the piece falls.

## Player (Class)

### player_type (Field)
This will take the value of 0 for a human and 1 for a bot.

### make_move (Field)
This field is a function that calls the process that determines the move of the player. This will eventually return a valid_move. If the player is a human, this function will call upon the user to input a move. If the player is a bot, this function will call the bots move.

## Game (Class)

### board_state (Field)
Every Game object will have a BoardState object as its board_state field.

### player_one (Field)
This field is a Player object.

### player_two (Field)
This field is also a Player object.

### game_history (Field)
This is a one dimensional integer list of the moves that each player has made.

### do_display (Field)
This boolean field determines whether the board will be displayed for this game.

### replay (Accessor)
This function replays a game by looking at the game_history and allows the user to toggle through each move on some sort of user interface.