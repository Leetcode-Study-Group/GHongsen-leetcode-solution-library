**最终代码：**

```go
func platesBetweenCandles(s string, queries [][]int) []int {
	n := len(s)
	sum := make([]int, n+1)
	left := make([]int, n)
	p := -1
	for i, b := range s {
		sum[i+1] = sum[i]
		if b == '|' {
			p = i
		} else { 
			sum[i+1]++
		}
		left[i] = p
	}

	right := make([]int, n)
	for i, p := n-1, n; i >= 0; i-- {
		if s[i] == '|' {
			p = i
		}
		right[i] = p
	}

	ans := make([]int, len(queries))
	for i, q := range queries {
		l, r := right[q[0]], left[q[1]]
		if l < r {
			ans[i] = sum[r] - sum[l]
		}
	}
	return ans
}
```

