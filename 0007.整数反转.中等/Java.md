**最终代码：**

```java
class Solution {
    public int reverse(int x) {
        int temp = 0;
        while (x != 0) {
            if (temp * 10 /10 != temp) {
                return 0;
            }
            temp = temp * 10 + x % 10;
            x /= 10;
        }
        return temp;
    }
}
```

