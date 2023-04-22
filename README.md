Creating a basic game in c
==========================

The purpose of this repo is to create a basic c game.
This initial game will be something simple like snake.

Using the GeeksforGeeks [Snake Game in C](https://www.geeksforgeeks.org/snake-game-in-c/#) as an example.

The goal is to make a NES/Atari emulator playable game since they are 8-bit

## Basic outline needed for the game
1. Rules:
    1. Moveable elements must stay within boundaries i.e. snake and food piece
    1. Snake grows longer after it eats a piece
    1. Piece must stay static until head of snake is in same space i.e. eats the piece
    1. Once piece is eaten, new piece will be randomly generated:
        * within boundary
        * on a space that is not the snake
1. Elements:
    * Outline/boundary of play area
    * Snake
    * Piece to eat
1. Functions:
    1. start_game(width, height)
        * sets up board games [height][width]
        * init snake
        * init piece
    1. random_space(piece)
        * places piece in random space in board
    1. move_snake(snake)
        * moves snake 
    1. check_piece(piece, snake)
        * is snake head and piece in same place?
    1. eat_piece(snake, piece)
        * if check_piece() is true:
            1. remove piece from board
            1. call random_space() to place piece in new place
    1. valid_new_piece(snake)
        * is new random space valid?
    1. grow_snake()
        * when piece gets eaten, grow length of snake by 1
    1. next_move(snake)
        * if no valid keyboard input, move in same direction
        * if valid keyboard, change direction if different than current direction
            otherwise keep going in same direction
        * if next move is boarder, then game over
    1. Optional
        1. game menu
        1. game over screen
1. Structure elements

        // Structure Elements
        typedef enum { false, true } bool;

        struct boundary {
            int width;
            int height;
            bool boundary[width][height]
            *struct snake;
            **struct piece;
        } boundary;

        struct snake {
            bool snake [boundary.width-1][boundary.height-1]; // boolean 2D array of snake positions
            bool next [boundary.width-1][boundary.height-1];// auxillary 2D array to move 
            next_move();
            move_snake();
            eat_piece();
            grow_snake();
            *struct piece;
        }snake;

        struct piece {
            check_piece();
            random_space();
            valid_new_piece();
        }
