**解题思路：**

​	已知：题目中提到要求出数组中 `k` 个数的 **最小差值** ，求最小差值最好的办法是先将数组排好序，直接使用 `sort.Ints(` 对数组进行排序，然后根据 `k` 的大小来决定比较范围，循环比较，这种一般称为「[滑动窗口](../算法/滑动窗口.md)」，然后比较窗口内的最大最小差值，记录每组对比最后保留最小的差值返回；



**最终代码：**

```java
func minimumDifference(nums []int, k int) (ans int) {
	ans = math.MaxInt32
	// 排序
	sort.Ints(nums)
	// 将数组切片利用下标进行比较，滑动窗口无需循环整个数组
	for key, value := range nums[k-1:] {
		// 切片后的数组，当前value是窗口最大值，下标对应的是窗口最小值
		ans = min(value-nums[key], ans)
	}
	return
}
func min(a, b int) int {
	if a > b {
		return b
	}
	return a
}
```

