这道题主要是把每一个单词 reverse 

```javascript
var reverseWords = function(s) {
    return s.split(" ").map(function(str) {
        return str.split("").reverse().join("");
    }).join(" ");
};
```

JavaScript 中 `String` 没有 `reverse` method, 而 `Array` 有.

```javascript
s.split(" ") // 双引号中间是空格，代表要把这个string 从每个空格的地方隔开，形成 array

// "Let's take LeetCode contest" ===> ["Let's", "take", "LeetCode", "contest"]
```

然后对这个数组循环，对于每一个字符串都要reverse，方法是

```javascript
str.split(" ").reverse().join(""); // 这里可以自己试验一下
```
到这里我们得到的结果是

```javascript
["s'teL", "ekat", "edoCteeL", "tsetnoc"]
```

然后把这个数组用 `join(" ")` 来重新变成 `String`


## 知识点
- 在 `JavaScript` 中 如何 reverse 一个 `String`
- 同样是循环
    ```javascript
    for (var i = 0; i < nums.length; i++) {

    }

    nums.forEach(function(num, index){

    }); 

    nums.map(function(num, index) {

    })
    ```
    这三个有什么区别
