---
tags:
  - Two_Pointers
  - array
---
---

Robil som úlohu [283. Move Zeroes](https://leetcode.com/problems/move-zeroes/) kde som použival dva vnorene while cykly 
(`while i` a v ňom `while j`). Keď som našiel nulu, moj `j` musel fyzicky "preupratovať" (poposúvať) všetky čísla až do konca. Ak som mal v poli 10 núl, 10-krát si zbytočne prebehol zvyšok poľa. To nie je Two Pointers, to je **Brute Force s posúvaním**.

Dva vnorene cykly do seba je zložitosť $O(n^2)$

### Kedy je to skutočný Two Pointers ? 

Mám dva indexy, ktoré žijú v **jednom** cykle (alebo v dvoch, ktoré sa neprekrývajú tak, aby násobili zložitosť).

1. **Fast Pointer (`i`):** Ten "skaut", ktorý beží vpred a hľadá zaujímavé veci (napr. nenulové čísla).
    
2. **Slow Pointer (`write`):** Ten "robotník", ktorý stojí a čaká, kým mu skaut povie: _"Mám to, zapíš to sem!"_.

```
class Solution:
	def moveZeroes(self, nums: List[int]) -> None:
	write = 0
	i = 0
	while i < len(nums):
		if nums[i] != 0:
			nums[write], nums[i] = nums[i], nums[write]
			write += 1
	i += 1
```

