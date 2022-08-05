```python
def binary_search(arr, val):
	# check midpoint, make progressively smaller windows
	low = 0
	high = len(arr)
	while result != val:
		midpoint = (high - low) / 2
		result = arr[midpoint]
		if result > val:
			low = midpoint
			midpoint = (high - low) / 2

```****