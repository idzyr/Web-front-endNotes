# Prototype【原型】

所有的 JavaScript 对象都会从一个 prototype（原型对象）中继承属性和方法。

一个没有实例化并且已经存在构造器的对象是不能直接添加新属性

```js
 Person.nationality = "USA";
```



**示例；**


```js
  function Person(naem,age,gender){
            this.naem = naem;
            this.age = age;
            this.gender = gender;
        };
        Person.nationality = "USA";
        var mPerson = new Person("张三","18","男");
        console.log("姓名%s 年龄%s 性别%s 国际%s",mPerson.naem,mPerson.age,mPerson.gender,mPerson.nationality); 
	// 输出结果；姓名张三 年龄18 性别男 国际undefined

```



## 继承

所有的 JavaScript 对象都会从一个 prototype（原型对象）中继承属性和方法如：

- `Date` 对象从 `Date.prototype` 继承。
- `Array` 对象从 `Array.prototype` 继承。
- `Person` 对象从 `Person.prototype` 继承。

所有 JavaScript 中的对象都是位于**原型链顶端**的 Object 的实例。

JavaScript 对象有一个指向一个原型对象的链。当试图访问一个对象的属性时，它**不仅**仅在该对象上搜寻，还会搜寻该对象的原型，以及该对象的原型的原型，依次层层向上搜索，直到找到一个名字匹配的属性或到达原型链的末尾。

`Date` 对象, `Array` 对象, 以及 `Person` 对象从 `Object.prototype` 继承。



## 添加属性和方法

- 有的时候我们想要在所有已经存在的对象添加新的属性或方法。

- 另外，有时候我们想要在对象的构造函数中添加属性或方法。

这时我们可以用到原型的特点来添加这些属性和方法，可以使用 `Object.prototype` 属性就可以给对象的构造函数添加新的属性。

格式：**构造函数名.prototype.新属性或者新方法**

```js
Person.prototype.nationality = "USA";
```



**示例；**

```js
function Person(naem,age,gender){
            this.naem = naem;
            this.age = age;
            this.gender = gender;
        };
        Person.prototype.nationality = "USA";
        var mPerson = new Person("张三","18","男");
        console.log("姓名%s 年龄%s 性别%s 国际%s",mPerson.naem,mPerson.age,mPerson.gender,mPerson.nationality); 
		// 输出结果；姓名张三 年龄18 性别男 国际USA

```

添加新的方法

**示例；**

```js
 function Person(naem,age,gender){
            this.naem = naem;
            this.age = age;
            this.gender = gender;

        };
        Person.prototype.changeName = function (newName) {
            this.naem = newName;
        }
        var mPerson = new Person("张三","18","男");
        console.log("姓名%s 年龄%s 性别%s",mPerson.naem,mPerson.age,mPerson.gender,mPerson); 
		// 输出结果；姓名张三 年龄18 性别男 Person {naem: "张三", age: "18", gender: "男"}
        mPerson.changeName("李四");
        console.log("姓名%s 年龄%s 性别%s",mPerson.naem,mPerson.age,mPerson.gender,mPerson); 
		//执行结果；姓名李四 年龄18 性别男 Person {naem: "李四", age: "18", gender: "男"}
```





## 网友总结；

### prototype使用场景

通常使用构造器（函数体）定义属性，使用原型对象（prototype）定义方法。

如此，构造器只包含属性定义，而方法则分装在不同的代码块，使代码更具可读性：

```js
// 构造器内定义属性
function Fun(a, b) {
  this.a = a;
  this.b = b;
}

// 原型属性定义方法
Fun.prototype.c = function() {
  return this.a + this.b;
}

// etc...
// 注意，千万不要使用字面量方式来定义属性和方法，否则原有属性和方法会被重写：

function Fn() {};

// 定义属性
Fn.prototype.a = 1;
Fn.prototype.b = 2;

// 字面量定义方法，原型被重写，原有属性和方法被更新
Fn.prototype = {
  c : function() {
    return this.a + this.b;
  }
}

var foo = new Fn();
foo.c();  // NaN
foo.a;  // undefined
foo.b;  // undefined
```









