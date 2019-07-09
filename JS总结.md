# Javascript总结

> 1. 基于对象和事件驱动是什么意思；
> 2. js可以做什么；



> 客户端脚本语言，用来实现页面中的交互效果，静态网页；

## 组成 

### ECMA基础语法

#### 变量

- var(变量泄漏)、
- let、const；

#### 数据类型

- 初始类型: null,undefined,Number,String,Boolean; 
- 引用类型: Object(function属于object但是类型是function)；

#### 运算符

- **只有关系运算符的结果为布尔值**

- 算术、关系、逻辑、赋值、一元、三元、特殊 ；

#### 控制流程

- 顺序结构、
- 分支结构 (break/continue终止循环；return终止函数) 、
- 循环结构；

#### 数组

- 可以进行越界访问(数组长度为3但是要访问第9位，即为越界访问)

- 下标范围：0 ~ arr.length-1

- 数组方法

- **[ES6]  解构赋值** ：模式匹配，解构赋值，赋值不成功显示undefined，等号右边必须是数组否则报错；

  ```js
  // 解构赋值的默认值
  let [x=1] = [ ]; // 赋值空数组
  console.log(x)  // 结果为默认值1
  ```

  

- **[ES6]  扩展运算符** ："..."

  - 用于数组合并

    ```js
    let arr1 = [1,2,3];
    let arr2 = ['a','b','c'];
    console.log([...arr1,...arr2]);
    ```

#### 函数

> 对特定代码块的封装，可以用于重复使用

##### 函数	

###### 创建

- 通过function定义一个函数 
- 通过字面量的方式创建
- 通过实例化 Function( )

###### 调用

- 以 fn( ) 函数名加括号的方式来调用 / 以变量名加括号

  ```js
  // 函数名加括号
  function fn1(){
      console.log(1)
  }
  fn1();
  // 变量名加括号
  let fn2 = function(){
      console.log(1)
  }
  fn2();
  ```

  

- 自调用

  ```js
  (function fn(){
      console.log(1)
  })()
  ```

- 事件后调用（在行内事件后调用函数）

  ```html
  <div onclick="fn()"> click me </div>
  ```

###### 参数

> 使函数变得更灵活，可以重复使用

- 形参：定义函数时，括号内的变量为形参(局部作用域，只能在函数内部访问到)；
- 实参：调用函数时，括号内的值为实参( )；

###### 参数个数

- 形参个数 == 实参个数：
  - 一 一对应，从左往右传入；
- 形参个数 > 实参个数：
  - 多余的形参的值为undefined；
- 形参个数 < 实参个数：
  - 多余的实参可以在 arguments 或 rest 中找到；
    - arguments对象：函数创建时就会生成arguments对象，接收***全部***实参，类型为Object；
    - [ES6] rest ***剩余*** 实参：接收多余的实参，类型为Array，可以进行数组遍历；



###### 参数默认值

- 通过三元表达式给参数写默认值；

  ```js
  // 以下设置默认值方式都基于此函数
  function fn(num){
      num = num == undefined ? 1 : num	// 通过三元表达式设置默认值
      console.log(num)	// 输出值是什么？
  }
  ```

- 通过 if / else 分支结构给参数写默认值；

  ```js
  if(num == undefined){  // 判断num是否等于undefined，即为没有值；
      num = 1			  // 如果if判断为真，则默认输出1 
  }else{
      num = num		  // 如果if判断为假，则输出num本身，即为有值
  }
  ```

- 通过逻辑或 " || " 给参数写默认值；

  ```js
  num = num || 1  //判断num是否为真，为真则返回本身,为假则返回预设值"1"
  // 返回第一个真值,返回最后一个假值
  ```

- [ES6] 通过直接赋值给参数写默认值；

  ```js
  function fn(num = 1){	// 在 ES6 中允许以赋值的形式写形参的默认值
      console.log(num)
  }
  ```

  

###### 返回值

- 如果函数和没有返回值，返回undefined；
- 函数的返回值用return来实现；
- 一个函数可以有多个返回值，但是只执行一个；
- return能够终止函数；
- return可以返回任意数据类型；

###### 回调函数

> 把一个函数的指针当作另一个函数的参数；

