## 917.仅仅反转字母-<font color=#5AB726>简单</font>

给你一个字符串 `s` ，根据下述规则反转字符串：

- 所有非英文字母保留在原有位置。

- 所有英文字母（小写或大写）位置反转。

返回反转后的 `s` 。

<br>

**示例 1：**

<pre>
<b>输入：</b>s = "ab-cd"
<b>输出：</b>"dc-ba" 
</pre>



<br>

**示例 2：**

<pre>
<b>输入：</b>s = "a-bC-dEf-ghIj"
<b>输出：</b>"j-Ih-gfE-dCba"
</pre>



<br>

**示例 3：**

<pre>
<b>输入：</b>s = "Test1ng-Leet=code-Q!"
<b>输出：</b>"Qedo1ct-eeLg=ntse-T!"
</pre>


<br>

**提示：**

* `1 <= s.length <= 100`
* `s` 仅由 ASCII 值在范围 `[33, 122]` 的字符组成
* `s` 不含 `'\"'` 或 `'\\'`

