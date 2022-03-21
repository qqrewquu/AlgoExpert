第二次做还是没什么思路，看了答案才会写

```python
# O(n) Time | O(n) Space
def spiralTraverse(array):
	
	finalArray= []
	endRow = len(array)
	endCol = len(array[0])
	startRow = 0
	startCol = 0
	
	while startRow < endRow and startCol < endCol:
		for col in range(startCol,endCol):
			finalArray.append(array[startRow][col])
			
		for row in range(startRow+1,endRow):
			finalArray.append(array[row][endCol-1])
			
		for col in reversed(range(startCol,endCol-1)):
			# handle edge case when there is a single row in the midde of the matrix
			if startRow == endRow-1:
				break
			finalArray.append(array[endRow-1][col])
			
			
		for row in reversed(range(startRow+1,endRow-1)):
			# handle edge case when there is a single column in the midde of the matrix
			if startCol == endCol-1:
				break
			finalArray.append(array[row][startCol])
			
		startRow += 1
		startCol += 1
		endRow -= 1
		endCol -= 1
	
	return finalArray
			
			
			
		
	
		
	

```