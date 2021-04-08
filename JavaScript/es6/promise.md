# 异步任务

## Promise异步类

通过 Promise 对象好像并没有看出它怎样 "更加优雅地书写复杂的异步任务"。

**构造函数；**

- `Promise(Start(resolve,reject) )` 起始函数会被异步执行：
  - 参数
    - Start 函数类型
      - 形参
        - `resolve` 函数类型，代表一切正常，此函数被调用后会继续执行Promise正常队列中的下一个任务。
        - `reject `函数类型，出现异常时所调用的，此函数被调用后会执行Promise 的异常序列任务。

```js
 new Promise(function(resolve,reject){
            console.log("任务一");
            resolve();
        })
```





**方法；**

- `then(function)` 添加一个新的任务到Promise对象的正常执行序列。

- `catch(function)`添加一个任务到Promise对象的异常处理序列。
- `finally(function)`  添加一个 Promise 执行的最后一定会执行的序列。



**一个完整的示例；**

- resolve()  中可以放置一个参数用于向下一个 then 传递一个值，

- reject()  参数中一般会传递一个异常给之后的 catch 函数用于处理异常。

  > **注意；**
  >
  > - resolve 和 reject 的作用域只有起始函数，不包括 then 以及其他序列；
  > - resolve 和 reject **并不能够使起始函数停止运行**，别忘了 return。

```js
// 瀑布流形式
new Promise(function(resolve,reject){
            console.log("起始函数");
            resolve("这里是初始函数");  //一切正常让Promise正常队列中的任务开始执行。
        }).then(function(value){
            console.log("正常任务队列执行提示");
            console.log("初始化函数传递的值\t%s",value);
            throw "任务处理异常";
             //如果出现异常就调用catch队列。
            /* reject()【reject()只在初始函数起作用】或  throw 都会去执行catch定义的异常处理函数*/
        }).catch(function(err){
            console.log("异常任务队列执行提示")
            console.error("异常信息\t%s",err);
        }).finally(function(){
            console.log("最终一定会执行的方法");
        });
```



### Promise 函数

上述的程序看上去比函数瀑布还要长，所以我们可以将它的核心部分写成一个 Promise 函数：

```js
     /*
        输入要执行的内容
       */ 
       function print(message){
            return new Promise(function(resolve,reject){
                console.log(message);
                resolve(); //执行正常队列方法。
            })
       };

       print("初始函数").then(function(){
         return print("正常队列");
         // 为了让起始函数停止运行这里要return
       }).then(()=>{
           print("正常队列2");
       });

```

执行结果；

```
初始函数
text-html.html:17 正常队列
text-html.html:17 正常队列2
```





### 回答常见的问题（FAQ）

**Q: then、catch 和 finally 序列能否顺序颠倒？**

A: 可以，效果完全一样。但不建议这样做，最好按 then-catch-finally 的顺序编写程序。

**Q: 除了 then 块以外，其它两种块能否多次使用？**

A: 可以，finally 与 then 一样会按顺序执行，但是 catch 块只会执行第一个，除非 catch 块里有异常。所以最好只安排一个 catch 和 finally 块。

**Q: then 块如何中断？**

A: then 块默认会向下顺序执行，return 是不能中断的，可以通过 throw 来跳转至 catch 实现中断。

**Q: 什么时候适合用 Promise 而不是传统回调函数？**

A: 当需要多次顺序执行异步操作的时候，例如，如果想通过异步方法先后检测用户名和密码，需要先异步检测用户名，然后再异步检测密码的情况下就很适合 Promise。

**Q: Promise 是一种将异步转换为同步的方法吗？**

A: 完全不是。Promise 只不过是一种更良好的编程风格。

**Q: 什么时候我们需要再写一个 then 而不是在当前的 then 接着编程？**

A: 当你又需要调用一个异步任务的时候。



## 异步函数Async

异步函数（async function）是 ECMAScript 2017 (ECMA-262) 标准的规范，几乎被所有浏览器所支持，除了 Internet Explorer。

**示例；**

在 Promise 中我们编写过一个 Promise 函数：

```js
 // 创建一个异步函数
		/*
			延迟输出一段文字
		*/
        funciton delayPrint(delay,message){
            return new Promise(function(resolve,reject){
                setTimeout(() => {
                    console.log(message);
                    resolve();  //一切正常执行正常队列任务。
                }, delay);
            });
        }

```

然后用不同的时间间隔输出了三行文本：

```js
  delayPrint(1000,"一【起始】").then(function(){
            return delayPrint(4000,"第二");
        }).then(function(){
            delayPrint(3000,"第三");
        });
```

我们可以对上面这段代码进行优化。

```js
     // 定义一个异步函数
        async function asyncFunc(){
            // await 异步函数会在这个 Promise 运行中暂停，直到其运行结束再继续运行。
            await delayPrint(1000,"起始函数一");
            await delayPrint(4000,"第二");
            await delayPrint(3000,"第三");
        }

        asyncFunc();
```

这样写异步函数 async function 中可以使用 await 指令，**await 指令后必须跟着一个 Promise**，异步函数会在这个 Promise 运行中暂停，直到其运行结束再继续运行。

异步函数实际上原理与 Promise 原生 API 的机制是一模一样的，只不过更便于程序员阅读。

**异常处理；**

处理异常的机制将用 try-catch 块实现：

```js
 // 异步函数
        async function asyncFunc(){
            try{
                await new Promise(function(resolve,reject){
                    throw "Some error"; // 或者 reject("Some error")
                })

            }catch (err){
                console.log(err);
                // 会输出 Some error
            }
        };

        asyncFunc();

```



**正常处理；**

如果 Promise 有一个正常的返回值，await 语句也会返回它：

```js
    // 异步函数
        async function asyncFunc() {
            let value =  await new Promise(function (resolve, reject) {
                resolve("正常执行结果");
            });
            console.log(value);
        };

        asyncFunc();
```

