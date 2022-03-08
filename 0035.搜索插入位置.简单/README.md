## 35.搜索插入位置-<font color=#5AB726>简单</font>

给定一个排序数组和一个目标值，在数组中找到目标值，并返回其索引。如果目标值不存在于数组中，返回它将会被按顺序插入的位置。

请必须使用时间复杂度为 `O(log n)` 的算法。

<br>

**示例 1：**

<pre>
<b>输入：</b>nums = [1,3,5,6], target = 5
<b>输出：</b>2
</pre>

<br>

**示例 2：**

<pre>
<b>输入：</b>nums = [1,3,5,6], target = 2
<b>输出：</b>1
</pre>

<br>

**示例 3：**

<pre>
<b>输入：</b>nums = [1,3,5,6], target = 7
<b>输出：</b>4
</pre>

<br>

**示例 4：**

<pre>
<b>输入：</b>nums = [1,3,5,6], target = 0
<b>输出：</b>0
</pre>

<br>

**示例 5：**

<pre>
<b>输入：</b>nums = [1], target = 0
<b>输出：</b>0
</pre>

<br>

**提示：**

- <code>1 <= nums.length <= 10<sup>4</sup></code>
- <code>-10<sup>4</sup> <= nums[i] <= 10<sup>4</sup></code>
- `nums` 为**无重复元素**的**升序**排列数组
- <code>-10<sup>4</sup> <= target <= 10<sup>4</sup></code>