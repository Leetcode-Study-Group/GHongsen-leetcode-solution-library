## 1.两数之和-<font color=#5AB726>简单</font>

给定一个整数数组 `nums` 和一个整数目标值 `target`，请你在该数组中找出 **和为目标值** *`target`* 的那 **两个** 整数，并返回它们的数组下标。

你可以假设每种输入只会对应一个答案。但是，数组中同一个元素在答案里不能重复出现。

你可以按任意顺序返回答案。

<br>

**示例 1：**

<pre>
<b>输入：</b>nums = [2,7,11,15], target = 9
<b>输出：</b>[0,1]
<b>解释：</b>因为 nums[0] + nums[1] == 9 ，返回 [0, 1] 。
</pre>

<br>

**示例 2：**

<pre>
<b>输入：</b>nums = [3,2,4], target = 6
<b>输出：</b>[1,2]
</pre>


<br>

**示例 3：**

<pre>
<b>输入：</b>nums = [3,3], target = 6
<b>输出：</b>[0,1]
</pre>
<br>

**提示：**

- <code>2 <= nums.length <= 10<sup>4</sup></code>
- <code>-10<sup>9</sup> <= nums[i] <= 10<sup>9</sup></code>
- <code>-10<sup>9</sup> <= target <= 10<sup>9</sup></code>
- **只会存在一个有效答案**


**进阶：** 你可以想出一个时间复杂度小于 <code>O(n<sup>2</sup>)</code> 的算法吗？