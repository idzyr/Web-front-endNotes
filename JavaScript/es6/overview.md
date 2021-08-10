# 概览

各大浏览器的最新版本，对 ES6 的支持可以查看[kangax.github.io/es5-compat-table/es6/]()。

访问r[uanyf.github.io/es-checker]()，可以看到您的浏览器支持 ES6 的程度



## Babel 转码器

Babel 是一个广泛使用的 ES6 转码器，可以将 ES6 代码转为 ES5 代码，从
而在现有环境执行。这意味着，你可以用 ES6 的方式编写程序，又不用担心
现有环境是否支持。下面是一个例子。

```js
// 转码前 
input.map(item => item + 1); 
 
// 转码后 
input.map(function (item) { 
  return item + 1; 
});
```

上面的原始代码用了箭头函数，Babel 将其转为普通函数，就能在不支持箭头
函数的 JavaScript 环境执行了。



## Traceur 转码器

Google 公司的Traceur转码器，也可以将 ES6 代码转为 ES5 代码。







