

**最终代码：**

```java
class Solution {
    public List<Integer> pancakeSort(int[] arr) {
        List<Integer> ans = new ArrayList<>();
        int len = arr.length;

        for (int i = len; i > 0; i--) {
            for (int j = 0; j < i - 1; j++) {
                if (arr[j] == i) {
                    if (j != 0) {
                        move(arr,j);
                        ans.add(j+1);
                    }
                    move(arr,i-1);
                    ans.add(i);
                    len--;
                    i = len+1;
                }
            }
        }
        return ans;

    }

    public void move(int[] arr,int len){
        for (int i = 0,j = len; i < j; i++,j--) {
            arr[i]^=arr[j];
            arr[j]^=arr[i];
            arr[i]^=arr[j];
        }
    }
}
```

