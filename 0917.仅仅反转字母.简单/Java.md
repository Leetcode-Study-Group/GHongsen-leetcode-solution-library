**最终代码**

```java
public String reverseOnlyLetters(String s) {
	char[] chars = s.toCharArray();
	for (int i = 0, j = chars.length - 1; i < j; i++, j--) {
		while (i < j && !Character.isLetter(chars[i])) i++;
		while (i < j && !Character.isLetter(chars[j])) j--;
		if (i < j) {
			chars[i] ^= chars[j];
			chars[j] ^= chars[i];
			chars[i] ^= chars[j];
		}
	}
	return String.valueOf(chars);
}
```

