**最终代码：**

```go
func singleNonDuplicate(nums []int) int {
	start, end := 0, len(nums)-1
	for start < end {
		mid := (end + start) / 2
		if nums[mid] == nums[mid^1] {
			start = mid + 1
		} else {
			end = mid
		}
	}
	return nums[start]
}
```

