# Sliding Windows
Two pointers.
Scan the list.
Quick and fast.


# Examples
[209. Minimum Size Subarray Sum](https://leetcode.com/problems/minimum-size-subarray-sum/)  
[862. Shortest Subarray with Sum at Least K](https://leetcode.com/problems/shortest-subarray-with-sum-at-least-k/) not solved yet  
[904. Fruit Into Baskets](https://leetcode.com/problems/fruit-into-baskets/)  
[992. Subarrays with K Different Integers](https://leetcode.com/problems/subarrays-with-k-different-integers/)
[]()
[]()


# templates
max array length with k different elements
```python3
def maxArrkEle(self, nums, k):
    count, i = {}, 0
    for j, v in enumerate(nums):
        count[v] = count.get(v, 0) + 1
        if len(count) > k:
            count[nums[i]] -= 1
            if count[nums[i]] == 0: del count[nums[i]]
            i += 1
    return j - i + 1
```

number of subarrays with at most k different elements
```python3
def atMostkEle(self, A, K):
    count = collections.Counter()
    res = i = 0
    for j in range(len(A)):
        if count[A[j]] == 0: K -= 1
        count[A[j]] += 1
        while K < 0:
            count[A[i]] -= 1
            if count[A[i]] == 0: K += 1
            i += 1
        res += j - i + 1
    return res
```

number of subarrays with at most k sum
```python3
def atMostkSum(self, A, S):
    if S < 0: return 0
    res = i = 0
    for j in range(len(A)):
        S -= A[j]
        while S < 0:
            S += A[i]
            i += 1
        res += j - i + 1
    return res
```