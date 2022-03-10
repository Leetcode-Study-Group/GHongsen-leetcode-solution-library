**最终代码：**

```go
func preorder(root *Node) (ans []int) {
	dfs(root, &ans)
	return ans
}
func dfs(node *Node, res *[]int) {
	if node == nil {
		return
	}
	*res = append(*res, node.Val)
	for _, child := range node.Children {
		dfs(child, res)
	}
}
```

