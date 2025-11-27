PROJECT TITLE:
TIC TAC TOE game in python.

OVERVIEW:
A simple console-based implementation of the classic Tic-Tac-Toe game for two players. The game utilizes Python functions, lists, and interactive input, allowing two players to take turns marking spaces in a 3×3 grid. The game continues until one player wins or the game ends in a draw.

FEATURES:
•	Interactive gameplay for two players ('X' and 'O')
•	Dynamic 3x3 board display
•	Input validation to prevent illegal moves
•	Win and draw detection after every move
•	Clear game-end messages
•	Self-contained source code; no external libraries required

TECHNOLOGIES USED:
•	Python (built-in data structures and functions)
•	Console Input/Output
•	No third-party dependencies

STEPS TO INSTALL AND RUN:
1.	Download or copy the Python script into a local file, e.g., tic_tac_toe.py.
2.	Make sure Python (3.13) is installed on your system.
3.	Open a terminal or command prompt.
4.	Navigate to the directory containing tic_tac_toe.py.
5.	Run the game using:   python tic_tac_toe.py
	
INSTRUCTIONS FOR TESTING:
•	When prompted, enter your moves by specifying row and column numbers separated by a space (e.g., 1 2).
•	Only positions labelled with a blank space can be chosen.
•	The game validates each move and will prompt again if the input is invalid.
•	After a win or draw, the game exits automatically.

SCREENSHOTS:
<img width="940" height="847" alt="image" src="https://github.com/user-attachments/assets/d128a06b-5e9f-4987-9339-2896ecf6ac3b" />
<img width="952" height="811" alt="image" src="https://github.com/user-attachments/assets/6455109c-72d4-4978-962a-27b8fde32c36" />
<img width="950" height="390" alt="image" src="https://github.com/user-attachments/assets/377bcf9d-9fa8-48ad-bc20-10d1132ea62d" />
CODE:
def create_board():
    
    return [
        [' ', ' ', ' '],
        [' ', ' ', ' '],
        [' ', ' ', ' ']
    ]

def print_board(board):
  
    print("\n   0   1   2")
    
    for i in range(len(board)):
        
        row = board[i]
        
        print(f"{i}  " + " | ".join(row))
        
        if i < 2:
            print("   ---|---|---")
    print()
    
if __name__ == "__main__":
    game_board = create_board()
    game_board[0][0] = 'X'
    game_board[1][1] = 'O'
    
    print_board(game_board)

def check_win(board, player):
    for r in range(3):
        if all(board[r][c] == player for c in range(3)):
            return True

    for c in range(3):
        if all(board[r][c] == player for r in range(3)):
            return True

    if all(board[i][i] == player for i in range(3)):
        return True


    if all(board[i][2 - i] == player for i in range(3)):
        return True


    return False

def check_draw(board):

    for r in range(3):
        for c in range(3):
            if board[r][c] == ' ':
                return False

    return True

def get_player_input(player, board):

    while True:
        user_input = input(f"Player '{player}', enter move (row col): ")
        parts = user_input.split()


        if len(parts) != 2:
            print("Invalid input. Please enter TWO numbers separated by a space.")
            continue

        row_str, col_str = parts


        if not (row_str.isdigit() and col_str.isdigit()):
            print("Invalid input. Please enter NUMBERS for row and col.")
            continue


        row = int(row_str)
        col = int(col_str)


        if not (0 <= row <= 2 and 0 <= col <= 2):
            print("Coordinates out of range. Must be 0, 1, or 2.")
            continue


        if board[row][col] != ' ':
            print("That cell is already taken! Try again.")
            continue


        return row, col



def play_game():


    print("--- Welcome to Tic-Tac-Toe! ---")

    board = create_board()
    current_player = 'X'
    game_over = False

    while not game_over:

        print_board(board)


        row, col = get_player_input(current_player, board)


        board[row][col] = current_player

        if check_win(board, current_player):
            print_board(board)
            print(f"🎉 Player '{current_player}' wins! Congratulations!")
            game_over = True


        elif check_draw(board):
            print_board(board)
            print("It's a draw! 🤝")
            game_over = True

        else:
            current_player = 'O' if current_player == 'X' else 'X'

if __name__ == "__main__":
    play_game()
