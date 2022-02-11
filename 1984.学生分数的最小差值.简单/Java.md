**解题思路：**

​	已知：题目中提到要求出数组中 `k` 个数的 **最小差值** ，求最小差值最好的办法是先将数组排好序，直接使用Java的工具类 `Arrays.sort()` 对数组进行排序，`Arrays.sort()` 使用的「**双轴快排**」直接使用就好了，然后根据 `k` 的大小来决定比较范围，循环比较，这种一般称为「**滑动窗口**」，然后比较窗口内的最大最小差值，记录每组对比最后保留最小的差值返回；



**最终代码：**

```java
public int minimumDifference(int[] nums, int k) {
  // Arrays.sort() 使用了双轴快排已经很快了直接使用
  Arrays.sort(nums);
  int min = Integer.MAX_VALUE;
  // 滑动窗口循环比较
  for (int i = k - 1;i < nums.length ;i++) {
    min = Math.min(nums[i]- nums[i-(k-1)],min);
  }
  return min;
}
```

