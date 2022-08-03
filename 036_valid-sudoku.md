## Problem
Valid Sudoku
https://leetcode.cn/problems/valid-sudoku/

## Problem Description
```
Determine if a 9 x 9 Sudoku board is valid. Only the filled cells need to be validated according to the following rules:

Each row must contain the digits 1-9 without repetition.
Each column must contain the digits 1-9 without repetition.
Each of the nine 3 x 3 sub-boxes of the grid must contain the digits 1-9 without repetition.

Example:
Input: board = 
[["5","3",".",".","7",".",".",".","."]
,["6",".",".","1","9","5",".",".","."]
,[".","9","8",".",".",".",".","6","."]
,["8",".",".",".","6",".",".",".","3"]
,["4",".",".","8",".","3",".",".","1"]
,["7",".",".",".","2",".",".",".","6"]
,[".","6",".",".",".",".","2","8","."]
,[".",".",".","4","1","9",".",".","5"]
,[".",".",".",".","8",".",".","7","9"]]
Output: true

```

## Code

- Support Language: Python

```
class Solution(object):
    def isValidSudoku(self, board):
        """
        :type board: List[List[str]]
        :rtype: bool
        """
        for i in range(9):
            l,r = [],[]
            for j in range(9):
                if board[i][j] not in l:
                    l.append(board[i][j])
                elif board[i][j] != '.':
                    return False
                if board[j][i] not in r:
                    r.append(board[j][i])
                elif board[j][i] != '.':
                    return False
        s = [(0,0), (3,0), (6,0), (0,3), (3,3), (6,3), (0,6), (3,6), (6,6)]
        
        for i in range(9):
            l, r = s[i]
            n = []
            for j in range(l, l+3):
                for k in range(r, r+3):
                    if board[j][k] not in n:
                        n.append(board[j][k])
                    elif board[j][k] != '.':
                        return False
        return True

```
