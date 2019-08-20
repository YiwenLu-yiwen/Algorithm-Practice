# Personal-Leetcode
## Personal Summary of LeetCode
### DAY1
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
