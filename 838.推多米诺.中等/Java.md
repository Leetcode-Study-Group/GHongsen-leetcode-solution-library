**最终代码：**

```java
public String pushDominoes(String dominoes) {
	char[] chars = dominoes.toCharArray();
	int i = 0;
	int n = chars.length;
	char start = 'L';
	char end;
	while (i < n) {
		int endIndex = i;
		// 连续的直立多米诺骨牌
		while (endIndex < n && chars[endIndex] == '.') endIndex++;
		// 如果 直立多米诺骨牌的最左侧跟前面相同 则中间的全部变为与两边一样
		end = endIndex >= n ? 'R' : chars[endIndex];
		if (end == start) {
			while (i < endIndex) {
				chars[i++] = start;
			}
		} else if (start == 'R' && end == 'L') {
			int k = endIndex - 1;
			while (i < k) {
				chars[i++] = 'R';
				chars[k--] = 'L';
			}
		}
		start = end;
    i = endIndex + 1;
	}
	return String.valueOf(chars);
}

```

