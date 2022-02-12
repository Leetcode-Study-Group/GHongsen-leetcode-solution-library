**最终代码：**

```java
public int numEnclaves(int[][] grid) {
  int mun = 0;
  // 记录长宽
  int m = grid.length;
  int n = grid[0].length;
  // 第一行和最后一行的陆地
  for (int j = 0; j < n; j++) {
    dfs(0, j, grid);
    dfs(m - 1, j, grid);
  }
  // 第一列和最后一列的陆地
  for (int i = 1; i < m - 1; i++) {
    dfs(i, 0, grid);
    dfs(i, n - 1, grid);
  }
  // 计算没有靠边的陆地数量
  for (int i = 1; i < m - 1; i++) {
    for (int j = 1; j < n - 1; j++) {
      mun+=grid[i][j];
    }
  }
  return mun;
}
// 扩散
public void dfs(int i, int j, int[][] grid) {
  // 验证当前坐标是否有效
  if (i >= 0 && i < grid.length && j >= 0 && j < grid[0].length && grid[i][j] == 1) {
    // 沉没陆地为海洋 方便统计
    grid[i][j] = 0;
    // 向四方扩散
    dfs(i - 1, j, grid); // 上
    dfs(i + 1, j, grid); // 下
    dfs(i, j - 1, grid); // 左
    dfs(i, j + 1, grid); // 右
  }
}
```
