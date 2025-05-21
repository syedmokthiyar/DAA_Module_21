# EX 3C Sudoku Solver
## DATE:
## AIM:
To write a python program to find the solution of sudoku puzzle using Backtracking.


## Algorithm
1. Find an Empty Cell: Scan the board to find a cell with value 0 (indicating it's unassigned).

2. Try Possible Numbers: For each number from 1 to 9, check if it's safe to place it:

3. Not present in the same row

4. Not present in the same column

5. Not present in the 3x3 subgrid

6. Place Number and Recurse:

7. If placing a number is valid, place it and recursively attempt to fill the rest of the board.

8. If the board is fully filled without violations, return True.



## Program:
Developed by:  GANESH R

Register Number:  212222240029

```python
board = [
    [0, 0, 0, 8, 0, 0, 4, 0, 3],
    [2, 0, 0, 0, 0, 4, 8, 9, 0],
    [0, 9, 0, 0, 0, 0, 0, 0, 2],
    [0, 0, 0, 0, 2, 9, 0, 1, 0],
    [0, 0, 0, 0, 0, 0, 0, 0, 0],
    [0, 7, 0, 6, 5, 0, 0, 0, 0],
    [9, 0, 0, 0, 0, 0, 0, 8, 0],
    [0, 6, 2, 7, 0, 0, 0, 0, 1],
    [4, 0, 3, 0, 0, 6, 0, 0, 0]
]

def printBoard(board):
    for i in range(0, 9):
        for j in range(0, 9):
            print(board[i][j], end=" ")
        print()

def isPossible(board, row, col, val):
    for j in range(0, 9):
        if board[row][j] == val:
            return False

    for i in range(0, 9):
        if board[i][col] == val:
            return False

    startRow = (row // 3) * 3
    startCol = (col // 3) * 3
    for i in range(0, 3):
        for j in range(0, 3):
            if board[startRow+i][startCol+j] == val:
                return False
    return True

def solve():
    #####################  Add your code here #########################
    #Start here
    for i in range(0, 9):
        for j in range(0, 9):
            if board[i][j] == 0:
                for val in range(1, 10):
                    if isPossible(board, i, j, val):
                        board[i][j] = val
                        solve()
                        board[i][j] = 0
                return
    printBoard(board)
    #End here
solve()

```

## Output:
![image](https://github.com/user-attachments/assets/7867ffb1-90b6-49dc-bfec-cd496607e99b)


## Result:
The Sudoku solver program executed successfully and found the solution for the given puzzle.
