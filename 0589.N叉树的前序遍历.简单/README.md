## 589.N叉树的前序遍历-<font color=#5AB726>简单</font>

给定一个 n 叉树的根节点  `root` ，返回 *其节点值的 **前序遍历*** 。

n 叉树 在输入中按层序遍历进行序列化表示，每组子节点由空值 `null` 分隔（请参见示例）。

<br>

**示例 1：**

![](../resources/img/589.N叉树的前序遍历-1.png)

<pre>
<b>输入：</b>root = [1,null,3,2,4,null,5,6]
<b>输出：</b>[1,3,5,6,2,4]
</pre>



<br>

**示例 2：**

![](../resources/img/589.N叉树的前序遍历-2.png)

<pre>
<b>输入：</b>root = [1,null,2,3,4,5,null,null,6,7,null,8,null,9,10,null,null,11,null,12,null,13,null,null,14]
<b>输出：</b>[1,2,3,6,7,11,14,4,8,12,5,9,13,10]
</pre>


<br>

**提示：**

* 节点总数在范围 <code>[0, 10<sup>4</sup>]</code>内
* <code>0 <= Node.val <= 10<sup>4</sup></code>
* n 叉树的高度小于或等于 `1000`