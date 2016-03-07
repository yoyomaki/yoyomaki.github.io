---
layout: page
title: Data Processing Using Python
description: Data Processing Using Python
---


```cpp
bool isVali_d(vector&lt;vector&lt;char&gt;&gt;&amp; board, int row , int column, char c){
      for (int i = 0; i &lt; 9; ++i)
          if (board[row][i] == c) return false;
      for (int j = 0; j &lt; 9; ++j)
          if (board[j][column] == c) return false
      for (int i = 0; i &lt; 3; ++i)
          for (int j = 0; j &lt; 3; ++j)
              if (board[row / 3 * 3 + i][column / 3 * 3 + j] == c)
                 return false;
      return true;
  } 
```

haha2


