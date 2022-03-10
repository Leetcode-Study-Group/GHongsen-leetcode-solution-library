## [2016. 增量元素之间的最大差值](https://leetcode-cn.com/problems/maximum-difference-between-increasing-elements/)-<font color=#5AB726>简单</font>

给你一个下标从 **0** 开始的整数数组 `nums` ，该数组的大小为 `n` ，请你计算 `nums[j] - nums[i]` 能求得的 **最大差值** ，其中 `0 <= i < j < n` 且 `nums[i] < nums[j]` 。

返回 **最大差值** 。如果不存在满足要求的 `i` 和 `j` ，返回 `-1` 。  <br>

<br>

**示例 1：**

<pre>
<b>输入：</b>nums = [7,<b>1</b>,<b>5</b>,4]
<b>输出：</b>4
<b>解释：</b>
最大差值出现在 i = 1 且 j = 2 时，nums[j] - nums[i] = 5 - 1 = 4 。
注意，尽管 i = 1 且 j = 0 时 ，nums[j] - nums[i] = 7 - 1 = 6 &gt; 4 ，但 i &gt; j 不满足题面要求，所以 6 不是有效的答案。
</pre>

<br>

**示例 2：**

<pre>
<b>输入：</b>nums = [9,4,3,2]
<b>输出：</b>-1
<b>解释：</b>
不存在同时满足 i &lt; j 和 nums[i] &lt; nums[j] 这两个条件的 i, j 组合。
</pre>

<br>

**示例 3：**

<pre>
<b>输入：</b>nums = [<b>1</b>,5,2,<b>10</b>]
<b>输出：</b>9
<b>解释：</b>
最大差值出现在 i = 0 且 j = 3 时，nums[j] - nums[i] = 10 - 1 = 9 。
</pre>

<br>

**提示：**

* `n == nums.length`
* `2 <= n <= 1000`
* <code>1 <= nums[i] <= 10<sup>9</sup></code>