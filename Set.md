# Set

Sets是值的集合，可以按顺序插入，但是Set中的元素只能出现一次。 Undefined 和 Nav都可以被放入到Set中。

## 语法
语法new Set([iterable]);
iterable是一个可迭代的对象。所有值都会传入Set中，如果为空或null，则新的Set为空

```
let set = new Set([1, 2, 3, 4]);
console.log(set); // => Set(4) {1, 2, 3, 4}

set = new Set();
console.log(set); // => Set(0) {}

set = new Set([4, 2, 1, 1]);
console.log(set); // => Set(3) {4, 2, 1}

set = new Set([null, undefined, 1, 0]);
console.log(set); // => Set(4) {null, undefined, 1, 0}
```

## 方法属性

### size 属性为Set长度 
```
console.log(set.size);
```

### add 
方法可以像Set末尾添加一个新的值 set.add(value)  value为要添加的元素

```
set = new Set([1]);
console.log(set); // =>Set(1) {1}
set.add(2);
console.log(set); // =>Set(2) {1, 2}
set.add(1);
console.log(set); // =>Set(2) {1, 2} 不可以添加已有值
set.add('1');
console.log(set); // =>Set(3) {1, 2, "1"}
set.add('aa').add('bb');
console.log(set); // =>Set(5) {1, 2, "1", "aa", "bb"} 可以使用链式调用

```

### clear 
方法用来清空一个Set 返回undefined set.clear()
```
set = new Set([1, 2, 3]);
console.log(set);
set.clear();
console.log(set);// =>Set(0) {}
```

### delete 
方法可以删除Set中的指定的值 set.delete(value) value为指定要删除的值 成功返回true 失败返回false
```
set = new Set([1, 2, 3]);
console.log(set); // =>Set(3) {1, 2, 3}
console.log(set.delete(2)); // =>true
console.log(set); //Set(2) {1, 3}
console.log(set.delete(2));
console.log(set); //Set(2) {1, 3}
```

### entries 
返回一个新的迭代器对象
```
set = new Set([1, 2, 3, 4]);
console.log(set); // =>Set(4) {1, 2, 3, 4}
let iter = set.entries();
console.log(iter); // => SetIterator {1, 2, 3, 4}
```

### forEach 
方法根据Set中元素的顺序，对每个元素执行一次callback set.forEach(callback[, thisArg]) callback为回调函数 thisArg可以当作callback的this来使用callback有3个参数 元素的值， 元素的索引和集合对象.

```
set = new Set(['a', 'b', 'c', 'd']);
console.log(set); // =>Set(4) {"a", "b", "c", "d"}
set.forEach(function(val1, val2, sets){
    console.log(val1, val2, sets);
    console.log(this); // => undefined
});

set.forEach(function(val1, val2, sets){
    console.log(val1, val2, sets);
    console.log(this); // => window
}, window); 
```

### has 
方法用来确认Set中是否存在指定的值 set.has(value) value为指定的值 如果存在返回true，否则返回false
```
set = new Set([1,2,3,4]);
console.log(set); // => Set(4) {1, 2, 3, 4}
console.log(set.has(1)); // => true
console.log(set.has(5)); // => false
```

### values keys 
方法返回一个Iterator对象
```
set = new Set([1,2,3,4]);
console.log(set); // => Set(4) {1, 2, 3, 4}
console.log(set.values()); // => SetIterator {1, 2, 3, 4}
console.log(set.keys()); // => SetIterator {1, 2, 3, 4}
```
    