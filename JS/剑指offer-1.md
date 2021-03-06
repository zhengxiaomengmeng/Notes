---
title: 剑指Offer-JavaScript版-part1.md
date: 2018-03-21 20:15:40
tags: JS
---

### 指offer实战-JavaScript版

前言：以前刚学JS的时候，一直觉得前端不怎么需要算法，就是单纯的实现业务功能，现在想想那时候的想法多少天真，可以说用幼稚来形容了。作为一个合格的程序猿，怎么可能不搞算法，前端的算法不会太复杂，一般都是一些比较简单的算法，对照剑指offer，将里面的算法重新实战一遍，代码位置在另一个仓库[Offer](https://github.com/Xia-Ao/Offer)

### 1、二维数组中的查找

**题目**：在一个二维数组中，每一行都按照从左到右递增的顺序排序，每一列都按照从上到下递增的顺序排序。请完成一个函数，输入这样的一个二维数组和一个整数，判断数组中是否含有该整数。

**思路**：二维数组是有规律的，按照横纵展开，向右向下递增。选取数组右上角的数字，如果该数字等于要查找的数组，则结束。如果大于要查找的数字，则该列都大于要查找的数字，剔除该列，向左移动一列继续查找；如果小于要查找的数字，则该行都小于要查找的数字，剔除该行，向下移动一行继续查找；直到查找到该数字或者查找到左下角还没有匹配，则返回没有匹配。

**代码**：[github](https://github.com/Xia-Ao/Offer/tree/master/offer)


```js
function find(array, target) {
    let row = array.length - 1;
    for (let i = row, j = 0; i >= 0 && j < array[i].length;) {
        if (target === array[i][j]) {
            return true
        } else if (target > array[i][j]) { //目标大于，则下移一行
            j++;  //向下移动一行
        } else {
            i--;  //向左一动一行
        }
    }
    return false
}
```


---

### 2、替换空格

**题目**：请实现一个函数，将一个字符串中的空格替换成“%20”。例如，当字符串为We Are Happy.则经过替换之后的字符串为We%20Are%20Happy。

**思路**：当然是直接用正则匹配然后使用replace替换就好了。

**代码**：


```js
function replaceSpace(str) {
    let reg = new RegExp(/\s/g);
    return str.replace(reg, '--')
}
```


---

### 3、从尾到头打印链表

**题目**：输入一个链表，从尾到头打印链表每个节点的值。

不懂链表的可以参考《学习JavaScript的数据结构与算法》

**思路**：先将链表每个结点的值存入数组中，然后通过数组的reverse方法，即可从尾到头打印

代码：Github


```js
function printLinkedList(head) {
    let arr = [];
    while (head !== null) {
        arr.push(head);
        head = head.next();
    }
    return arr.reverse();
}
```




---
### 4、重建二叉树

**题目**：输入某二叉树的前序遍历和中序遍历的结果，请重建出该二叉树。假设输入的前序遍历和中序遍历的结果中都不含重复的数字。例如输入前序遍历序列{1,2,4,7,3,5,6,8}和中序遍历序列{4,7,2,1,5,3,8,6}，则重建二叉树并返回。

**思路**：

**代码**：Github


---

### 5、用两个栈来实现一个队列

**题目**：用两个栈来实现一个队列，完成队列的Push和Pop操作。 队列中的元素为int类型

**思路**：栈的操作是后入先出（LIFO），队列的操作是先入先出（FIFO）

**代码**：Github


```js
let arr1 = [], arr2 = [], result = [];

function push(head) {
    arr2.push(head);
    return arr
}

function shift() {
    if (arr1.length) {
        arr1.shift()
    } else if (arr2.length) {
        arr2.shift()
    } else {
        return null
    }
    return arr
}
```



---
### 6、旋转数组的最小数字 

**题目**：把一个数组最开始的若干个元素搬到数组的末尾，我们称之为数组的旋转。 输入一个非递减排序的数组的一个旋转，输出旋转数组的最小元素。 例如数组{3,4,5,1,2}为{1,2,3,4,5}的一个旋转，该数组的最小值为1。 NOTE：给出的所有元素都大于0，若数组大小为0，请返回0。

**思路**：其实剑指Offer中想要表达的是一种寻找数组最小值的二分查找方法，旋转之后原数组分为两个部分，[3,4,5,1,2],前面的部分最小的数肯定大于或等于后面部分最大的数，通过这一点可以节省遍历，典型的二分法。

**代码**：Github


```js
function rotate(arr) {
    return arr.sort(function (a, b) {
        if (a < b)
            return -1;
        else return 1
    })[0];
//        return Math.min.apply(arr, arr);
}
```



---
### 7、斐波那契数列

**题目**：大家都知道斐波那契数列，现在要求输入一个整数n，请你输出斐波那契数列的第n项。`n<=39`

**思路**：传统思路是使用递归，这种方法简单直接，但是会有一个问题，存在严重的效率问题，很多的重复计算，因此，剑指Offer提出一种优化方法，使用内存记录之前的计算结果，从0 ，1 ，2 开始一直到n，计算过的值被记录下来，就不用再计算了。大大的节省了时间。

**代码**：Github


```js
function fibonacci(n) {
        if (n === 0 || n === 1)
            return n;
        else {
            var one = 0;
            var two = 1;
            var result = 0;
            for (var i = 2; i <= n; i++) {
                result = one + two;
                one = two;
                two = result
            }
            return result;
        }

    }
```

---
### 8、跳台阶

**题目**：一只青蛙一次可以跳上1级台阶，也可以跳上2级。求该青蛙跳上一个n级的台阶总共有多少种跳法。

**思路**：其实就是斐波那契函数的应用，如果n=1则只有一种，如果n=2则有两种,如果n=3，则有前两种之和，记一个函数f(n),则跳法为f(n-1)+f(n-2)

**代码**：Github

```js
function fibonacci(n) {
        if (n === 1 || n === 2)
            return n;
        else {
            var one = 0;
            var two = 1;
            var result = 0;
            for (var i = 3; i <= n; i++) {
                result = one + two;
                one = two;
                two = result
            }
            return result;
        }

    }
```

---
### 9、变态跳台阶

**题目**：一只青蛙一次可以跳上1级台阶，也可以跳上2级……它也可以跳上n级。求该青蛙跳上一个n级的台阶总共有多少种跳法。

**思路**：其实就是斐波那契函数的应用，如果n=1则只有一种，如果n=2则有两种,如果n=3，则有前两种之和在加上自己跳n阶的一种，记一个函数f(n),则跳法为f(n-1)+f(n-2)+...+f(1)+1

**代码**：Github
```js
function fibonacci(n) {
    var arr = [1, 2];
    if (n === 1 || n === 2)
        return arr[n - 1];
    else {
        var result = 0;
        for (var i = 3; i <= n; i++) {
            result = 1 + arr.reduce(function (total, currentValue) {
                return total + currentValue;
            });
            arr.push(result);
        }
        return result;
    }

}
```

---
### 10、矩形覆盖

**题目**：我们可以用2*1的小矩形横着或者竖着去覆盖更大的矩形。请问用n个2*1的小矩形无重叠地覆盖一个2*n的大矩形，总共有多少种方法？

**思路**：其实就是斐波那契函数的应用，注意题目中是无重叠，如果n=1则只有一种，n=2时则有2种，
           n=3时，左上角可以横着放也可以竖着放，竖着放的话，右边剩下两列，刚好是f(2)的情况，当横着放的时候，左下角必须横放一个，右边就剩下一列，f(1)，则有f(2)+f(1)种,
           因此推导f(n)= f(n-1)+f(n-2)

**代码**：Github
```js
function rectCover(number) {
    // write code here
    var n = number;
    var arr = [1, 2];
    var result = 0;
    if (n === 1 || n === 2)
        return arr[n - 1];
    else {
        for (var i = 3; i <= n; i++) {
            result = arr[arr.length - 1] + arr[arr.length - 2];
            arr.push(result);
        }
        return result
    }
}
```
---
### 11、二进制中1的个数

**题目**：输入一个整数，输出该数二进制表示中1的个数。其中负数用补码表示。

**思路**：把一个整数减去1 ，再和原整数做 & 运算，就会把原整数最右边的一个1变成0，做多少次这样的操作，就有多少个1

**代码**：Github
```js
function NumberOf1(n) {
    var count = 0;
    while (n) {
        ++count;
        n = (n - 1) & n
    }
    return count
}
```
---
###

**题目**：

**思路**：

**代码**：Github

---
###

**题目**：

**思路**：

**代码**：Github
