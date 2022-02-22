**最终代码：**

```java
class Solution {
    public boolean isOneBitCharacter(int[] bits) {
        for (int i = 0; i < bits.length; i = bits[i] + i + 1) {
            if (i == bits.length - 1) {
                return true;
            }
        }
        return false;
    }
}
```

