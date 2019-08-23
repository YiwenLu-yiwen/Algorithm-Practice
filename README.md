# Personal-Leetcode
## Personal Summary of LeetCode
(Q21)
Create all possible solution \
Approach 1: Brute Force
Generate each and calculate valid or not
```python
def generate(A = []):
            if len(A) == 2*n:
                if valid(A):
                    ans.append("".join(A))
            else:
                A.append('(')
                generate(A)
                A.pop()
                A.append(')')
                generate(A)
                A.pop()
```
Approach 2: Backtracking
```python
def backtrack(S = '', left = 0, right = 0):
            if len(S) == 2 * N:
                ans.append(S)
                return
            if left < N:
                backtrack(S+'(', left+1, right)
            if right < left:
                backtrack(S+')', left, right+1)
```
Approach 3: DP (Unknown)


Merge two lists(fastest)
```python
def merge2Lists(self, l1, l2):
          head = point = ListNode(0)
          while l1 and l2:
              if l1.val <= l2.val:
                  point.next = l1
                  l1 = l1.next
              else:
                  point.next = l2
                  l2 = l1
                  l1 = point.next.next
              point = point.next
          if not l1:
              point.next=l2
          else:
              point.next=l1
          return head.next
```
Enumerate:
``` python
my_list = ['apple', 'banana', 'grapes', 'pear']
counter_list = list(enumerate(my_list, 1))
print(counter_list)
Output: [(1, 'apple'), (2, 'banana'), (3, 'grapes'), (4, 'pear')]
```
When we do ListNode questions: \
    1. if we want to use ListNode(item).next.val: make sure it has values \
    2. None in ListNode has no values \
    $if head is a listnode$ \
    3. if we do current = head, everything changed in head will appear in current

```python
class ListNode:
     def __init__(self, x):
         self.val = x
         self.next = None
```
Example: Q24 \
Right answer:
```python
class Solution:
    def swapPairs(self, head: ListNode) -> ListNode:
        tmp = sub = head
        pre = None
        cnt = 0
        while head != None and head.next != None:
            cnt += 1
            pre = head.val
            sub.val = head.next.val
            sub.next.val = pre
            sub = sub.next.next
            head = head.next.next
        if cnt == 0:
            return head
        else:
            return tmp
```
Wrong: 
```python
class Solution:
    def swapPairs(self, head: ListNode) -> ListNode:
        tmp = sub = ListNode(None) #### Difference
        pre = None
        cnt = 0
        while head != None and head.next != None:
            cnt += 1
            pre = head.val
            sub = head.next
            sub.next = ListNode(pre)
            sub = sub.next.next
            head = head.next.next
        if cnt == 0:
            return head
        else:
            return tmp
```
