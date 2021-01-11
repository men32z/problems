# problems

# 1
```
function findSum(arr, sumValue) {
		for (let j = 0; j < arr.length; j++) {
			for (let i = (j + 1); i < arr.length; i++) {
				if(sumValue == arr[i] + arr[j]) return [i, j];
			}
		}
		return null;
	}
```