# [Product of Array Except Self](https://leetcode.com/problems/product-of-array-except-self/)

## O(n) space

```js
/**
 * @param {number[]} nums
 * @return {number[]}
 */
var productExceptSelf = function(nums) {
    answer = [];
    left = [];
    right = [];
    
    left[0]=1;
    for (var i = 1; i < nums.length; i++){
        left[i] = left[i-1]*nums[i-1];
    }
    
    right[nums.length - 1]=1;
    for (var j = nums.length-2; j >= 0; j--){
        right[j] = right[j+1]*nums[j+1];
    }
    
    for (var k = 0; k < nums.length; k++){
        answer[k] = left[k] * right[k];
    }
    
    return answer;
};
```
## O(1) space
```js
/**
 * @param {number[]} nums
 * @return {number[]}
 */
var productExceptSelf = function(nums) {
    answer = [];
    
    answer[0]=1;
    for (var i = 1; i < nums.length; i++){
        answer[i] = answer[i-1]*nums[i-1];
    }
    
    var right=1;
    for (var j = nums.length-1; j >= 0; j--){
        answer[j] = answer[j]*right;
        right  *= nums[j];
    }

    return answer;
};
```