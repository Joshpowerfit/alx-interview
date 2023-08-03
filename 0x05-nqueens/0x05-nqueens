#!/usr/bin/python3
"""N queens solution finder module.
"""

import sys

def is_safe(board, row, col):
    # Check if there is a queen in the same column
    for i in range(row):
        if board[i][col]:
            return False

    # Check if there is a queen in the upper-left diagonal
    for i, j in zip(range(row, -1, -1), range(col, -1, -1)):
        if board[i][j]:
            return False

    # Check if there is a queen in the upper-right diagonal
    for i, j in zip(range(row, -1, -1), range(col, len(board))):
        if board[i][j]:
            return False

    return True

def nqueens_util(board, row, solutions):
    n = len(board)
    if row == n:
        solutions.append([[i, j] for i, row in enumerate(board) for j, cell in enumerate(row) if cell])
    else:
        for col in range(n):
            if is_safe(board, row, col):
                board[row][col] = 1
                nqueens_util(board, row + 1, solutions)
                board[row][col] = 0

def nqueens(n):
    if not n.isdigit():
        print("N must be a number")
        sys.exit(1)
    
    n = int(n)
    if n < 4:
        print("N must be at least 4")
        sys.exit(1)

    board = [[0 for _ in range(n)] for _ in range(n)]
    solutions = []
    nqueens_util(board, 0, solutions)

    for solution in solutions:
        print(solution)

if __name__ == "__main__":
    if len(sys.argv) != 2:
        print("Usage: nqueens N")
        sys.exit(1)
    
    nqueens(sys.argv[1])

