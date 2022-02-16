# [Maximum Subarray](https://leetcode.com/problems/maximum-subarray/submissions/)

## Dynamic Programming, Kadane's Algorithm
```js
/**
 * @param {number[]} nums
 * @return {number}
 */
var maxSubArray = function(nums) {
    // any subarray whose sum is positive is worth keeping
    var currentSubarray = nums[0];
    var maxSubarray = nums[0];
    
    for (var i = 1; i < nums.length; i++){
        currentSubarray = Math.max(nums[i], currentSubarray + nums[i]);
        maxSubarray = Math.max(maxSubarray, currentSubarray);
    }
    
    return maxSubarray
};
```