---
title: Array操作方法.md
date: 2017-10-05 20:05:40
tags: JS
---

## Array对象

[官方API文档](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Array/length)

### 数组属性

[`constructor`](http://www.runoob.com/jsref/jsref-constructor-array.html) 返回创建数组对象的原型函数。

[`length`](http://www.runoob.com/jsref/jsref-length-array.html)` `设置或返回数组元素的个数。

[`prototype`](http://www.runoob.com/jsref/jsref-prototype-array.html)` `允许你向数组对象添加属性或方法。

### Array 对象属性

改变自身值的方法一共有9个，分别为pop、push、reverse、shift、sort、splice、unshift，以及两个ES6新增的方法copyWithin 和 fill

不会改变自身的方法一共有9个，分别为concat、join、slice、toString、toLocateString、indexOf、lastIndexOf、未标准的toSource以及ES7新增的方法includes。

##### 添加修改删除等操作

**浅复制** 是指当对象的被复制时，只是复制了对象的引用，指向的依然是同一个对象  
[`concat()`](http://www.runoob.com/jsref/jsref-concat-array.html) 连接两个或更多的数组，组成一个新的数组并返回。

[`copyWithin( )`](http://www.runoob.com/jsref/jsref-copywithin.html)` `从数组的指定位置拷贝元素到数组的另一个指定位置中。

[`slice( start, end )`](#)将数组中一部分元素**浅复制**存入新的数组对象，并且返回这个数组对象。

[`fill()`](#)使用一个固定值来填充数组。

[`join()`](#)` `将数组中的所有元素连接成一个字符串，并返回这个字符串。

[`push()`](http://www.runoob.com/jsref/jsref-push.html) 向数组的末尾添加一个或更多元素，并返回新的长度，**改变了原数组**。

[`unshift()`](http://www.runoob.com/jsref/jsref-unshift.html)` `向数组的开头添加一个或更多元素，并返回新的长度。**改变了原数组**

[`shift()`](http://www.runoob.com/jsref/jsref-shift.html) 删除数组第一个元素，并返回数组的第一个元素，会**改变原数组**。

[`splice()`](http://www.runoob.com/jsref/jsref-splice.html) 从数组中添加或删除元素。会**改变原数组**

[`pop()`](#)删除数组的最后一个元素并返回删除后的元素，**改变了原数组**。

##### 替换数组

`copyWithin(ES6)`用于数组内元素之间的替换，即替换元素和被替换元素均是数组内的元素。**改变了原数组**  
 `arr.copyWithin(target, start[, end = this.length])`

`fill(ES6)`它同样用于数组元素替换，但与copyWithin略有不同，它主要用于将数组指定区间内的元素替换为某个值。**改变了原数组**

##### 查询数组

[`every()`](http://www.runoob.com/jsref/jsref-every.html) 检测数值元素的每个元素是否都符合条件。返回Boolean值。

[`filter()`](http://www.runoob.com/jsref/jsref-filter.html) 检测数值元素，并返回符合条件所有元素的数组。

[`find()`](http://www.runoob.com/jsref/jsref-find.html) 返回符合传入测试（函数）条件的数组元素。当数组中的元素在测试条件时返回 true 时, find\(\) 返回符合条件的元素，之后的值不会再调用执行函数。

[`some()`](#)` `检测数组元素中是否有元素符合指定条件。返回布尔值

[`findIndex()`](http://www.runoob.com/jsref/jsref-findindex.html) 返回符合传入测试（函数）条件的数组元素索引。同样，检测到第一个的时候，然后返回，不在执行后面的。

[`indexOf(item,start)`](#)搜索数组中的元素，并返回它所在的位置，如果没有，返回-1，但是不区分NaN。

[`lastIndexOf()`](#)返回一个指定的字符串值最后出现的位置，在一个字符串中的指定位置从后向前搜索。

**计算转换**

[`reduce()`](http://www.runoob.com/jsref/jsref-reduce.html)` `将数组元素计算为一个值（从左到右）。如遇到字符串，执行字符串拼接。

[`reduceRight()`](http://www.runoob.com/jsref/jsref-reduceright.html)` `将数组元素计算为一个值（从右到左）。

[`toString()`](http://www.runoob.com/jsref/jsref-tostring-array.html)` `把数组转换为字符串，并返回结果。

[`toLocaleString()`](https://www.gitbook.com/book/xia-ao/notes/edit#)把数组使用头LocaleString方法转换为字符串，并返回结果。

[`valueOf()`](http://www.runoob.com/jsref/jsref-valueof-array.html)` `返回数组对象的原始值。

##### 排序

[`reverse()`](#)反转数组的元素顺序，该方法返回对数组的引用，会**改变原数组**。

[`sort( )`](http://www.runoob.com/jsref/jsref-sort.html)```对数组的元素进行排序。使用数字排序，你必须通过一个函数作为参数来调用。``

语法：`arr.sort([comparefn])`comparefn是可选的，如果省略，数组元素将按照各自转换为字符串的Unicode\(万国码\)位点顺序排序。

##### 遍历方法12个

1、**forEach**

[`forEach(function(currentValue,index,arr),thisArg)`](http://www.runoob.com/jsref/jsref-foreach.html)  数组每个元素都执行一次回调函数。

* value 当前正在被处理的元素的值，index 当前元素的数组索引，array 数组本身
* thisArg 可选，用来当做fn函数内的this对象。

2、**every**

使用传入的函数测试所有元素，只要其中有一个函数返回值为 false，那么该方法的结果为 false；如果全部返回 true，那么该方法的结果才为 true。

3、**some**

some 测试数组元素时，只要有一个函数返回值为 true，则该方法返回 true，若全部返回 false，则该方法返回 false。

4、**filter**

filter() 方法使用传入的函数测试所有元素，并**返回所有通过测试的元素组成的新数组**。它就好比一个过滤器，筛掉不符合条件的元素。

语法：`arr.filter(fn, thisArg)`

5、**map**

[`map()`](#)通过指定函数处理数组的每个元素，并返回处理后的**新数组**。

语法：`arr.map(fn, thisArg)`

6、**reduce**

reduce() 方法接收一个方法作为累加器，数组中的每个值(从左至右) 开始合并，最终为一个值。

语法：`arr.reduce(fn, initialValue)`fn 表示在数组每一项上执行的函数，接受四个参数：
* `previousValue` 上一次调用回调返回的值，或者是提供的初始值
* `value` 数组中当前被处理元素的值
* `index` 当前元素在数组中的索引
* `array` 数组自身

`initialValue` 指定第一次调用 fn 的第一个参数。
当 fn 第一次执行时：

* 如果 initialValue 在调用 reduce 时被提供，那么第一个 previousValue 将等于 initialValue，此时 item 等于数组中的第一个值；
* 如果 initialValue 未被提供，那么 previousVaule 等于数组中的第一个值，item 等于数组中的第二个值。此时如果数组为空，那么将抛出 TypeError。
* 如果数组仅有一个元素，并且没有提供 initialValue，或提供了 initialValue 但数组为空，那么fn不会被执行，数组的唯一值将被返回。

7、**reduceRight**

数组中的每个值（从右至左）开始合并，最终为一个值

8、**entries(ES6)**

返回一个数组迭代器对象，该对象包含数组中每个索引的键值对。

9、**find&findIndex(ES6)**

find() 方法基于ECMAScript 2015（ES6）规范，返回数组中第一个满足条件的元素（如果有的话）， 如果没有，则返回undefined。

findIndex() 方法也基于ECMAScript 2015（ES6）规范，它返回数组中第一个满足条件的元素的索引（如果有的话）否则返回-1。

语法：`arr.find(fn, thisArg)`，`arr.findIndex(fn, thisArg)`

10、**keys(ES6)**

返回一个数组索引的迭代器。

11、**values(ES6)**

返回一个数组迭代器对象，该对象包含数组中每个索引的值。

12、**Symbol.iterator(ES6)**

###小结：
1. Array.prototype本身就是一个数组，并且它的长度为0。
2. 所有插入元素的方法, 比如 push、unshift，一律返回数组新的长度；
3. 所有删除元素的方法，比如 pop、shift、splice 一律返回删除的元素，或者返回删除的多个元素组成的数组；
4. 部分遍历方法，比如 forEach、every、some、filter、map、find、findIndex，它们都包含function(value,index,array){} 和 thisArg 这样两个形参。
5. Array.prototype 的所有方法均具有鸭式辨型这种神奇的特性。它们不止可以用来处理数组对象，还可以处理类数组对象。




#### Array.of （构造函数）

`Array.of`用于将参数依次转化为数组中的一项，然后返回这个新数组，而不管这个参数是数字还是其它，它基本上与Array构造器功能一致，唯一的区别就在单个数字参数的处理上.

```js
Array.of(8.0); // [8]
Array(8.0); // [undefined × 8]
```

#### Array.from （构造函数）


只要一个对象有迭代器，Array.from就能把它变成一个数组（当然，是返回新的数组，不改变原对象）。  
语法：`Array.from(arrayLike[, processingFn[, thisArg]])`  
Array.from拥有3个形参，第一个为类似数组的对象，必选。第二个为加工函数，新生成的数组会经过该函数的加工再返回。第三个为this作用域，表示加工函数执行时this的值。后两个参数都是可选的。  
**注意**:一旦使用加工函数，必须明确指定返回值，否则将隐式返回undefined，最终生成的数组也会变成一个只包含若干个undefined元素的空数组。

#### Array.isArray\(\)

判定一个对象是数组的五种方法，前四种都不保险，如果将某个对象的对象的`__proto__`属性为`Array.prototype`，便导致了该对象继承了Array对象，前四种方法就会判定为true.

```js
var a = [];
// 1.基于instanceof
a instanceof Array;
// 2.基于constructor
a.constructor === Array;
// 3.基于Object.prototype.isPrototypeOf
Array.prototype.isPrototypeOf(a);
// 4.基于getPrototypeOf
Object.getPrototypeOf(a) === Array.prototype;
// 5.基于Object.prototype.toString
Object.prototype.toString.apply(a) === '[object Array]';
```

所以严格意义上判定一个对象是否是数组，推荐使用第五种方法，再说到`Array.isArray()`，实际上就是推荐使用的第五种toString方法。

典型问题：

### 数组去重

实际上有很多种方法，其实都大同小异，只要熟悉数组操作的API方法，你就可以写出很多种，但是本质都是一样的。优先推荐使用ES6中Set属性不重复的特征去重。

1. 两层for循环，一层遍历数组，一层循环对比，对相同的元素从数组中删除，或者新建一个res数组，将不同的元素push到新数组中，返回新数组。效率低，当数组比较长时不合适。

   ```js
   let arr = [0, 3, 4, 3, 4, 6, 2, 4];
   for (let i = 0; i < arr.length; i++) {
       for (let j = i + 1; j < arr.length; j++) {
           if (arr[i] === arr[j]) {
               arr.splice(j, 1);
               j--;  //要将值重新向前递进
               console.log(arr)
           }
       }
   }

   // [0, 2, 3, 4, 6]
   ```
时间复杂度：O(n^2)

  
2. 使用IndexOf或者includes检查是否重复，其实跟第一种方法比较就是将第二层循环使用了IndexOf这种有遍历接口的API操作，这个操作的本质是不是跟第一种方法一样使用循环遍历，这个就是要看源码了。

   ```js
   let arr = [0, 3, 4, 3, 4, 6, 2, 4];
   let res = [];
   for (let i = 0, len = arr.length; i < len; i++) {
      let current= arr[i];
      if(res.indexOf(current)===-1){
          res.push(current)
      }

      //或者使用includes
      if(!res.includes(current)){
          res.push(current)
      }

   }

   // [0, 2, 3, 4, 6]
   ```
  时间复杂度：


   

3. 先用`sort`排序，或者已知数组是有序的，后比较相邻两个是否相等。

   ```js
   let arr = [0, 3, 4, 3, 4, 6, 2, 4];
   arr.sort();
   let temp;
   let res=[]
   console.log(temp)
   for (let i = 0, len = arr.length; i < len; i++) {
       if (!i || temp !== arr[i]) {
           res.push(arr[i])
       }
       temp=arr[i]
   }
   console.log(res);

   // [0, 2, 3, 4, 6]
   ```
时间复杂度：有序数组O(n)



4. ES6中Set属性

   ```js
   // 去除数组的重复成员
   [...new Set(array)]

   let arr = [0, 3, 4, 3, 4, 6, 2, 4];
   let res=[...new Set(arr)]

   // [0, 2, 3, 4, 6]
   ```

   **注意**：  
   1、以上去重只对数组中同一种数据类型进行比较去重，如果有不同的数据类型，要区别对待  
   2、向 Set 加入值的时候，不会发生类型转换，Set 内部判断两个值是否不同，使用的算法叫做“Same-value-zero equality”，它类似于精确相等运算符（===），主要的区别是NaN等于自身，在 Set 内部，它认为两个NaN是相等。  
   3、indexOf内部使用的精确相等运算符（===），`NaN===NaN 的结果是 false`  
   4、includes内部也是使用的类似精确相等运算符（===），`NaN===NaN 的结果是 true`

### 1、单数组操作

### 2、数组遍历方法

### 3、多数组操作
