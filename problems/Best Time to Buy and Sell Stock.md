# [Best Time to Buy and Sell Stock](https://leetcode.com/problems/best-time-to-buy-and-sell-stock/)

## O(n^2)

```js
/**
* @param {number[]} prices
* @return {number}
*/

var maxProfit = function(prices) {
    var max = 0;
    var sellDate = prices.length-1;
    var buyDate = prices.length-2;
    // i = buy date
    // j = sell date

    for(var i = 0; i < prices.length-1; i++){
        var buyPrice = prices[i];
        for(var j = i+1; j <prices.length; j++){
            var sellPrice = prices[j];
            if (sellPrice-buyPrice > max){
                max = sellPrice-buyPrice;
            }
        }
    }

    return max;
};

```
## Single pass O(n)
```js
/**
* @param {number[]} prices
* @return {number}
*/

var maxProfit = function(prices) {
    var largestDiff=0
    var minSoFar = 100000000000;

    for (var i = 0; i<prices.length;i++){
        if (prices[i] < minSoFar){
            minSoFar = prices[i];
        }

        else{
            largestDiff = Math.max(largestDiff, prices[i] - minSoFar)
        }
    }
    
    return largestDiff;
};
```