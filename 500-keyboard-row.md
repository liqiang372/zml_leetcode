由于设定的每一行没有啥规律，所以只能把三行的字母都列出来，然后看一看 word 是否属于其中一行的 subset.
```javascript
var findWords = function(words) {
    var row1 = 'qwertyuiop';
    var row2 = 'asdfghjkl';
    var row3 = 'zxcvbnm';
    
    var res = [];
    words.forEach(function(w) {
        if (isSubset(row1, w) || isSubset(row2, w) || isSubset(row3, w)) {
            res.push(w);
        }
    });
    return res;
};

// 这是我们的 helper function.
var isSubset = function (row, word) {
    for (var i = 0; i < word.length; i++) {
        // word 是一个 string, 知道 index后，查看其中的 character 的方法是 word.charAt(index)
        var c = word.charAt(i).toLowerCase();
        // 看看 string 是否包含一个 character, 和 array.indexOf 查看是否有元素一样
        // 如果包含就返回所在的 index, 如果不包含，就返回 -1.
        if (row.indexOf(c) === -1) return false; 
    }
    return true;
}
```

## 知识点
- `String.charAt(Index)` 来找 index 位置的 Character
- `String.indexOf(Character)` 看 String 是否包含某一个 Character