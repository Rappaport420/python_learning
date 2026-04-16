---
tags:
  - array
  - Sliding_Window
---
---
Velmi podobný koncept k Two pointers. V podstate tiež použivam dva indexy ale definuju mi okno. 

Pristup:

#### 1. Shrinkable Window (To, čo máš ty)
Tento prístup okno agresívne zmenšuje (`while k < 0`), aby bolo v každom momente **legálne**.

- **Logika:** "Vždy, keď poruším pravidlo, zmenšujem okno, kým znova neplatí."
```
class Solution:
	def longestSubarray(self, nums: List[int]) -> int:
		left = 0
		max_win = 0
		k = 1
		for right in range(len(nums)):
			if nums[right] == 0:
				k -=1
			while k < 0:
				if nums[left] == 0:
					k += 1
				left += 1
			max_win = max(max_win, right-left+1)
		return max_win-1
```


#### 2. Non-Shrinkable Window (Elegantnejší "Fast" prístup)
Tento prístup je v komunite senior developerov veľmi obľúbený, pretože nevyžaduje vnútorný `while` cyklus. Okno sa nikdy nezmenšuje – ono len **rastie**, alebo **stagnuje** (posúva sa v konštantnej veľkosti).

```
class Solution:
    def longestSubarray(self, nums: List[int]) -> int:
        left = 0
        k = 1
        
        for right in range(len(nums)):
            if nums[right] == 0:
                k -= 1
            
            # ŽIADEN WHILE! Len jeden IF.
            if k < 0:
                if nums[left] == 0:
                    k += 1
                left += 1
        return right - left
```
