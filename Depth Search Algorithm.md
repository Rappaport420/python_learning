---
tags:
  - DFS
  - recursive
  - linked_lists
---
[104. Maximum Depth of Binary Tree](https://leetcode.com/problems/maximum-depth-of-binary-tree/)

Given the `root` of a binary tree, return _its maximum depth_.
A binary tree's **maximum depth** is the number of nodes along the longest path from the root node down to the farthest leaf node.

```
# Definition for a binary tree node.
# class TreeNode:
	# def __init__(self, val=0, left=None, right=None):
		# self.val = val
		# self.left = left
		# self.right = right
class Solution:
	def maxDepth(self, root: Optional[TreeNode]) -> int:
		if not root:
			return 0
		return 1 + max(self.maxDepth(root.left), self.maxDepth(root.right))
```


Tu je framework ako nad tým myslieť **vždy**:

1. **Base case** — kedy sa zastavím? (zvyčajne `None`, prázdny vstup, alebo `n == 0`)

2. **Čo robí jedna úroveň?** — zabudni na celý strom, zamysli sa len nad **jedným** nodom. Čo on vie a čo potrebuje od detí?

3. **Čo vrátiš nahor?** — čo potrebuje rodič od teba?

---

Pri `maxDepth`:

- Jeden node vie: "som tu, teda +1"
- Potrebuje od detí: ich maximálnu hĺbku
- Vráti nahor: `1 + max(ľavá, pravá)`