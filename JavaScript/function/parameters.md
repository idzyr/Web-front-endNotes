# 函数参数



## arguments 对象

JavaScript 函数有个内置的对象 arguments 对象。

argument 对象包含了函数调用的参数数组。

通过这种方式你可以很方便的找到最大的一个参数的值：

```js
x = sumAll(1, 123, 500, 115, 44, 88);
 
function sumAll() {
    var i, sum = 0;
    for (i = 0; i < arguments.length; i++) {
        sum += arguments[i];
    }
    return sum;
}

//结果；871
```

