# 对象定义

```javascript
let 对象名 = {对象属性，方法等}
```



## 对象属性

**定义；**

```js
let person = {
            name:"Miku",
            age:16,
            eyeColor:"blue"
     
}
```

**访问属性；**

- 方式一；

  ```js
  console.log("名字是"+person.name);
  ```

  

- 方式二；

  ```js
   console.log("喜欢的颜色是%s",person["eyeColor"]);
  ```



## 对象方法

**定义；**

```js
let person = {
            name:"Miku",
            age:16,
            eyeColor:"blue",
    		// 定义一个showAge方法
            showAge:function(){
                console.log("年龄是"+this.age);
            }
        }
```

**调用方法；**

```js
 person.showAge();
```

