---
tags:
  - recursive
  - linked_lists
---
---
Rekurzia je pri linked lists vždy horšia varianta 

**Iteratívna** — rýchlejšia, menej pamäte (O(1))  
**Rekurzívna** — pomalšia, viac pamäte (O(n) call stack)

Rekurzia sa používa keď je **kód čitateľnejší** alebo štruktúra problému je prirodzene rekurzívna (stromy, grafy). Nie kvôli výkonu.

Pre linked list reverse — iteratívna je vždy lepšia voľba. 💪

[2130. Maximum Twin Sum of a Linked List](https://leetcode.com/problems/maximum-twin-sum-of-a-linked-list/)

- tato uloha bola velmi zaujimava lebo kombinovala skills naučne v ulohe predtým cielom bolo najst najvačši sučet dvojic v liste pricom dvojice šli z kraja (prvy a posledny, druhy a predposledný, atd...)

1. V prvom kroku som musel najst stred (slow and fast pointer)
2. Nasledne ked som ho našiel rozdelil som pole na dve a to druhe revertol 
3. Do tretice som paralelne šiel obe polia prišom som hladal najvyšši sučet 

```
from typing import Optional

# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next

class Solution:

    def reverseList(self, head: Optional[ListNode]) -> Optional[ListNode]:
        if not head or not head.next:
            return head
        new_head = self.reverseList(head.next)
        head.next.next = head
        head.next = None
        return new_head
        
    def pairSum(self, head: Optional[ListNode]) -> int:
        if not head.next:
            return None
        elif not head.next.next:
            return head.val + head.next.val
            
        # Krok 1: Nájdi stred
        slow = head
        fast = head.next
        while fast.next and fast.next.next:
            slow = slow.next
            fast = fast.next.next
            
        # Krok 2: Otočí druhú polovicu
        second_head = slow.next
        reverted_head = self.reverseList(second_head)
        
        # Krok 3: Paralelný prechod, hľadaj max súčet
        var_r = reverted_head
        var_h = head
        max_val = head.val + reverted_head.val
        
        while var_r:
            if var_r.val + var_h.val > max_val:
                max_val = var_r.val + var_h.val
            var_r = var_r.next
            var_h = var_h.next
        return max_val
```