###### [ES6] rest剩余参数

###### [ES6] name属性

> 返回函数的函数名；

###### [ES6] 箭头函数

- this ：this 指向不会改变

##### 作用域

> 变量作用的范围

###### 作用域的概念 

###### 作用域分类

- 全局作用域

  - 用 var/let 在全局声明的变量；
  - 变量不用var/let声明，直接赋值的变量也拥有全局作用域；

- 局部作用域

  - 形参拥有局部作用域；

  - 用 var/let 关键字在函数内部声明变量；

- 块级作用域

  - { }  大括号即为块级作用域；

###### 作用域链

> 在为变量赋值时遵循的一条规则，只能从内部访问外部的值；

###### 闭包

> 目的：为了解决函数外部不能访问函数内部变量的问题；
>
> 概念：函数内部的函数，操作并且返回变量；

##### 内置顶层函数

> 作用：进行数据类型转换(隐式数据类型转换、强制数据类型转换)；

- Number( )：将任意数据类型转换为数字类型；
- isNaN( )：判断任意数据类型是否可以转为数字类型；
- Boolean( )：将任意数据类型转换为布尔类型；
- parseInt( )：将字符串转换为整型；
- parseFloat( )：将字符串转换为浮点型；
- eval( )：将传入的字符串当作JS代码来执行

#### 对象

##### 创建对象：

- 构造函数

```js
function Float(){
    this.speed=20;
    this.float=function(){
        
    }
}
// 实例化
let float1=new Float();
float1.speed;  // 属性
float1.float();  //方法
```



- json格式

```js
let obj={
    speed:20,
    float:function(){
        
    }
}
obj.speed;  // 属性
obj.float();  //方法
```



- 类 es6

```js
class Float{
    // 构造函数
	constructor(){
		this.speed=20;
    }
    // 原型对象
    float(){
        
    }
}
// 实例化
let float1=new Float();
float1.speed;
float1.float();
```



##### 增删改属性、方法

- 增：`float1.speedX=20`
- 删:`delete float.speed`

##### constructor：指向构造函数

##### `__proto__`:指向原型对象，prototype

##### instanceof:判断对象的构造函数，返回true与false



##### 原型对象prototype

> 是构造函数的属性，用来存放公共的属性和方法，节省内存。



##### 继承:

> 原型对象prototype，call，apply

##### 原型链:

> 对象继承属性与方法时遵循的一条规则，`__proto__`与prototype组成。

```js
// 对象 属性 __proto__
    // 构造函数 属性 prototype
    function Person() {
        this.name = "zs"
    }
    function Student() {
        this.name = "ls"
    }
    Student.prototype = new Person();
    let ww = new Student();
    console.log(ww.name);
    console.log(ww.__proto__ == Student.prototype)    // true
    console.log(Student.prototype.__proto__ == Person.prototype);   // true
    console.log(Person.prototype.__proto__ == Object.prototype);    // true
    console.log(Object.prototype.__proto__);   //null
```



#### BOM

# DOM

#### 获取元素的方法：（5）

#### 操作内容：innerHTML  innerText

#### 操作样式：

**设置样式**

- 添加行内样式：`obj.style.attr=value;`
- 操作类名：

```js
obj.classList.add("box");
obj.classList.remove("box");
obj.classList.toggle("box");   // 切换类
```

className:表示所有的类名

- 操作id:

**获取样式**
获取元素的样式：`window.getComputedStyle(ele,null).attr;`

#### 操作属性

###### 标准属性

获取：`obj.attr`

设置：`obj.attr=value`

###### 非标准属性

设置：`obj.setAttribute(name,value)`

获取：`obj.getAttribute(name)`

### 元素的尺寸与位置

- offsetWidth:元素的真实宽度
- offsetHeight:元素的真实高度
- offsetTop:获取具有定位属性的父元素垂直方向的距离
- offsetLeft:获取具有定位属性的父元素水平方向的距离
- scrollTop：获取有滚动体的元素滚动时垂直方向的距离

```js
window.onscroll=function(){
    document.
}
```



- scrollLeft:获取有滚动体的元素滚动时水平方向的距离

### 节点

### 事件

### 事件对象

### 事件流

### 事件委派

### 本地存储



