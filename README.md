// CS-GROUP-2
//Tic Tac Toe game ( C++)

//Below is the source code:

#include <iostream>
using namespace std;

char board[3][3];
char currentPlayer = 'X';

// Initialize the board with empty spaces
void initializeBoard() {
    for (int i = 0; i < 3; ++i)
        for (int j = 0; j < 3; ++j)
            board[i][j] = ' ';
}

// Display the current state of the board
void displayBoard() {
    cout << "  0   1   2\n";
    for (int i = 0; i < 3; ++i) {
        cout << i << " ";
        for (int j = 0; j < 3; ++j) {
            cout << board[i][j];
            if (j < 2) cout << " | ";
        }
        cout << "\n";
        if (i < 2) cout << "  ---------\n";
    }
}

// Switch turns between players
void switchPlayer() {
    currentPlayer = (currentPlayer == 'X') ? 'O' : 'X';
}

// Check if the current player has won
bool checkWin() {
    // Check rows and columns
    for (int i = 0; i < 3; ++i) {
        if ((board[i][0] == currentPlayer &&
             board[i][1] == currentPlayer &&
             board[i][2] == currentPlayer) ||
            (board[0][i] == currentPlayer &&
             board[1][i] == currentPlayer &&
             board[2][i] == currentPlayer)) {
            return true;
        }
    }
    // Check diagonals
    if ((board[0][0] == currentPlayer &&
         board[1][1] == currentPlayer &&
         board[2][2] == currentPlayer) ||
        (board[0][2] == currentPlayer &&
         board[1][1] == currentPlayer &&
         board[2][0] == currentPlayer)) {
        return true;
    }

    return false;
}

// Check for a draw
bool checkDraw() {
    for (int i = 0; i < 3; ++i)
        for (int j = 0; j < 3; ++j)
            if (board[i][j] == ' ')
                return false;
    return true;
}

// Main game loop
void playGame() {
    int row, col;
    bool gameEnded = false;
    initializeBoard();

    while (!gameEnded) {
        displayBoard();
        cout << "Player " << currentPlayer << ", enter row and column (0-2): ";
        cin >> row >> col;

        // Input validation
        if (row < 0  || row > 2 || col < 0 || col > 2) {
            cout << "Invalid position. Try again.\n";
            continue;
        }

        // Check if the cell is empty
        if (board[row][col] != ' ') {
            cout << "Cell already taken. Try again.\n";
            continue;
        }

        // Make the move
        board[row][col] = currentPlayer;

        // Check for win or draw
        if (checkWin()) {
            displayBoard();
            cout << "Player " << currentPlayer << " wins!\n";
            gameEnded = true;
        } else if (checkDraw()) {
            displayBoard();
            cout << "It's a draw!\n";
            gameEnded = true;
        } else {
            switchPlayer();
        }
    }
}

int main() {
    playGame();
    return 0;
}
#include <iostream>
using namespace std;

char board[3][3];
char currentPlayer = 'X';

// Initialize the board with empty spaces
void initializeBoard() {
    for (int i = 0; i < 3; ++i)
        for (int j = 0; j < 3; ++j)
            board[i][j] = ' ';
}

// Display the current state of the board
void displayBoard() {
    cout << "  0   1   2\n";
    for (int i = 0; i < 3; ++i) {
        cout << i << " ";
        for (int j = 0; j < 3; ++j) {
            cout << board[i][j];
            if (j < 2) cout << " | ";
        }
        cout << "\n";
        if (i < 2) cout << "  ---------\n";
    }
}

// Switch turns between players
void switchPlayer() {
    currentPlayer = (currentPlayer == 'X') ? 'O' : 'X';
}

// Check if the current player has won
bool checkWin() {
    // Check rows and columns
    for (int i = 0; i < 3; ++i) {
        if ((board[i][0] == currentPlayer &&
             board[i][1] == currentPlayer &&
             board[i][2] == currentPlayer) ||
            (board[0][i] == currentPlayer &&
             board[1][i] == currentPlayer &&
             board[2][i] == currentPlayer)) {
            return true;
        }
    }
    // Check diagonals
    if ((board[0][0] == currentPlayer &&
         board[1][1] == currentPlayer &&
         board[2][2] == currentPlayer) ||
        (board[0][2] == currentPlayer &&
         board[1][1] == currentPlayer &&
         board[2][0] == currentPlayer)) {
        return true;
    }

    return false;
}

// Check for a draw
bool checkDraw() {
    for (int i = 0; i < 3; ++i)
        for (int j = 0; j < 3; ++j)
            if (board[i][j] == ' ')
                return false;
    return true;
}

// Main game loop
void playGame() {
    int row, col;
    bool gameEnded = false;
    initializeBoard();

    while (!gameEnded) {
        displayBoard();
        cout << "Player " << currentPlayer << ", enter row and column (0-2): ";
        cin >> row >> col;

        // Input validation
        if (row < 0  || row > 2 || col < 0 || col > 2) {
            cout << "Invalid position. Try again.\n";
            continue;
        }

        // Check if the cell is empty
        if (board[row][col] != ' ') {
            cout << "Cell already taken. Try again.\n";
            continue;
        }

        // Make the move
        board[row][col] = currentPlayer;

        // Check for win or draw
        if (checkWin()) {
            displayBoard();
            cout << "Player " << currentPlayer << " wins!\n";
            gameEnded = true;
        } else if (checkDraw()) {
            displayBoard();
            cout << "It's a draw!\n";
            gameEnded = true;
        } else {
            switchPlayer();
        }
    }
}

int main() {
    playGame();
    return 0;
}

