# 1. Two Sum
Given an array of integers nums and an integer target, return indices of the two numbers such that they add up to target.  
You may assume that each input would have exactly one solution, and you may not use the same element twice.  
You can return the answer in any order.  
## Thoughts
Solve it using HashMap, use number as Key and index as Value.


## Solution
``` java
class Solution {
    public int[] twoSum(int[] nums, int target) {
        HashMap<Integer,Integer> pool = new HashMap<Integer,Integer>();
        int[] res = {-1,-1};
        int index = 0;
        for (int i: nums){
            if (pool.containsKey(i)){
                res[0] = pool.get(i);
                res[1] = index;
                return res;
            }else{
                pool.put(target-i,index);
            }
            index ++;
        }
        return res;
    }
}
```