**最终代码：**

```java
class Solution {
    public int[] twoSum(int[] nums, int target) {
        // 循环数组
        for (int i = 0; i < nums.length; i++) {
            // 查询与nums[i]相加等于target的数存在数组中么
            int temp = getArrayOfIndex(nums, target - nums[i], i);
            // temp大于0说明找到了 返回当前下标和对应数字的下标
            if (temp >= 1) {
                return new int[]{i, temp};
            }
        }
        return new int[0];
    }

    /**
     * 找出起始index之后有没有数字a  并返回下标
     */
    public static int getArrayOfIndex(int[] nums, int a, int startIndex) {
        // 循环数组后半段即可，前半段都循环过不需要再循环
        for (int i = startIndex + 1; i < nums.length; i++) {
            // 找到就返回下标
            if (nums[i] == a) {
                return i;
            }
        }
        return -1;
    }
}
```

