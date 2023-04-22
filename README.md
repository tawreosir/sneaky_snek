Creating a basic game in c

The purpose of this repo is to create a basic c game.
This initial game will be something simple like snake.

Using the GeeksforGeeks snake in c as example.
https://www.geeksforgeeks.org/snake-game-in-c/#

The goal is to make a NES/Atari emulator playable game since they are 8-bit

Basic outline needed for the game
    1. Rules:
        - Moveable elements must stay within boundaries i.e. snake and food piece
        - Snake grows longer after it eats a piece
        - Piece must stay static until head of snake is in same space i.e. eats the piece
        - Once piece is eaten, new piece will be randomly generated:
            a. within boundary
            b. on a space that is not the snake
    2. Elements:
        - Outline/boundary of play area
        - Snake
        - Piece to eat
    3. Functions:
        a. (optional) game menu
        b. start_game(width, height)
            - sets up board games [height][width]
            - init snake
            - init piece
        c. random_space(piece)
           - places piece in random space in board
        d. move_snake(snake)
           - moves snake 
        e. check_piece(piece, snake)
           - is snake head and piece in same place?
        f. eat_piece(snake, piece)
            - if check_piece() is true:
                 i. remove piece from board
                ii. call random_space() to place piece in new place
        g. valid_new_piece(snake)
            - is new random space valid?
        h. grow_snake()
            - when piece gets eaten, grow length of snake by 1
        j. next_move(snake)
            - if no valid keyboard input, move in same direction
            - if valid keyboard, change direction if different than current direction
              otherwise keep going in same direction
            - if next move is boarder, then game over
        k. (optional) game over screen
    4. Structure elements
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
