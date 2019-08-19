# Personal-Leetcode
## Personal Summary of LeetCode
### D1
Create all possible solution (Q21)
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
