一开始写的答案不是最优解。能想到每次for loop后面要比较当前的winTeam和bestTeam的分数，但是不会实现。

看了一下答案后得到最优解
```python
# O(n) Time | O(n) Space
def tournamentWinner(competitions, results):
	
	bestTeam = ""
	teamScores = {bestTeam:0}
	
	for i,compet in enumerate(competitions):
		winTeamIdx = abs(results[i]-1)
		winTeam = compet[winTeamIdx]
		
		if winTeam in teamScores:
			teamScores[winTeam] += 3
			
		else:
			teamScores[winTeam] = 3
			
			
		if teamScores[winTeam] > teamScores[bestTeam]:
			teamScores[bestTeam] = teamScores[winTeam]
			bestTeam = winTeam
			
	return bestTeam
			

	
# 	# O(nlogn) Time | O(n) Space
# 	teamScores = {}
	
# 	for i,compet in enumerate(competitions):
# 		winTeamIdx = abs(results[i]-1)
# 		winTeam = compet[winTeamIdx]
		
# 		if winTeam in teamScores:
# 			teamScores[winTeam] += 3
			
# 		else:
# 			teamScores[winTeam] = 3
			
		
# 	return sorted(teamScores.items(), key=lambda x: x[1],reverse=True)[0][0]
```