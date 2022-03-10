**最终代码：**

```java
class Solution {
    public int maximumDifference(int[] nums) {
        int n = nums.length;
        int ans = -1, min = nums[0];
        for (int i = 1; i < n; ++i) {
            // 如果后面的数大，就求差值，并比较之前的差值
            if (nums[i] > min) {
                ans = Math.max(ans, nums[i] - min);
            } else {
                // 如果小就替换
                min = nums[i];
            }
        }
        return ans;
    }
}
```

