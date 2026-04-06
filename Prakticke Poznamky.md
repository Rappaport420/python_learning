---
tags:
  - code
---
---
# Tips and Tricks#

`result = []`
`"".join(result)`
- result je pole ktoreho obsah lepime na prazdny string a vraciama string - konverzia listu na string 
`return " ".join(my_list[::-1])`
- vlozi medzery medzi polozky listu 

`a,b = b, a % b`
- viem assignut viacero premien naraz

# List Comprehension #

- Je rýchlejši ako klasicky for cyklus ale vie iba čitat nie prepisovat 

Tento zapis:
`return [i + extraCandies >= m_value for i in candies]`
Je to iste ako tento:
```
result = []
for i in candies:
	if i + extraCandies >= m_value:
		result.append(True)
	else:
		result.append(False)
return result
```
