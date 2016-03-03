---
layout: page
title: Data Processing Using Python
description: Data Processing Using Python
---


<link rel="stylesheet" href="//cdnjs.cloudflare.com/ajax/libs/highlight.js/9.2.0/styles/default.min.css">
<script src="//cdnjs.cloudflare.com/ajax/libs/highlight.js/9.2.0/highlight.min.js"></script>
<script>hljs.initHighlightingOnLoad();</script>

<pre><code class="cpp"> bool isVali_d(vector&lt;vector&lt;char&gt;&gt;&amp; board, int row , int column, char c){
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
</code></pre>
haha2

<pre><code>2016/02/20
Li Zhang
Nanjing University</code></pre>

