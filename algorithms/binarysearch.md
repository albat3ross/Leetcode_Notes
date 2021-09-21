# Binary Search
[Intro link](https://algo.monster/problems/binary_search_intro)

## Example code
```python
def binary_search(arr: List[int], target: int) -> int:
    left, right = 0, len(arr) - 1
    while left <= right:  # note the <=
        mid = (left + right) // 2 
        if arr[mid] > target:
            right = mid - 1  # basic operation will be discard mid
        if arr[mid] < target:
            left = mid + 1
        else:
            return mid
    return -1
```

## Notes
- About the end loop: generally we should consider equality case, they cover the edge case when there's only 1 element in range.
- Should we discard mid: in classic binary search we should just discard it since it does not fit the target
