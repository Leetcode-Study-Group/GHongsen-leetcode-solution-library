**最终代码：**

```go
func maxNumberOfBalloons(text string) int {
   letter := [26]int{}
   for _, ch := range text {
      letter[ch-'a']++
   }
   letter['l'-'a'] /= 2
   letter['o'-'a'] /= 2
   ans := min(min(min(min(letter['b'-'a'], letter['a'-'a']), letter['l'-'a']), letter['o'-'a']), letter['n'-'a'])
   return ans
}

func min(a int, b int) int {
   if a < b {
      return a
   }
   return b
}
```

