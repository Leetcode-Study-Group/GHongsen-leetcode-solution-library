**最终代码：**

```java
public int maxNumberOfBalloons(String text) {
  int[] letter = new int['z' + 1];
  for (char i : text.toCharArray()) {
    letter[i]++;
  }
  letter['l'] /= 2;
  letter['o'] /= 2;
  return Math.min(Math.min(Math.min(Math.min(letter['b'], letter['a']), letter['l']), letter['o']), letter['n']);
}
```

