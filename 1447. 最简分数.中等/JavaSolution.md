**解题思路：**

已知：

* ``2 <= 分母 <= n``

* ``1 <= 分子 <= 分母``  

可以写出循环

```java
for (byte denominator = 2; denominator <= n; denominator++) {
  for (byte numerator = 1; numerator < denominator; numerator++) {
    // 逻辑代码
  }
}
```

剩下的只要求出当前分子分母组成的分数是否是 **最简** 分数（即判断两个数的最大公约数是否为1）；

利用递归实现 `欧几里得算法` 求出两数最小公约数是否为1；

```java
public int gcd(int denominator, int numerator) {
  if (numerator == 0) {
    return denominator;
  }
  return gcd(numerator, denominator % numerator);
}
```



**最终代码：**

```java
public List<String> simplifiedFractions(int n) {
  List<String> ans = new ArrayList<>();
  for (int denominator = 2; denominator <= n; denominator++) {
    for (int numerator = 1; numerator < denominator; numerator++) {
      if (gcd(denominator, numerator) == 1) {
        ans.add(numerator + "/" + denominator);
      }
    }
  }
  return ans;
}
public int gcd(int denominator, int numerator) {
  return numerator == 0 ? denominator : gcd(numerator, denominator % numerator);
}
```

