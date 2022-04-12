---
title: 1.两数之和 # 文章标题，强烈建议填写此选项
name_en: two-sum # 文章英文名用于地址访问避免地址栏中文
date: 2022-04-12 16:58:01 # 发布时间，强烈建议填写此选项，且最好保证全局唯一
author: 洪森 # 文章作者
img: # 文章特征图，推荐使用图床(腾讯云、七牛云、又拍云等)来做图片的路径.如: http://xxx.com/xxx.jpg
top: false # 推荐文章（文章是否置顶），如果 top 值为 true，则会作为首页推荐文章
hide: false # 隐藏文章，如果hide值为true，则文章不会在首页显示
cover: false # v1.0.2版本新增，表示该文章是否需要加入到首页轮播封面中
coverImg: # v1.0.2版本新增，表示该文章在首页轮播封面需要显示的图片路径，如果没有，则默认使用文章的特色图片
password: # 文章阅读密码，如果要对文章设置阅读验证密码的话，就可以设置 password 的值，该值必须是用 SHA256 加密后的密码，防止被他人识破。前提是在主题的 config.yml 中激活了 verifyPassword 选项
toc: true # 是否开启 TOC，可以针对某篇文章单独关闭 TOC 的功能。前提是在主题的 config.yml 中激活了 toc 选项
mathjax: false # 是否开启数学公式支持 ，本文章是否开启 mathjax，且需要在主题的 _config.yml 文件中也需要开启才行
summary: 力扣简单题：01.两数之和 # 文章摘要，自定义的文章摘要内容，如果这个属性有值，文章卡片摘要就显示这段文字，否则程序会自动截取文章的部分内容作为摘要
categories: leecode # 文章分类，本主题的分类表示宏观上大的分类，只建议一篇文章一个分类
tags: # 文章标签，一篇文章可以多个标签
 - leecode
 - java
keywords: # 文章关键字
reprintPolicy: cc_by # 文章转载规则， 可以是 cc_by, cc_by_nd, cc_by_sa, cc_by_nc, cc_by_nc_nd, cc_by_nc_sa, cc0, noreprint 或 pay 中的一个
---

## [1. 两数之和](https://leetcode-cn.com/problems/two-sum/)-<font color=#5AB726>简单</font>

给定一个整数数组 `nums` 和一个整数目标值 `target`，请你在该数组中找出 **和为目标值** *`target`* 的那 **两个** 整数，并返回它们的数组下标。

你可以假设每种输入只会对应一个答案。但是，数组中同一个元素在答案里不能重复出现。

你可以按任意顺序返回答案。

<br>

**示例 1：**
<pre>
<b>输入：</b> nums = [2,7,11,15], target = 9  
<b>输出：</b> [0,1]
<b>解释：</b> 因为 nums[0] + nums[1] == 9 ，返回 [0, 1] 。
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

## 最终代码

### Java

```java
class Solution {
    public int[] twoSum(int[] nums, int target) {
        // 循环数组
        for (int i = 0; i < nums.length; i++) {
            // 查询与nums[i]相加等于target的数存在数组中么
            int temp = getArrayOfIndex(nums, target - nums[i], i);
            // temp大于0说明找到了 返回当前下标和对应数字的下标
            if (temp >= 1) {
                return new int[]{i, temp};
            }
        }
        return new int[0];
    }

    /**
     * 找出起始index之后有没有数字a  并返回下标
     */
    public static int getArrayOfIndex(int[] nums, int a, int startIndex) {
        // 循环数组后半段即可，前半段都循环过不需要再循环
        for (int i = startIndex + 1; i < nums.length; i++) {
            // 找到就返回下标
            if (nums[i] == a) {
                return i;
            }
        }
        return -1;
    }
}
```

### Golang

### C#