## 1447.最简分数-<font color=#FFA119>中等</font>


给你一个整数 `n` ，请你返回所有 0 到 1 之间（不包括 0 和 1）满足分母小于等于  `n` 的 **最简** 分数 。分数可以以 **任意** 顺序返回。<br><br>

**示例 1：**

<pre>
<b>输入：</b>n = 2  
<b>输出：</b>["1/2"]  
<b>解释：</b>"1/2" 是唯一一个分母小于等于 2 的最简分数。
</pre>

<br>

**示例 2：**

<pre>
<b>输入：</b>n = 3  
<b>输出：</b>["1/2","1/3","2/3"]  
</pre>

<br>

**示例 3：**

<pre>
<b>输入：</b>n = 4  
<b>输出：</b>["1/2","1/3","1/4","2/3","3/4"]  
<b>解释：</b>"2/4" 不是最简分数，因为它可以化简为 "1/2" 。 
</pre>

<br>

**示例 4：**

<pre>
<b>输入：</b>n = 1  
<b>输出：</b>[]
</pre>

<br>

**提示：**

* `1 <= n <= 100`