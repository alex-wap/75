# [Contains Duplicate](https://leetcode.com/problems/contains-duplicate/)

```js
/**
* @param {number[]} nums
* @return {boolean}
*/

var containsDuplicate = function(nums) {
    // hash map
    // if already contains value, return true
    var numsMap = {};

    for (var i = 0; i < nums.length; i++){
        if (numsMap[nums[i]] == null){
            numsMap[nums[i]] = 0;
        }
        else{
            return true;
        }
    }

    return false;
};
```