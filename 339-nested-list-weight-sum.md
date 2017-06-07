这里用到了递归的思想

```javascript
var depthSum = function(nestedList) {
    var sum = 0;
    
    function helper(nestedList, level) {
        for (var i = 0; i < nestedList.length; i++) {
            if (nestedList[i].isInteger()) {
                sum += nestedList[i].getInteger() * level;
            } else {
                // if it is a list
                helper(nestedList[i].getList(), level + 1);
            }
        }
    }
    helper(nestedList, 1);
    return sum;
};
```

也可以把 sum 放到 helper 里面

```javascript
var depthSum = function(nestedList) {
    
    function helper(nestedList, level) {
        var sum = 0;
        for (var i = 0; i < nestedList.length; i++) {
            if (nestedList[i].isInteger()) {
                sum += nestedList[i].getInteger() * level;
            } else {
                // if it is a list
                sum += helper(nestedList[i].getList(), level + 1);
            }
        }
        return sum;
    }
    return helper(nestedList, 1);

};
```