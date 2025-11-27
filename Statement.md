POBLEM STATEMENT: The challenge is to implement a two-player Tic-Tac-Toe game on a 3x3 grid played in turns. Players alternate moves, placing 'X' or 'O' in empty cells. The objective is to connect three of their symbols in a straight line—horizontally, vertically, or diagonally—before the opponent does. If the grid is filled without any player achieving this, the game is declared a draw.

SCOPE OF THE PROJECT: 1)Console-based game for 2 participants using text input/output.

2)Handles all aspects of gameplay: board creation, move validation, alternate turns, win/draw detection, and display of current state.

3)Enforces game rules strictly (valid moves, switching turns, preventing overwriting).

4)Provides clear victory and draw announcements.

5)Optional extensions (not in current scope):

6)Support for larger grids or custom win lengths.

7)Automated or AI players.

8)Graphical user interface.

TARGET USERS: 1)Python learners and beginners looking to practice logic, data structures, and input/output operations.

2)Anyone wanting to play a quick terminal Tic-Tac-Toe game.

3)Students and educators demonstrating turn-based game logic.

HIGH-LEVEL FEATURES: 1)Game Initialization: Sets up an empty board, ensures clear display with row/column indices.​

2)Move Input and Validation: Prompts user input for moves and validates proper format, boundaries, and empty cell requirement.

3)Turn Management: Alternates turns between Player 'X' and Player 'O'.

4)Win Detection: Checks rows, columns, and diagonals after every move for a victory condition.

5)Draw Detection: Recognizes full boards without a winner and declares a draw.

6)End-of-Game Announcements: States the result after each round.

7)Simple, robust structure: Each function handles an essential piece of game logic.
