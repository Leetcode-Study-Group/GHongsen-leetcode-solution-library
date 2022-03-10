## [3. 无重复字符的最长子串](https://leetcode-cn.com/problems/longest-substring-without-repeating-characters/)-<font color=#FFA119>中等</font>

给定一个字符串 `s` ，请你找出其中不含有重复字符的 **最长子串** 的长度。  <br>

<br>

**示例 1：**

<pre>
<b>输入：</b>s = "abcabcbb"
<b>输出：</b>3 
<b>解释：</b>因为无重复字符的最长子串是 "abc"，所以其长度为 3。
</pre>

<br>

**示例 2：**

<pre>
<b>输入：</b>s = "bbbbb"
<b>输出：</b>1
<b>解释：</b>因为无重复字符的最长子串是 "b"，所以其长度为 1。
</pre>

<br>

**示例 3：**

<pre>
<b>输入：</b>s = "pwwkew"
<b>输出：</b>3
<b>解释：</b>因为无重复字符的最长子串是 "wke"，所以其长度为 3。
     请注意，你的答案必须是 子串 的长度，"pwke" 是一个子序列，不是子串。
</pre>


<br>

**提示：**

- <code>0 <= s.length <= 5 * 10<sup>4</sup></code>
- `s` 由英文字母、数字、符号和空格组成