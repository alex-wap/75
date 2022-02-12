# [Two Sum](https://leetcode.com/problems/two-sum/)

```js
/**
* @param {number[]} nums
* @param {number} target
* @return {number[]}
*/

var twoSum = function(nums, target) {
    var dict = {};

    for(var cur = 0;cur < nums.length; cur++){
        if(target-nums[cur] in dict){
            return [cur,dict[target-nums[cur]]];
        }

        else{
            dict[nums[cur]] = cur;
        }
    }
};