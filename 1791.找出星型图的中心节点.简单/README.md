## 1791.找出星型图的中心节点-<font color=#5AB726>简单</font>

有一个无向的 **星型** 图，由 `n` 个编号从 `1` 到 `n` 的节点组成。星型图有一个 **中心** 节点，并且恰有 `n - 1` 条边将中心节点与其他每个节点连接起来。

给你一个二维整数数组 `edges` ，其中 <code>edges[i] = [u<sub>i</sub>, v<sub>i</sub>]</code> 表示在节点 <code>u<sub>i</sub></code> 和 <code>v<sub>i</sub></code> 之间存在一条边。请你找出并返回 `edges` 所表示星型图的中心节点。<br>

<br>

**示例 1：**

![](../resources/img/1791.找出星型图的中心节点-1.png)

<pre>
<b>输入：</b>edges = [[1,2],[2,3],[4,2]]
<b>输出：</b>2
<b>解释：</b>如上图所示，节点 2 与其他每个节点都相连，所以节点 2 是中心节点。 
</pre>


<br>

**示例 2：**

<pre>
<b>输入：</b>edges = [[1,2],[5,1],[1,3],[1,4]]
<b>输出：</b>1
</pre>

<br>

**提示：**

- `3 <= n <= 105`
- `edges.length == n - 1`
- `edges[i].length == 2`
- <code>1 <= u<sub>i</sub>, v<sub>i</sub> <= n</code>
- <code>u<sub>i</sub> != v<sub>i</sub></code>
- 题目数据给出的 `edges` 表示一个有效的星型图