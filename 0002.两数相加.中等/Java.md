**最终代码：**

```java
class Solution {
  public ListNode addTwoNumbers(ListNode l1, ListNode l2) {
    ListNode tempList = new ListNode();
    // 保存头地址返回值
    ListNode first = tempList;

    // 记录进位是多少
    int carry = 0;

    while (l1 != null || l2 != null) {

      // 如果l1 l2 有元素 则将值累加到carry中
      if (l1 != null) {
        carry += l1.val;
        l1 = l1.next;
      }
      if (l2 != null) {
        carry += l2.val;
        l2 = l2.next;
      }

      // 如果carry大于等于10说明要进位，将余数赋值给val [两数相加如果进位 进位数只能是1]
      if (carry >= 10) {
        tempList.val = carry % 10;
        carry = 1;
      } else {
        tempList.val = carry;
        carry = 0;
      }
      if (l1 != null || l2 != null) {
        tempList.next = new ListNode();
        tempList = tempList.next;
      }
    }
    if (carry != 0) {
      tempList.next = new ListNode();
      tempList = tempList.next;
      tempList.val = 1;
    }
    return first;
  }
}
```

