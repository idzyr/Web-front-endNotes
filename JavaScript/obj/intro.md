# JavaScript对象

## 创建对象

### 使用Object

在 JavaScript 中，几乎所有的对象都是 Object 类型的实例，它们都会从 Object.prototype 继承属性和方法。

Object 构造函数创建一个对象包装器。

Object 构造函数，会根据给定的参数创建对象，具体有以下情况：

- 如果给定值是 null 或 undefined，将会创建并返回一个空对象。
- 如果传进去的是一个基本类型的值，则会构造其包装类型的对象。
- 如果传进去的是引用类型的值，仍然会返回这个值，经他们复制的变量保有和源对象相同的引用地址。
- 当以非构造函数形式被调用时，Object 的行为等同于 new Object()。

**语法格式：**

```js
// 以构造函数形式来调用
new Object([value])
```

value 可以是任何值。

以下实例使用 Object 生成布尔对象：

```js
// 等价于 o = new Boolean(true);
var o = new Object(true);
```

**实例;**

这个例子创建了对象的一个新实例，并向其添加了四个属性：

```js
person=new Object();	//构建一个空对象，分别设置四个属性
person.firstname="John";
person.lastname="Doe";
person.age=50;
person.eyecolor="blue";
```



### 使用{}

```js
let 对象名 = {对象属性，方法等}
```

#### 对象属性

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



#### 对象方法

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

### 对象构造器

```js
  function person(naem,age,gender){
            this.naem = naem;
            this.age = age;
            this.gender = gender;

        };
```

**创建对象实例；**

```js
 var mPerson = new person("张三","18","男");
 console.log("姓名%s 年龄%s 性别%s",mPerson.naem,mPerson.age,mPerson.gender);   
```



## 为已有对象添加新属性

可以通过为对象赋值，向已有对象添加新属性：

假设 person 对象已存在 - 您可以为其添加这些新属性如 `eyecolor`：

```js
// 对象.新属性名 = 值;
person.eyecolor = "blue";

```

## 为对象添加方法

方法只不过是附加在对象上的函数。

在构造器函数内部定义对象的方法：

```js
 function person(naem,age,gender){
            this.naem = naem;
            this.age = age;
            this.gender = gender;
            this.changeName = changeName;   // 添加一个修改名称的方法器值类型为function
            function changeName(newName) {
                this.naem = newName;
            };

        };
        var mPerson = new person("张三","18","男");
        console.log("姓名%s 年龄%s 性别%s",mPerson.naem,mPerson.age,mPerson.gender); 
        // 输出结果；姓名张三 年龄18 性别男
        mPerson.changeName("李四"); 
        console.log("姓名%s 年龄%s 性别%s",mPerson.naem,mPerson.age,mPerson.gender); 
        // 输出结果；姓名李四 年龄18 性别男
```



## JavaScript 类

JavaScript 是面向对象的语言，但 JavaScript 不使用类。

在 JavaScript 中，**不会创建类**，也不会通过类来创建对象（就像在其他面向对象的语言中那样）。

JavaScript 基于 prototype，而不是基于类的。



## JavaScript for...in 循环

JavaScript for...in 语句循环遍历对象的属性。

**语法**

```
for (variable in object)
{
    执行的代码……
}
```

> **注意：** for...in 循环中的代码块将针对每个属性执行一次。

**实例**

循环遍历对象的属性：

```js
var mPerson = new person("张三","18","男");
 
for (x in person)
{
    txt=txt + person[x];
}
```



>  **new 和不 new的区别：**

-  如果 new 了函数内的 this 会指向当前这个 person 并且就算函数内部不 return 也会返回一个对象。
-  如果不 new 的话函数内的 this 指向的是 window。
