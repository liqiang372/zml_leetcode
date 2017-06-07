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