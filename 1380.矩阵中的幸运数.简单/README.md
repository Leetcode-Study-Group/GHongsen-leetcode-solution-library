## 1380.矩阵中的幸运数-<font color=#5AB726>简单</font>

给你一个 `m x n` 的矩阵，矩阵中的数字 **各不相同** 。请你按 **任意** 顺序返回矩阵中的所有幸运数。

幸运数是指矩阵中满足同时下列两个条件的元素：<br>

- 在同一行的所有元素中最小  
- 在同一列的所有元素中最大  

<br>

**示例 1：**

<pre>
<b>输入：</b>matrix = [[3,7,8],[9,11,13],[15,16,17]]  
<b>输出：</b>[15]  
<b>解释：</b>15 是唯一的幸运数，因为它是其所在行中的最小值，也是所在列中的最大值。  
</pre>

<br>

**示例 2：**

<pre>
<b>输入：</b>matrix = [[1,10,4,2],[9,3,8,7],[15,16,17,12]]  
<b>输出：</b>[12]  
<b>解释：</b>12 是唯一的幸运数，因为它是其所在行中的最小值，也是所在列中的最大值。  
</pre>

<br>

**示例 3：**

<pre>
<b>输入：</b>matrix = [[7,8],[1,2]]  
<b>输出：</b>[7]  
</pre>

<br>

**提示：**

* `m == mat.length`
* `n == mat[i].length`
* `1 <= n, m <= 50`
* <code>1 <= matrix[i][j] <= 10<sup>5</sup></code>
* 矩阵中的所有元素都是不同的

