# 数组操作
#### 合并连个数组
通常我们想将两个数组合并成一个时，我们用concat方法：
```js
var aArr = [1, 2, 3, 4, 5];
var bArr = [6, 7, 8 ,9];

aArr.concat(bArr); 
console.log(aArr); // [1, 2, 3, 4, 5, 6, 7, 8 ,9];
```
也可以使用：
```js
var aArr = [1, 2, 3, 4, 5];
var bArr = [6, 7, 8 ,9];

Array.prototype.push.apply(aArr, bArr);
console.log(aArr); // [1, 2, 3, 4, 5, 6, 7, 8 ,9];
```

