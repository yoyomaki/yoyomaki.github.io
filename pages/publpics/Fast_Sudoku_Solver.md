---
layout: frontpage
title: Fast Sudoku Solver
---
<link rel="stylesheet" href="//cdnjs.cloudflare.com/ajax/libs/highlight.js/9.2.0/styles/default.min.css">
<script src="//cdnjs.cloudflare.com/ajax/libs/highlight.js/9.2.0/highlight.min.js"></script>
<script>hljs.initHighlightingOnLoad();</script>

<div class="navbar">
  <div class="navbar-inner">
      <ul class="nav">
          <li><a href="mousebc_fig3.html">prev</a></li>
          <li><a href="iplotCorr.html">next</a></li>
      </ul>
  </div>
</div>

<h4><a name="Fast Sudoku Solver"></a>Fast Sudoku Solver</h4>

A generic way to solve a Sudoku puzzle is to use recursion. Here is a sample code:

```cpp
// determine the board is valid or not.
bool isValid(vector<vector<char>>& board, int row , int column, char c){
     for (int i = 0; i < 9; ++i)
         if (board[row][i] == c) return false;
     for (int j = 0; j < 9; ++j)
         if (board[j][column] == c) return false
     for (int i = 0; i < 3; ++i)
         for (int j = 0; j < 3; ++j)
             if (board[row / 3 * 3 + i][column / 3 * 3 + j] == c)
                return false;
     return true;
}
//empty cell is represented by char '.'
bool solve(vector<vector<char>>& board){
     for (int i = 0; i < 9; ++i){
         for (int j = 0; j < 9; ++j){
             if ('.' == board[i][j]){
                for (int k = 0; k < 9; ++k){
                    if (isValid(board, i, j, '1' + k)){
                       board[i][j] = '1' + k;
                       if (solve(board)) return true;
                       else board[i][j] = '.';
                    }
                 }
                 return false;
             }
          }
      }
      return true;
} 
```

However, this algorithm has a bad performance on instance with 30~40 numbers that are given on the board out of 81 numbers. The Fast Sudoku Solver is using:

 1. Backtracking: back up to the preceding variable and try a different assignment for it.
 
 2. Forward checking: keep track of remaining legal values forunassigned variables, and terminate search when any variable has nolegal values.
 
 3. Heuristics: choose the variable which has the fewest “legal” moves (AKA minimum remaining values heuristics). For tie-breaker among most constrained variables, choose variable with most constraints on remaining variables. Given a variable, choose the least constraining value, which is the one that rules out the fewest values in the remaining variables.

```
pseudo code:
A table keeps recording legal moves for each variable after each step.
 
0. If there is an variable has no legal moves, backtrack.
1. Select unassigned variable x using most constrained and most constraining heuristics.
2. Order legal moves of x as {x1,...,xn} by least constraining heuristics. 
3. Assign x = x1, update legal-move table, and move to next variable.
```

The plot of average number of search steps performed on 10 random generated instances with different number of numbers given on the board from 1 to 71.

![Fast Sudoku Solver Performance Plot](../../assets/publpics/sudoku_plot.png)

Source code is coming.


