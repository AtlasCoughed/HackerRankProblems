You are climbing a stair case. It takes n steps to reach to the top.

Each time you can either climb 1 or 2 steps. In how many distinct ways can you climb to the top?

Note: Given n will be a positive integer.

Example 1:

Input: 2
Output: 2
Explanation: There are two ways to climb to the top.
1. 1 step + 1 step
2. 2 steps
Example 2:

Input: 3
Output: 3
Explanation: There are three ways to climb to the top.
1. 1 step + 1 step + 1 step
2. 1 step + 2 steps
3. 2 steps + 1 step


```
/**
 * @param {number} n
 * @return {number}
 */
var climbStairs = function(n) {
    if(n == 1) return 1;
    else if(n == 2) return 2;
    // else if(n > 2) return climbStairs(n-1) + climbStairs(n-2);
    else if(n > 2) {
        let nums = [];
        nums[1] = 1;
        nums[2] = 2;
        for(let i=3; i<=n; i++){
            nums[i] = nums[i-1] + nums[i-2];   
        }
        return nums[n]
    }
};
```
