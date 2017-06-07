把 2n 个数分成 n 个组，把每个组里面较小的数累加起来，找出最大值。

思路就是把数组排序，这样 奇数位的数字加起来就是最大值

```javascript
var arrayPairSum = function(nums) {
    nums.sort(function(a, b){
        return a - b;
    });
    var sum = 0;
    for (var i = 0; i < nums.length; i++) {
        // 这里注意是 3 个等号，查看 3个等号 和 2个等号的区别
        if ( i % 2 === 0) {
            sum += nums[i];
        }
    }
    return sum;
};
```

循环也可以写成

```javascript
var arrayPairSum = function(nums) {
    nums.sort(function(a, b){
        return a - b;
    });
    var sum = 0;
    nums.forEach(function(num, index) {
        // 查看 MDN, forEach 用法
        if (index % 2 === 0) {
            sum += num;
        }
    });
    return sum;
};
```


## 知识点
1. 对于数组的排序 [Array.prototype.sort()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/sort?v=control)
2. 对于数组的循环 [Array.prototype.forEach()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/forEach?v=control)
3. 3 个等号和2个等号的区别
    ```javascript
    0 == false   // true
    0 === false  // false, because they are of a different type
    1 == "1"     // true, automatic type conversion for value only
    1 === "1"    // false, because they are of a different type
    null == undefined // true
    null === undefined // false
    '0' == false // true
    '0' === false // false
    ```