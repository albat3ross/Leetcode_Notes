# BackTracking
[General approach](https://leetcode.com/problems/permutations/discuss/18239/A-general-approach-to-backtracking-questions-in-Java-(Subsets-Permutations-Combination-Sum-Palindrome-Partioning))

# Related Questions
### Basic

[78. Subsets]()  
[90. Subsets II]()  
[46. Permutations]()  
[47. Permutations II]()  
[39. Combination Sum]()  
[40. Combination Sum II]()  
[131. Palindrome Partitioning]()  

### Advanced


# Example code
```python
class Solution:
    def permute(self, nums: List[int]) -> List[List[int]]:
        def backtracking(pool, path, res):
            if not pool:
                res.append(path)  # End case
                return
            for i in range(len(pool)): # dfs
                bt(pool[:i]+pool[i+1:], path + [pool[i]], res)
                
        res = []
        backtracking(nums,[],res)
        return res
```

# Notes
- In python3 we can append path directly since every iteration we create a new path
- dfs part usually is where the trick at