



# Example code
```python
class Solution:
    def minDepth(self, root: Optional[TreeNode]) -> int:
        pool = [root] if root else []
        min_depth = 0
        while pool:
            min_depth += 1
            if [node for node in pool if not node.left and not node.right]:
                break
            pool = [kid for node in pool for kid in (node.left, node.right) if kid]
        return min_depth
```