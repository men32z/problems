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

# 2

```
function countOccurences(strValue) {
		let letters = [];
		strValue.split('').forEach(x => {
			letters[x] = letters[x] > 0 ? letters[x] + 1 : 1;
		});
		return letters;
	}
```

# 3

```
function countPeaks(arr) {
	let peaks = 0;
	arr.push(0);
	arr.unshift(0);
	console.log(arr);
	let equals = 0;
	let equalsFI = null;
	for (let i = 1; i < arr.length - 1; i++) {
		if(arr[i] > arr[i + 1] && arr[i] >= arr[i - 1]) {
			if(!equalsFI || arr[i] >= arr[equalsFI - 1]) equals = 0;
			peaks = peaks + 1 + equals;
			equals = 0;
			equalsFI = 0;
		} else if (arr[i] == arr[i+1]) {
			equals += 1;
			if(!equalsFI) equalsFI = i;
		} else {
			equals = 0;
			equalsFI = null;
		}
	}
	return peaks;
}
```