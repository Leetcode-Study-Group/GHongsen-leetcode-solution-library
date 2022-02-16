**最终代码：**

```java
public List<Integer> luckyNumbers(int[][] matrix) {
	List<Integer> luckyNumbers = new ArrayList<>();
	for (int[] ints : matrix) {
		int[] colMinIndex = getMin(ints);
		int col = 0;
		for (; col < matrix.length; col++) {
			if (colMinIndex[0] < matrix[col][colMinIndex[1]]) {
				break;
			}
		}
		if (col == matrix.length){
			luckyNumbers.add(colMinIndex[0]);
		}
	}
	return luckyNumbers;
}
private int[] getMin(int[] ints) {
	int min = ints[0];
	int index = 0;
	for (int i = 1; i < ints.length; i++) {
		if (ints[i] < min) {
			min = ints[i];
			index = i;
		}
	}
	return new int[]{min, index};
}
```

