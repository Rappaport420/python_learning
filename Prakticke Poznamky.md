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

Viem assignut viacero premien naraz
```
a,b = b, a % b
```

Vytvorenie listu plneho nul 
```
# Creating a list of size n filled with 0
a = [0] * n
```
# List Comprehension #

- Je rýchlejši ako klasicky for cyklus ale vie iba čitat nie prepisovat 

Tento zapis:
```
return [i + extraCandies >= m_value for i in candies]
```
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


SET je rychlejši ako string alebo list 
preto ak napr som chcel hladat samohlasky v stringu spravil som si zoznam na porovnavanie obsahujuci všeky samohlasky. Na takyto usecase je najlepšie použit set: **vowels = {'a', 'e', 'i', 'o', 'u'}** 


Sprav poznamky 

SET vs LIST vs STRING vs HASHTABLE