**最终代码：**

```java
class Solution {
    public double[][][] cache;
    public double knightProbability(int n, int k, int row, int column) {
        cache = new double[k + 1][n][n];
        double trueNum = dfs(n, k, row, column);
        double allNum = Math.pow(8,k);
        return trueNum / allNum;
    }

    public double dfs(int n, int k, int row, int column) {
        if (row < 0 || row >= n || column < 0 || column >= n) {
            return 0;
        }
        if (k == 0) {
            return 1;
        }
        if (cache[k][row][column] != 0) {
            return cache[k][row][column];
        }

        return cache[k][row][column] = dfs(n, k - 1, row - 1, column + 2)
                + dfs(n, k - 1, row - 1, column - 2)
                + dfs(n, k - 1, row + 1, column + 2)
                + dfs(n, k - 1, row + 1, column - 2)
                + dfs(n, k - 1, row - 2, column + 1)
                + dfs(n, k - 1, row - 2, column - 1)
                + dfs(n, k - 1, row + 2, column + 1)
                + dfs(n, k - 1, row + 2, column - 1);
    }
}
```

