**解题思路：**

已知：

* ``2 <= 分母 <= n``

* ``1 <= 分子 <= 分母``  

可以写出循环

```go
for denominator := 2; denominator <= n; denominator++ {
  for numerator := 1; numerator < denominator; numerator++ {
    // 逻辑代码
  }
}
```

剩下的只要求出当前分子分母组成的分数是否是 **最简** 分数（即判断两个数的最大公约数是否为1）；

利用递归实现「欧几里得算法」 求出两数最大公约数是否为1；

```go
func gcd(a, b int) int {
	for a != 0 {
		a, b = b%a, a
	}
	return b
}
```



**最终代码：**

```java
func simplifiedFractions(n int) (ans []string) {
  // 循环所有分母小于n的分数
	for denominator := 2; denominator <= n; denominator++ {
		for numerator := 1; numerator < denominator; numerator++ {
      // 如果两个数最大公约数为1加入结果集
			if gcd(numerator, denominator) == 1 {
				ans = append(ans, strconv.Itoa(numerator)+"/"+strconv.Itoa(denominator))
			}
		}
	}
	return
}
// 欧几里得算法
func gcd(a, b int) int {
	for a != 0 {
		a, b = b%a, a
	}
	return b
}
```
