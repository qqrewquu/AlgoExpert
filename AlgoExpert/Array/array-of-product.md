能写出暴力解，但是没有最优解的思路。看了答案后写出来了


```python
# O(n) Time | O(n) Space
def arrayOfProducts(array):

	result = [1 for _ in range(len(array))]
	
	
	leftProduct = 1
	
	for i,num in enumerate(array):
		result[i] = leftProduct
		leftProduct *= num
	
	rightProduct = 1
	
	for i in reversed(range(len(array))):
		result[i] *= rightProduct
		rightProduct *= array[i]
	
	return result
	
	
	
	
```