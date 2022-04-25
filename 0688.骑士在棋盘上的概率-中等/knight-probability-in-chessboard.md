---
title: 688.骑士在棋盘上的概率 # 文章标题，强烈建议填写此选项
name_en: knight-probability-in-chessboard # 文章英文名用于地址访问避免地址栏中文
date: 2022-04-20 18:01:23 # 发布时间，强烈建议填写此选项，且最好保证全局唯一
author: 洪森 # 文章作者
img: # 文章特征图，推荐使用图床(腾讯云、七牛云、又拍云等)来做图片的路径.如: http://xxx.com/xxx.jpg
top: false # 推荐文章（文章是否置顶），如果 top 值为 true，则会作为首页推荐文章
hide: false # 隐藏文章，如果hide值为true，则文章不会在首页显示
cover: false # v1.0.2版本新增，表示该文章是否需要加入到首页轮播封面中
coverImg: # v1.0.2版本新增，表示该文章在首页轮播封面需要显示的图片路径，如果没有，则默认使用文章的特色图片
password: # 文章阅读密码，如果要对文章设置阅读验证密码的话，就可以设置 password 的值，该值必须是用 SHA256 加密后的密码，防止被他人识破。前提是在主题的 config.yml 中激活了 verifyPassword 选项
toc: true # 是否开启 TOC，可以针对某篇文章单独关闭 TOC 的功能。前提是在主题的 config.yml 中激活了 toc 选项
mathjax: false # 是否开启数学公式支持 ，本文章是否开启 mathjax，且需要在主题的 _config.yml 文件中也需要开启才行
summary: 力扣中等题：688.骑士在棋盘上的概率 # 文章摘要，自定义的文章摘要内容，如果这个属性有值，文章卡片摘要就显示这段文字，否则程序会自动截取文章的部分内容作为摘要
categories: leecode # 文章分类，本主题的分类表示宏观上大的分类，只建议一篇文章一个分类
tags: # 文章标签，一篇文章可以多个标签
 - leecode
 - java
keywords: # 文章关键字
reprintPolicy: cc_by # 文章转载规则， 可以是 cc_by, cc_by_nd, cc_by_sa, cc_by_nc, cc_by_nc_nd, cc_by_nc_sa, cc0, noreprint 或 pay 中的一个
---

## [688. 骑士在棋盘上的概率](https://leetcode-cn.com/problems/knight-probability-in-chessboard/)-<font color=#FFA119>中等</font>

在一个 `n x n` 的国际象棋棋盘上，一个骑士从单元格 `(row, column)` 开始，并尝试进行 `k` 次移动。行和列是 **从 0 开始** 的，所以左上单元格是 `(0,0)` ，右下单元格是 `(n - 1, n - 1)` 。  

象棋骑士有8种可能的走法，如下图所示。每次移动在基本方向上是两个单元格，e然后在正交方向上是一个单元格。  

![](https://cdn.jsdelivr.net/gh/Leetcode-Study-Group/GHongsen-leetcode-solution-library/resources/img/688.骑士在棋盘上的概率-1.png)

每次骑士要移动时，它都会随机从8种可能的移动中选择一种(即使棋子会离开棋盘)，然后移动到那里。  

骑士继续移动，直到它走了 `k` 步或离开了棋盘。  

返回 *骑士在棋盘停止移动后仍留在棋盘上的概率* 。  <br>

<br>

**示例 1：**

<pre>
<b>输入:</b> n = 3, k = 2, row = 0, column = 0  
<b>输出:</b> 0.0625  
<b>解释:</b> 有两步(到(1,2)，(2,1))可以让骑士留在棋盘上。  
在每一个位置上，也有两种移动可以让骑士留在棋盘上。  
骑士留在棋盘上的总概率是0.0625。  
</pre>

<br>

**示例 2：**

<pre>
<b>输入:</b> n = 1, k = 0, row = 0, column = 0
<b>输出:</b> 1.00000
</pre>

<br>

**提示：**

- `1 <= n <= 25`
- `0 <= k <= 100`
- `0 <= row, column <= n`

## 做题思路

## 最终代码

### Java

```java
class Solution {
    public double[][][] cache;
    public double knightProbability(int n, int k, int row, int column) {
        cache = new double[k + 1][n][n];
        double trueNum = dfs(n, k, row, column);
        double allNum = Math.pow(8,k);
        return trueNum / allNum;
    }

    public double dfs(int n, int k, int row, int column) {
        if (row < 0 || row >= n || column < 0 || column >= n) {
            return 0;
        }
        if (k == 0) {
            return 1;
        }
        if (cache[k][row][column] != 0) {
            return cache[k][row][column];
        }

        return cache[k][row][column] = dfs(n, k - 1, row - 1, column + 2)
                + dfs(n, k - 1, row - 1, column - 2)
                + dfs(n, k - 1, row + 1, column + 2)
                + dfs(n, k - 1, row + 1, column - 2)
                + dfs(n, k - 1, row - 2, column + 1)
                + dfs(n, k - 1, row - 2, column - 1)
                + dfs(n, k - 1, row + 2, column + 1)
                + dfs(n, k - 1, row + 2, column - 1);
    }
}
```

### Golang

### C#