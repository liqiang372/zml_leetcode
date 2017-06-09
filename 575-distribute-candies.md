这里我们接触算法中 非常重要的一个概念: __Hash table__, 中文叫哈希表。
为什么要用 Hash table, 用 array 不行吗？

### Array
- 优点: 所有的 element 按照顺序，齐齐整整放在一起
- 缺点: 查找一个元素的时间是 O(N)， 这是什么意思呢？ 
    比如我们有一个 array， [0, 3, 2, 1, 4, 5, 8, 7, 9, ]
    我们如果想知道这个 array 是否包含一个元素 5, 那么我们至少要扫一遍 array 才能知道。
    这个时间是和 array 长度正相关的，所以我们管这个时间叫做 O(N).

    (当然，如果这个数组是排序好的，那么可以用二分查找，binary search, 时间是O(logN))

### Hash table
查找一个元素的时间是O(1), 表示的是无论我存了多少个元素，我找到这个元素的时间是常数.
hash table 是一种 key, value 键值对的表比如

```javascript
// hashtable
{
    "xiaohong": "female",
    "xiaolei": "male",
    "xiaoming": "male",
}
```
而在 javascript 中， Object (对象) 正好符合这个概念，所以我们经常用 Object 来表示一个 hash table

```javascript
var students = {
    "xiaohong": "female",
    "xiaolei": "male",
    "xiaoming": "male",
}
// 这样我们用常量时间取得一个 key 的 value
students["xiaohong"] // female

// or 

students.xiaoming // male
```

### Hash set
你暂时可以把 hash set 当作 hashmap 的一种变种，只不过它不是 key/value pair, 只需要存 key, 并且不能有 duplicate, hashmap 也是不能有 duplicate, 因为后来的key 会把之前相同的key 覆盖掉.
这个你知道就行


好了回到题目本身

我们需要知道到底有多少种不同的 candies, 那么我们可以用 javascript 中的一个 object 当作 hashtable
```javascript
var distributeCandies = function(candies) {
    var kinds = {};
    candies.forEach(function(c) {
        kinds[c] = null; // 这里随便给他赋值，因为value 不重要，我们只看key
    });
    // 然后看一看 kinds 里面有多少个key, 这里用到的 method 是 Object.keys(kinds) 返回一个
    // 装满 keys 的 array
    var numOfKinds = Object.keys(kinds).length;
    // 这里我们用到的是非常常用的 Conditional (ternary) Operator
    // https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Conditional_Operator
    return numOfKinds >= Math.floor(candies.length / 2) ? Math.floor(candies.length / 2) : numOfKinds;
};

```

## 知识点
- 了解了hashtable 是什么玩意，以及用 javascript 中的 object 来表示 hashtable
- 学会了 Ternary operator
    这个其实就是
    ```javascript
    if (condition) {
        return a;
    } else {
        return b;
    }

    // 因为这种操作太常见了，所以就直接
    return condition ? a : b;
    ```



