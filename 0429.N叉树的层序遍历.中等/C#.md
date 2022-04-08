**最终代码：**

```c#
public class Solution {
    private readonly IList<IList<int>> _ans = new List<IList<int>>();
    public IList<IList<int>> LevelOrder(Node root)
    {
        Bfs(root,0);
        return _ans;
    }

    private void Bfs(Node root,int depth)
    {
        if (root == null)
        {
            return;
        }
        // 深度超过长度就延长一个
        if (_ans.Count <= depth)
        {
            _ans.Add(new List<int>());
        }
        
        _ans[depth].Add(root.val);

        if (root.children == null)
        {
            return;
        }
        foreach (var child in root.children)
        {
            Bfs(child,depth+1);
        }
    }
}
```

