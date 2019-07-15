# JavaScript

##### JS的作用

1. 嵌入动态文本于网页中
2. 对浏览器事件做出响应    （用户的动作，行为   比如：点击、触摸、滑动）
3. 读写html元素
4. 在数据提交到服务器之前验证服务器     （注册、登录）
5. 控制cookie，包括创建和修改
6. 基于Node.js技术进行服务器端编程

```js
浏览器：js(静态页面，添加了动效）  vue.js 微信小程序    
服务器：php（动态页面）, node.js开发平台（js)  
数据库 mysql mongdb（json) 
```

##### JS语法特点

> 基于对象和事件驱动的解释性松散型语言，它是单线程/异步

> 客户端脚本语言，用来实现页面中的交互效果，静态网页。

详解：JavaScript一种直译式脚本语言，是一种动态类型、弱类型、基于原型的语言，内置支持类型。它的解释器被称为JavaScript引擎，为浏览器的一部分，广泛应用于客户端的脚本语言，用来给HTML网页增加动态功能。

1.  弱类型：所谓弱类型语言，只表明该语言在表达式运算中不强制校验运算元的数据类型。
2. 解释型：（即时编译型）
3. 基于对象：JS中所有数据根源上都是对象
4. 事件驱动
5. 单线程/异步：（callback）

##### JS的组成部分

1. ECMAScript：是JavaScript基础规范，定义了JavaScript基础语法。

   > 变量（var、let、const）
   >
   > 数据类型：初始数据类型（undefined、null、Number、string、boolean）；引用数据类型object（函数function）
   >
   > 运算符（算术、关系（Boolean）、逻辑、赋值、一元、三元、特殊）
   >
   > 流程控制（顺序结构、分支结构、循环结构、break、continue、return）
   >
   > 数组（越界访问、下标范围、数组对象的方法）
   >
   > 函数：定义、创建、调用、参数、返回值、回调函数、name属性（es6)、rest参数(es6)、箭头函数（es6)、作用域（概念、分类）、作用域链、闭包、内置顶层函数
   >
   > 原型、原型链、继承
   >
   > 对象、日期对象、正则对象

2. BOM浏览器对象模型：可以对浏览器窗口进行访问和操作。

   > window、location（href）、history(前进，后退，刷新）

3. DOM文档对象模型：通过创建树来表示文档，从而使开发者对文档的内容和结构具有控制力。用DOM API可以轻松操作文档。

4. 面向对象（表达）、单线程异步机制（表达）（js中哪些是异步的）

5. es6新增的属性

   > name属性，rest参数，箭头函数，let，块级作用域，class，模板字符串、解构赋值、给参数赋默认值

##### JS引入方式

1. 外部式

   ```html
   <script src="js/index.js"></script>
   ```

2. 嵌入式

   ```html
   <script>
   	alert("123")
   </script>
   ```

3. a链接

   ```html
   <a href="javascript:alert('123');"></a>
   ```

4. 重定向

   ```html
   <form action="javascript:alert('123');">
       <button>提交</button>
       <input type="button">
       <input type="submit">
   </form>
   ```

5. 事件中

   ```html
   <span onclick="alert('123')">this is span</span>
   ```

##### JS调试工具

1. `alert()` 弹出对话框
2. `document.write()` 输出到页面，可以解析html语法
3. `console.log()` 控制台输出
4. `prompt()` 输入框，第一个值是提示信息，第二个值是默认值
5. `confirm()` 带确定和取消的对话框，返回值为boolean值，true或false

##### 注释

作用：可以添加注释来对JavaScript进行解释，提高代码的可读性，还可以用于停靠代码。

- 单行注释 `//`
- 多行注释 `/* */`

# ECMAScript基础语法

### 变量与常量

#### 变量

###### 什么是变量？

> 可变的量（可以存储数据的一个容器。可以存储和引用任何数据类型）

###### 声明关键字

> var 存在变量提升现象  1.预解析 2.解析
>
> let 不存在变量提升现象

###### 语法

> let 变量名
>
> var 变量名

###### 变量定义的四种方式

1. 先声明后赋值

   ```js
   let a;
   a=123;
   ```

2. 声明的同时赋值

   ```js
   let a=123;
   ```

3. 一次声明多个变量后赋值

   ```js
   let a,b,c;
   a=123;
   b=456;
   c=789;
   ```

4. 一次声明多个变量的同时赋值

   ```js
   let a=123,b=456,c=789;
   ```

###### 变量的命名规范

1. 严格区分大小写
2. 变量的命名必须以字母，下划线或`$`开头，余下的部分可以是任意的字母，数字，或者下划线，`$`
3. 不能用关键字和保留字来命名
4. JS自己的命名习惯：驼峰命名法、首字母大写、命名要有意义

#### 常量

###### 什么是常量？

> 固定不变的量，一旦声明不可改变

###### 声明关键字

> const

> 声明时必须赋值

### 数据类型

#### 初始类型 

> 初始数据类型保存在栈区 （先入后出）

1. **Undefined** 

   > 声明变量但是没有赋值 

2. **Null** 

   > 未声明&&未定义，相当于一个占位符
   > null 属于对象object
   > null Null NULL完全不一样

3. **Number**

   - 整型、浮点型

   - 二进制0b、八进制0o、十进制、十六进制0x

   - 科学计数法表示 
     - 10e10  表示10乘以10的10次方
     - 3e6  表示 3乘以10的6次方
   - 最值
     - 最大值：Number.MAX_VALUE   1.7976931348623157e+308
     - 最小值：Number.MIN_VALUE   5e-324

   - 特殊值
     - NaN非数字
     - +0
     - -0
   - 无穷
     - 正无穷：infinity      1/0
     - 负无穷：-infinity     -1/0
     - 被除数/null  相当于  被除数/0

4. **string**
   - 语法
     
     - 反引号``（模板字符串的使用）(使用反引号时要注意兼容性)      
     
     - 单引号''         
     
     - 双引号""
   - 用法
     - 只能成对出现，不能相互交叉使用。
     - 可相互嵌套
   - 字符编码：ASCII    GB2312     GBK     UTF-8      Unicode
   - 转义字符：\

```
ASCII编码中
A   十进制65   十六进制41
a   十进制97   十六进制61
```

```
\n换行    \r回车    \t制表符    \b空格    \'单引号    \"双引号    \\斜杠
```

5. **boolean**

   > true    false

6. ES6新增：**symbol**

   > symbol表示独一无二的值，它的实例是唯一且不可改变的

#### 引用类型 

> 引用数据类型object一般保存在堆区

> object 包含相关属性和方法的集合，包括Function，Array，Object

**function属于object但是类型是Function**

###### 栈（数据结构）

栈是一种先入后出的数据结构。

###### 栈区

由编译器自动分配，用来存放函数的参数或者变量的值（局部变量）

###### 栈区存放的优点

- 数据的长度是固定的，访问速度很快
- 我们的初始数据类型一般存放在栈区中

###### 堆区

- 数据的长度不固定，访问速度较慢
- 一般引用数据类型存放在堆区

### 运算符

#### 1.  算术运算符
```js
+  -  *  /  %取余  ++自增  --自减  **求幂 

x**y   x的y次方  同Math.pow(x,y) 

// 数字+'' 将数字转换为字符串  
'abc'+123   //abc123
'abc'+true  //abctrue
123-"123"   //0
123-"12a"   //NaN
123-true    //122  true 1
```
#### 2.  关系运算符 
结果为boolean
```js
<  <=  >  >=  == != ===  !==
== 判断值
=== 判断值和类型
```
#### 3.  赋值运算符 
```js
=  +=  -=  *=  /=  %=
```
#### 4.  逻辑运算符
```js
&&与  同真为真，有假为假
||或  有真为真，同假为假
!非

短路原则
let a
a=10  (除0和NaN，其余都是真)
true || (a=20)      // true
false && (a=10)     // false

//逻辑判断的顺序
let x=1;
let y=2;
let z=x&&y;
let m=!x&&y;
console.log(z,m);  //  2  false
```
#### 5.  一元运算符
```js
typeof 测试操作数类型
eg:    typeof(123)  //number
       typeof('123')  //string

+10 正数
-10 负数

++  自增
--  自减

new  实例化对象
delete 删除对象属性或变量

扩展运算符： ...arr  输出arr中的元素
```
#### 6.  三元运算符
```js
表达式 ? 为真执行项：为假执行项

eg:
1>2 ? alert("1>2") :alert("2>1")
```
#### 7.  特殊运算符
```
()优先运算，函数调用
\ 转义
,  声明多个变量,赋值
```

### 控制流程

#### 顺序结构
#### 分支结构  
（1）单路分支
```js
if(表达式){
    程序…
}
```
（2）双路分支
```js
if(表达式){
    程序…
}else{ 
    程序…
}

//三目运算
let status = confirm("下雨") ? console.log('打伞'):console.log('不打伞')
```
（3）多路分支
```js
if(表达式){
    程序…
}else if(表达式){
    
}else{
    
}

switch(变量){
    case 值1:语句1;break;    // 值为变量能够取到的值,值与变量的数据类型要相同
    case 值2:语句2;break;
    ...
    default:其他情况;
}
```
#### 循环结构
（1）for循环
```js
for(初始值;循环条件;步进值){
    
}
```
（2）while循环：先判断，后执行。
```js
while(条件){
    
}

//猜数字游戏
let num = parseInt(Math.random()*55+10)
while(true){
    let num2 =parseInt(prompt("请输入一个数"))
    if(num2==num){
        alert("恭喜你，猜对了")
        break      
    }else if(num2<num){
        alert("数字过小")
    }else{
        alert("数字过大")
    }
}
```
（3）do while ：先执行，后判断。最少之行一次
```js
do{
    循环体
}while()
```
**for循环和while循环的使用选择**   

1. for循环必须知道循环次数，而while循环可以不确定  
2. 所以在已知循环次数情况下用for循环  
3. 使用时优先考虑for循环，当无法写出循环条件的起始结束步进值是考虑用while循环。

**干预循环**  

1. continue：退出本次循环，进行下一次  
2. break 终止循环

### 数组

> 数组：引用类型。存储在堆区 

#### 一维数组

###### 定义

存储一系列相关数据的集合。

###### 语法 

字面量的方式：let arr =[1,2,3,4,5,6] 
实例化对象的方式：

```js
let arr2 = new Array(1,2,3,4,5,6)    
let arr3=new Array(8)  指定了数组的长度为8    
let arr4=[undefined,null,"string",123,NaN]  
```
###### 访问数组

`arr[下标] `
下标：每个元素在数组中的位置称为下标。 
下标的范围：0~arr.length-1 
数组[下标]=``  "" ''  

```
反引号``：会识别其中的格式。
```
###### 数组的长度

 `arr.length `
数组可以越界访问 值为undefined

###### 数组的遍历

 对数组的元素进行依次访问。  

```js
for(let i=0;i<arr.length;i++){
    console.log(arr[i])
}
for(let value of arr){
    console.log(value)   显示数组中的元素
}
for(let index in arr){
    console.log(index)    显示数组元素的下标
}
```
###### 数组的添加修改元素 

`arr[index]=10 `

###### 数组删除元素

```
arr.splice(index,length)  从index位置开始，删除length个元素
arr.splice(下标，删除元素的个数，要添加的元素)
```
###### 浅拷贝与深拷贝

```js
let arr1=[1,2,3,4,5]
let arr2 =arr1   //传址 
arr2[0]="aa"
console.log(arr1)     
console.log(arr2)

let arr1=[1,2,3,4,5]
let arr2 =[]    //新建地址，地址中的元素为空
for(let i of arr1){  
    arr2[i]=arr1[i]   //传值
}
arr2[0]="aa"  
console.log(arr1)     
console.log(arr2)
```
#### 二维数组
```js
let arr=[[1,2],[3,4],[5,6]]
for(let i=0;i<arr.length;i++){
    for(let j=0;j<arr[i].length;j++){
        console.log(arr[i][j])
    }
}

//二维的深拷贝
let arr1=[[1,2],[3,4],[5,6]]
let arr2=[]
for(let i=0;i<arr1.length;i++){
    let newArr=[]
    for(let j=0;j<arr1[i].length;j++){
        newArr[j]=arr1[i][j]
    }
    arr2[i]=newArr
}
arr1[0][0]="aa"
console.log(arr2)
```
#### 数组解构赋值(ES6)
> 以数组的形式为变量赋值

> 模式匹配，解构赋值，赋值不成功显示undefined，等号右边必须是数组否则报错；

```js
let [a,b,c]=[1,2,3]  //1 2 3
let [a,b,c]=[1,2]  //1 2 undefined

//默认值
let [x=1]=[]   //1
let [x=1]=['a'];   //a

//注意
等号右边是数组，否则会报错
let y=true;  //报错
let y=[true]  //true

```
#### 数组扩展运算符(ES6)
作用：数组的合并
```js
let arr1=[1,45,7,6]
let arr2=['a','b','c']
console.log([...arr1,...arr2])
let arr3=arr1.concat(arr2)
console.log(arr3)

let [d,...[e,f]]=[1,2,30],
console.log(d,e,f)
```

### 函数

#### 函数

###### 函数的定义
封装一个特定功能的代码块，用于重复使用。  
###### 函数的优势
   1. 调用更加方便
   2. 维护更加容易
   3. 使程序更加简洁
   4. 逻辑更加调理

###### 函数的创建
1. 通过function关键字进行创建

```js
function 函数名字([形参]){
    函数体
    [return ]
}

eg:
//输出五颗星
function printX(){
    console.log("******")
}
printX()   //调用
```
2. 字面量的方式

```js
let fn =function(){}   匿名函数
调用方式：
变量名()

let fn =function(){}
fn()
```
3. 通过实例化Function()

```js
let fn =new Function(变量，函数体) //变量和函数体的数据类型是字符串
eg:
let fn =new Function('a','b','alert(a+b)')
fn(10,20)
```
###### 函数的调用
1. 函数名()
```
函数名([实参])
```
2. 变量名()
3. 事件后调用 （ 在行内事件后调用函数）

```js
let box =document.querSelector(".box")

<div onclick="fn()">click me</div>
function fn(){
    console.log(1)
}
```
4. 匿名函数的自调用

```js
(function(a,b){
    alert(a+b)
})(10,20)
```
###### 参数  
设置参数的目的：使函数更加灵活，可以重复使用

形式参数：创建函数时创建的参数，接收实参，以便于在函数内部使用 （形参的作用域属于局部作用域。）
实际参数：调用函数时创建的参数，传递参数，将外部的数据传入函数体 

###### 参数个数

- 形参个数=实参个数： 从左到右，一一对应。 
- 形参>实参：多出的形参为undefined 
- 实参>形参：多出的实参通过arguments对象，或rest剩余参数接收   

1. arguements对象 
在函数创建是自带arguments对象，接收全部参数；类型为Object
```
每创建一个函数，函数就会隐形的创建一个arguments对象。它包含实际传入参数的信息。

arguments对象的属性:
    length 获取实参的个数
    callee 获取函数本身的引用
    
访问传入参数的具体的值。argumens[下标]
```

2. rest参数：（ES6) 
接收多余的参数  类型为数组，所以可以用Array(forEach)进行数组遍历

```js
//rest操作符 rest参数
function fn(a,b,...arr){   
    console.log(a,b,arr)
}
function(1,25,7,8,96,5,4,2,53)
```

###### 默认参数 (四种方式) 

- 方式一：三元表达式 三目运算

  ```js
  function fn(num){
      num = num==undefined?3:num;
      ...
  }
  ```

- 方式二：if else分支语句

  ```js
  function fn(num){
      if(num=='undefined'){
          num=3;
      }else{
          num=num;
      }
  }
  ```

- 方式三：逻辑或 短路原则

  ```js
  num=num||3;
  
  function bt(a,b){
      a=a || 1;   短路原则
      b=b||1;
      return a*b;
  }
  ```

- 方式四：es6参数默认值

  ```js
  function fn(a=1,b=1){  //默认值永远是靠后的
      
  }
  //默认参数
  function fn(name="小白"){
      console.log(name)
  }
  fn("小红")
  ```

###### 返回值 
每一个程序运行完之后都有一个返回值    

函数没有写return，默认返回值为undefined
>作用： 
>1.return可以终止函数，return可以返回任意数据类型。 
>2.return可以给函数一个返回值，在外部可直接使用 
>3.返回值只有一个 
>4.在一个代码中可以有多个return分支，但只有一个被执行。

###### 函数的重载

函数根据传入参数的数量或者数据类型的不同，实现不同的功能，就叫做函数的重载。

###### name属性

> 返回函数的函数名

###### js宿主环境

```js
//this
function fn(){   
    console.log(this)  //普通函数的this指向window
}
console.dir(window)
window.alert()   //window省略 
```

#### 作用域

> 变量作用的范围

###### js是一个函数作用域  

###### 作用域的分类

- 全局作用域
  - 用 var/let 在全局声明的变量；
  - 变量不用var/let声明，直接赋值的变量也拥有全局作用域；
- 局部作用域
  - 形参拥有局部作用域；
  - 用 var/let 关键字在函数内部声明变量；
- 块级作用域
  - { }  大括号即为块级作用域；

###### 作用域链

> 为变量赋值时遵循的一条规则。只能从内部访问外部的值。 

我们可以把作用域看成是链条连接起来的，这样能使得函数有序的进行运行。
```js
[[scopes]]=[windows.name,name]  保存window信息，和自己的内容  不会真是保存，保存地址。
Windows
```

```js
let name="xiaoba"   var
function fn(){ 
    console.log(name)  暂时性死区
    let name="xiaohong"
}
```

> 全局环境：windows全局环境，不在任何局部中 
> 局部环境：每一个函数内部都是局部环境 
> 全局变量：在windows环境中创建的变量  定义在全局环境中的变量 
> 局部变量：在函数内创建的变量   定义在局部环境中的变量
> 注意：局部环境可以调用全局变量，全局环境不可以调用局部变量。

```js
let aa=10
function fn(){
    aa+=10
    console.log(aa)
}
fn()
console.log(aa)
```

#### 回调函数

###### **回调函数**

> 将一个函数的指针当做参数传给另一个函数，并且在调用这个参数的时候，那么这个函数就叫做回调函数。 
> 把一个函数的指针当做另一个函数的参数。  

###### 回调函数的功能

> 在一个功能执行完成以后再进行另外一个功能的执行。

```js
//需求：在说完一段话之后再控制台输出一段文本
//定义一个say函数用来说话，定义一个write函数输出文本到控制台
function say(content,fn){
    alert(content);
    fn();  //fn表示的是write这个回调函数，所以要实现函数的功能，需要调用fn这个函数
}
function write(){
    console.log("nice to meet you!");
}
say("hello",write);
```

#### 递归函数
递归函数：在函数内部调用函数本身，但是使用时要注意，否则会陷入死循环 
**使用递归函数的时候一定要有一个终止的条件。**  

```js
//递归函数的用法：求数字的阶乘  n的阶乘

function jiecheng(num){
    if(num===1){
        return 1;
    }
    else{
        return num*jiecheng(num-1);
    }
}
let num=prompt("请输入一个数","5");
console.log(jiecheng(num));

```
#### 闭包
###### 目的

> 为了解决函数外部不能访问函数内部变量的问题。

###### 概念

> 闭包指的是在函数外部有权访问函数内部的变量，这个函数就称之为闭包函数。
> 函数内部的函数，操作并且返回这个函数的变量。

```js
function  bibao(){
    let a=10;
    return function(){
        return a;
    }
}
let b=bibao();
console.log(b());
```
###### 闭包的应用

* 函数只需要执行一次，其内部变量不需要维护
* 封装相关的功能集（jQuery）
* 可以读取函数内部的变量。  

###### 闭包函数的弊端：

闭包会使函数内部的变量暴露在内存中，导致内存空间的浪费。并且因为闭包将函数内部变量暴露出来，所以会导致内存的泄露（IE浏览器中）。 
解决方法：在退出函数的时候将不需要的变量删除。

#### 块级作用域
在ES5中没有块级作用域，所以下面代码的最终结果为10
```js
for(var i=0;i<10;i++){
    
}
console.log(i);  //10
```
在ES6中新增了块级作用域,所以下面代码结果会报错
```js
for(let i=0;i<10;i++){
    
} 
console.log(i);  //报错 i is not defined
```
###### 块级作用域的表现形式 

块级作用域由一对{}包裹，我们学习的if或者for中的{}都拥有块级作用域（ES6中的let声明也拥有块级作用域）  

#### ES6中新增了解构赋值
在ES6中允许我们以一定的格式从数组或者对象中提取值对变量进行赋值，这个过程就叫做解构  

* 用处
* 在函数中接收参数
* 接收函数的返回值
* 函数的返回值只有一个会起作用，当有多个返回值的时候可以将它们放在一个数组中作为返回值

```js
function fn(){
    ...
    return [a,b,d];
}
let [a,b,d]=fn();

function fn([a,b,c,d=4]){
    return a+b+c+d;
}
let a=fn([1,2,3,10]);
console.log(a);
```
#### ES6箭头函数

> this：this指向不会改变

ES6中新增了箭头函数来定义函数

```js
//(参数1,参数2,...)=>{函数体}
()=>{...}
```
作用：
使函数变得更加整洁
简化回调函数
```js
function fn(callback){
    ...
    callback();
    ...
}
fn(()=>{alert(1)})
```

#### 内置顶层函数
概念：由JS预备好的可以在任意地方直接调用的函数叫做内置顶层函数（拥有全局的作用域）  
作用：进行数据类型的转换
分类：隐式类型转换，强制类型转换。

###### Number()
> 将任意数据类型转为数值型

1. true转为1，false转为0，null转为0
2. undefined转为NaN
3. 字符串：
    1. 如果字符串中只包含数字，那么会转为字符串所对应的的数值，并且会将无意义的前导0或者后导0去掉
    2. 如果字符串中是一个标准的浮点型，那么会转为对应的浮点型，并且会将无意义的前导0或者后导0去掉
    3. 如果是空字符串转为0
    4. 如果是其他的转为NaN

###### parseInt() 
> 将字符串转换为整型

1. 如果一个字符串中只包含数字，会转成对应的数值型（整型）
2. 如果字符串中有多个空格，会找到第一个不为空的值进行转换
3. 如果不是以数字，"-数字"，"空格"开头的字符串，转为NaN
4. 如果后面跟两个参数：第一个表示要转换的数据，第二个表示数据的进制。最终的转换结果为十进制

###### parseFloat()
> 将字符串转为小数

1. 小数点只有一个会起作用
2. 如果字符串是一个整数，返回整数本身，不会返回浮点数

###### String()
> 将任意数据类型转为字符串

* null,undefined,true,false以及纯数字，转为它本身所对应的的字符串

###### Boolean()
> 将任意数据类型转为布尔值

* null,undefined,false,0,'',NaN转为false
* 除了上面的六个以外，其他的都为true
```js
console.log(''== 0)  //true
console.log(''===0) //false
```

###### isNaN()
> 判断一个数据是否能够转为数值

* 如果能返回false，如果不能返回true
* isNaN(x)返回结果为false，那么x在任何算术表达式中都不会使结果为NaN
* isNaN(x)返回结果为true，那么x在任何算术表达式中都会使结果为NaN

###### eval()
> 将传入的字符串当做js代码执行

* 避免在不必要的情况下使用eval
    - 需要解析，速度慢
    - 操作的字符串容易受到篡改，所以安全性较差

###### Number扩展
- Number.isFinite()判断一个数据是否为有限的，如果是返回true，如果不是返回false 
- Number.isNaN()判断一个数据是否是NaN  

```js
// 区分 isNaN()与Number.isNaN()
console.log(isNaN("true"));  //true
console.log(Number.isNaN("true"))  //false
```
Number.isInteger()判断一个数据是否为整数 
因为在js中整型和浮点型的存储机制相同，20.0和20表示的是一个值


#### 数据类型转换
###### 强制类型转换
> 跟前面学习的内置顶层函数相关，使用内置顶层函数可以将数据强制转换为某一种类型

* Number()  强制转为数值型
* String()  强制转为字符串型
* Boolean()  强制转为布尔类型
* parseInt() 强制转为整型
* parseFloat() 强制转为浮点型

###### 隐式类型转换
> 因为js是一门弱类型的语言，所以在运算符两侧的数据可以是任意数据类型。任意数据类型可以进行运算就是因为js引擎在解析的时候隐式的帮助我们进行了数据类型的转换。

**算术运算符**

`-*/% ` 会将运算符左右两侧的数据转为数值型进行运算（隐式调用Number()函数进行转换）  
+字符串的拼接
 非字符串类型在进行相加时规则和     `-*/%`相同

**关系运算符**

* 两个字符串进行比较，依次比较字符串的字符编码
* 除此以外，都会隐式的调用Number()函数进行数据转换，然后进行比较

**逻辑运算符**

* && || ！ 运算会隐式调用Boolean()函数将运算符左右两侧的数据转为布尔值，再进行逻辑运算
* 语句
    * if,while,do_while,三元表达式中的判断条件都会隐式的调用Boolean()函数，按照这个函数的转换规则转为布尔值进行比较

### 对象

>  首先对象是一个引用数据类型，对象可以拥有各种各样的属性，对象就是属性的无序集合。

#### 对象

###### 对象的组成部分

| 名称 |                             作用                             |
| :--: | :----------------------------------------------------------: |
| 属性 |                        描述对象的状态                        |
| 方法 | 当属性的属性值是一个函数的时候，我们称之为方法。方法用来描述对象的行为 |

###### 对象的创建方式
1. 隐式创建  使用json格式的对象  

```js
let obj = {
    
}
```
2. 通过实例化Object构造函数  

```js
let obj = new Object();
```
3. 通过实例化自定义构造函数

```js
function Person(){  //自定义构造函数
    
}
let student = new Person(); //实例化
```
4. 类（ES6）

```js
class Float{
    // 构造函数
	constructor(){        // constructor 指向构造函数
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

###### 对象属性的增删改查

**增**

1. 创建的同时进行属性添加

```js
let lala = {
    name:"啦啦",
    sex:"女",
    age:12
}
```
2. 先创建对象，通过`对象.属性名`来添加属性

```js
let lala={}
lala.name="啦啦";
lala.sex="女";
lala.age=12;
```
**改（更新）**

* 通过`对象.属性名=新的属性值`来进行属性的更新

**查（查看）**

* 通过`对象.属性名`来进行属性的查看

**删除**

1. 销毁对象（将整个对象进行销毁）

```js
对象=null;
```
2. 删除对象的某一个属性

```js
delete 对象.属性
```
###### 对象的遍历
通过遍历将对象中每一个属性都获取到
```js
let suancai={
    name:"酸菜",
    price:"15/份",
    taste:"酸辣"
}
for(let i in suancai){
    //console.log(i);
    console.log(suancai[i]);  //对象的属性名保存在了变量i中，通过中括号[变量]访问对象的属性
}
```
###### 对象的拷贝
**浅拷贝**

传址，只是将对象的存储地址进行了复制，如果对原来的对象进行修改，会影响到拷贝之后的新对象
```js
let newObj=obj;
```

**深拷贝**

传值，将对象中的所有属性和方法放入到一个新的对象中，当我们对原来的对象进行修改时不会影响新对象  

实现深拷贝：利用递归函数的特性进行深拷贝

```js
let animal={
    name:"动物",
    sex:"公",
    age:5,
    color:{
        color1:"red",
        color2:"blue",
        color3:"yellow",
        colors:{
            colors1:"red and blue",
            colors2:"yellow and pink"
        }
    },
    arr:[4,5,87,9,6]
}
function deepCopy(obj){
    let nObj=null;
    if(typeof obj==="object" && typeof obj !==null){
        nObj= obj instanceof Array ? [] : {};    //instanceof  判断实例化构造函数
        for(let i in obj){
            nObj[i]=deepCopy(obj[i])
        }
    }else{
        nObj=obj;
    }
    return nObj;
}
let dog=deepCopy(animal);
dog.name="哈士奇"
dog.color.colors.colors1="ss"
dog.arr[0]=100;
console.log(dog)
console.log(animal)
```
#### ES6中新增的对象特性
###### 对象属性和方法的简写
当属性值保存在一个变量中，并且属性名与变量名相同，我们可以只写一个。

在ES6中方法的形式可以进行简写 

方法名(){函数体}

```js
let username="张三";
let obj={
    username,
    say(){
        alert("李四去哪儿了？");
    }
}
obj.say(); //弹出框
console.log(obj.username); //张三
```
###### 对象的解构赋值
* 接收函数的参数  
* 接收函数的返回值 

==对象的解构赋值与数组的解构赋值==

###### 对象的rest参数
* 用于解构赋值  
* 接收函数的参数

#### 对象的特性
##### 封装
封装：将对象的所有组成部分组合起来，尽可能的隐藏对象的部分细节，使其受到保护，只提供有限的接口进行访问。

###### 封装方法
1. 工厂函数：将创建对象以及对象的属性的添加都封装起来

```js
function Animal(name,sex,purpose){
    let animal={};
    animal.name=name;
    animal.sex=sex;
    animal.purpose=purpose;
    return animal;
}
let dog=new Animal("哈士奇","公","拆家");
console.log(dog);
```
2. 通过构造函数的方式封装

```js
function Animal(name,sex,age,purpose){
    this.name=name;
    this.sex=sex;
    this.age=age;
    this.purpose=purpose;
}
let dog=new Animal("哈士奇","公",3,"开心豆")
console.log(dog);
```
###### 原型
工厂函数以及构造函数在创建新的对象的时候会将所有的属性方法再复制一遍放入一个新的对象中，有一些公共的方法或者属性会被重复的保存，导致内存的负荷增大。 
为了解决这个问题，js为我们提供了原型的概念---原型用来存储对象中公共的属性或方法。  

###### 原型的分类  

- 构造函数的原型：`prototype` 
- 对象的原型：`__proto__ ` 

`__proto__`指向原型对象 prototype

原型对象prototype：是构造函数的属性，用来存放公共的属性和方法，节省内存。

**instanceof**：判断对象的构造函数，返回true 或 false

```js
function Person(name,sex,age,job){
    this.name=name;
    this.sex=sex;
    this.age=age;
    this.job=job;
}
Person.prototype={      //构造函数的原型
    say:function(){
        console.log("我们都爱说话");
    },
    eat:function(){
        console.log("我们都要吃饭")
    }
}
let player=new Person("颖宝","女",18,"演员");
console.log(player);
```
###### new操作的具体操作
1. 创建了一个空对象
2. 将构造函数的私有属性与方法放在这个空对象中
3. 将构造函数原型`prototype`中的公共属性和方法放在这个对象的原型`__proto__`中
```js
第一步：player={}
第二步：palyer={
            
        }
第三步：player.__proto__==Person.prototype
```
##### 继承
在js中基于对象创建一个新的对象，新对象拥有原对象的属性和方法，这个叫继承。
###### 实现继承的方法
1. 原型继承 
通过将父对象的构造函数实例放在子对象的原型中，实现继承。

```js
function Person(){
    this.name="姓名";
    this.sex="性别";
}
function Father(){
    // this.name="李爸爸";
    this.wife="刘女士";
}
Father.prototype= new Person();
let father=new Father();
console.log(father.name);
```
2. call继承 
将父对象的某一个方法暂时借给子对象，并且会立即执行
将父对象的构造函数整个都继承给子对象
格式：fun.call(obj,参数1,参数2)
本质上来说，call方法实际就是要改变fun函数内的this指向

```js
function Animal(){
    this.name="动物";
    this.say=function(a,b){
        console.log("我叫"+a+",我今年"+b+"岁了");
    }
}
function Dog(){

}
let animal=new Animal();
let dog =new Dog();
// animal.say.call(dog,"琪琪",12);  //继承单个方法,使用时立即执行函数
Animal.call(dog);   //继承整个构造函数
dog.name="琪琪";
console.log(dog);
```
3. apply继承 
用法与call相同 
不同的是apply传递参数的时候会将参数放在一个数组中传递，call会将一个一个用逗号隔开进行传递 
格式：fun.apply(obj,[参数1,参数2,...])

```js
function Animal(){
    this.name="动物";
    this.say=function(a,b){
        console.log("我叫"+a+",我今年"+b+"岁了");
    }
}
function Dog(){

}
let animal=new Animal();
let dog =new Dog();
// animal.say.apply(dog,["叮当",3]);
Animal.apply(dog);
dog.say("铛铛",3)
dog.name="铛铛";
console.log(dog);
```
4. bind 继承 
bind用法与call,apply相同，不同的bind不能继承整个构造函数，bind的继承结果会返回函数本身，不会立即执行 
bind符合我们正常的需求，可以将继承来的方法保存，当我们需要的时候再进行调用。 

```js
function Animal(){
    this.name="动物";
    this.say=function(a,b){
        console.log("我叫"+a+",我今年"+b+"岁了");
    }
}
function Dog(){

}
let animal=new Animal();
let dog =new Dog();
let a= animal.say.bind(dog);
a("铛铛",3)

```
##### 访问对象属性或方法的顺序

>对象本身=>构造函数=>构造函数的原型=>构造函数原型的构造函数=>构造函数原型的构造函数的原型...=>Object,如果都没有这个产生错误（如果访问的是属性，返回undefined；如果是方法返回一个错误）

##### 原型链

对象继承属性与方法时遵循的一条规则，`__proto__`与`prototype`组成。

>访问对象的属性或方法时，会从对象本身开始，去寻找，如果没有会去原型中去寻找，一层一层网上寻找，直到找到Object,null结束，这个过程就叫做原型链。

> 对象 => 对象原型 => 原型对象 => 原型对象的原型 => 原型对象原型的原型对象 => ... => Object => null

```js
/ 对象 属性 __proto__
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


### JS原生对象
> 由JS为我们准备好的可以直接使用的对象 
> Array对象，String对象，Object对象，Math对象，Date对象，正则对象

#### Array对象
数组对象有一些我们常用的属性或方法。
###### 属性
1. **length**:数组的长度，用来表示数组元素的个数
2. **constructor**：保存构造函数

###### 方法

1. **arr.push(元素)**  
>往数组的末尾添加一个或多个元素 
>返回值是修改后的数组长度 
>会修改原数组  

```js
let arr = [4, 5, 68, 7, 51, 2, 0, 40]
let b = arr.push(88, 16)
console.log(b)    // 10
console.log(arr)    // [4, 5, 68, 7, 51, 2, 0, 40, 88, 16]
```

2. **arr.unshift(元素)**  
>往数组的开头添加一个或多个元素 
>返回值是修改后的数组长度 
>会修改原数组 

```js
let arr = [4, 5, 68, 7, 51, 2, 0, 40]
let b = arr.unshift(88, 16)
console.log(b)    // 10
console.log(arr)    // [88, 16, 4, 5, 68, 7, 51, 2, 0, 40]
```

3. **arr.pop()**
>从数组的末尾删除一个元素 
>返回值是被删除的元素 
>会修改原数组  

```js
let arr = [4, 5, 68, 7, 51, 2, 0, 40]
let b = arr.pop()
console.log(b)    // 40
console.log(arr)    // [4, 5, 68, 7, 51, 2, 0]
```

4. **arr.shift()**
>从数组的开头删除一个元素 
>返回值是被删除的元素 
>会修改原数组（只能删除一个）

```js
let arr = [4, 5, 68, 7, 51, 2, 0, 40]
let b = arr.shift()
console.log(b)    // 4
console.log(arr)    // [5, 68, 7, 51, 2, 0, 40]
```

5. **arr.splice(起始下标,删除的长度,添加的元素)**
>有三个参数，分别表示起始下标，删除的长度，添加的元素（可以是任意数据类型） 
>会对原数组造成影响 
>返回值是被删除的元素组成的数组 
>添加可以将删除的长度为0，写上添加的元素

```js
let arr = [4, 5, 68, 7, 51, 2, 0, 40]
let b = arr.splice(1, 3, 99, 88, 77)
console.log(b)    // [5, 68, 7]
console.log(arr)    // [4, 99, 88, 77, 51, 2, 0, 40]
```

6. **arr.join(连接符)**  
>可以将数组转为用分隔符隔开的字符串 
>对原数组没有影响 
>返回值是一个字符串

```js
let arr = [4, 5, 68, 7, 51, 2, 0, 40]
let b = arr.join('-')
console.log(b)    // 4-5-68-7-51-2-0-40
console.log(arr)    // [4, 5, 68, 7, 51, 2, 0, 40]
```

7. **arr.slice(起始下标,结束下标)**  
>用于数字的截取，截取的内容包含起始下标，不包含结束下标 
>返回值是截取的数组 
>对原数组没有影响 
>参数可以是负数，表示从倒数第几个开始，到倒数第几个结束 
>如果只有一个起始下标，那么从起始下标截取到最后

```js
let arr = [4, 5, 68, 7, 51, 2, 0, 40]
let b = arr.slice(1, 4)
console.log(b)    // [5, 68, 7]
console.log(arr)    // [4, 5, 68, 7, 51, 2, 0, 40]

// 支持负数  （倒着从-1开始数）
let b = arr.slice(-7, -4)
console.log(b)    // [5, 68, 7]
console.log(arr)    // [4, 5, 68, 7, 51, 2, 0, 40]
```

8. **arr.concat()**
>用于多个数组的拼接 
>参数可以是一个或多个数组 
>返回值是拼接后的新数组 
>不会对原数组造成影响

```js
let arr = [1, 2, 3]
let arr1 = [4, 5, 6]
let arr2 = [7, 8, 9]
let b = arr.concat(arr1, arr2);
console.log(b)    // [1, 2, 3, 4, 5, 6, 7, 8, 9]
console.log(arr)   // [1, 2, 3]
```

9. **arr.indexOf()**
>查找一个元素在数组中第一次出现的位置 
>返回值是元素对应的下标，如果这个元素不存在返回-1  

```js
let arr = [4, 5, 68, 7, 51, 2, 0, 40]
let b = arr.indexOf(7)
console.log(b)    // 3
console.log(arr.indexOf(10))    // -1
console.log(arr)    // [4, 5, 68, 7, 51, 2, 0, 40]

//数组去重，用indexOf()实现

```

10. **arr.lastIndexOf()**
>倒序查找一个元素在数组中第一次出现的位置 
>返回值是元素对应的下标，如果这个元素不存在返回-1

```js
let arr = [4, 5, 68, 7, 51, 2, 0, 40, 7]
let b = arr.lastIndexOf(7)
console.log(b)    // 8
console.log(arr.lastIndexOf(10))    // -1
```

11. **arr.sort()**
>用于数组排序，如果没有参数，默认按照元素的字符编码排列 
>如果有参数，参数必须是函数（回调函数），函数有两个参数为a,b（a-b表示升序，b-a表示倒序） 
>返回值是排序之后的数组 
>会修改原数组

```js
let arr = [4, 5, 68, 7, 51, 2, 0, 40, 7]
let b = arr.sort()
console.log(b)    // [0, 2, 4, 40, 5, 51, 68, 7, 7]
console.log(arr)   // [0, 2, 4, 40, 5, 51, 68, 7, 7]

let arr = [4, 5, 68, 7, 51, 2, 0, 40, 7]
arr.sort(function (a, b) {
    // return a - b;      // [0, 2, 4, 5, 7, 7, 40, 51, 68]
    return b - a;        // [68, 51, 40, 7, 7, 5, 4, 2, 0]
})

完整表达式: a-b> 0 ? 1 : -1;  如果为1，交换位置(升)，如果为-1，不交换位置(降)

//箭头函数
arr.sort((a,b)=>a-b)     //升序
arr.sort((a,b)=>b-a)     //降序

//随机排序
arr.sort(() => {
    return Math.random() - 0.5;
})
```

12. **arr.forEach()**
>用于数组的遍历 
>参数是一个回调函数，回调函数有两个参数，第一个表示数组元素，第二个表示元素下标 
>没有返回值，默认为undefined
>对原数组没有影响


```js
let arr = [4, 5, 68, 7, 51, 2, 0, 40, 7]
let a =arr.forEach((v,i)=>{
    //遍历执行的程序
})
```

13. **arr.filter()**
>用于数组过滤，按回调函数的条件进行过滤 
>参数是回调函数，回调函数的参数有两个，第一个表示数组元素，第二个表示元素下标（回调函数必须有返回值，返回一个筛选条件）
>一个数组到另一个数组：范围会小于等于

```js
let arr = [4, 5, 68, 7, 51, 2, 0, 40, 7]
let b = arr.filter(function (value, index) {
    return value > 6;       //筛选arr数组中值大于6的元素
})
console.log(b);   // [68, 7, 51, 40, 7]
```

14. **arr.map()**
>数组映射，按照回调函数的结果将数组元素放大或缩小 
>参数是回调函数，回调函数的参数有两个，第一个表示数组元素，第二个表示元素下标（回调函数必须有返回值，返回一个筛选条件） 
>一个数组到另一个数组：元素是一一对应的。范围不变。

```js
let arr = [4, 5, 68, 7, 51, 2, 0, 40, 7]
let b = arr.map(function (value, index) {
    return value * 2;        //将数组中的所有元素都乘以2返回
});
console.log(b);   // [8, 10, 136, 14, 102, 4, 0, 80, 14]

// 箭头函数
let b = arr.map((value,index)=>value*2);
console.log(b);
```

15. **arr.some()**
>判断是否存在满足条件的元素，存在返回true，不存在返回false 
>参数是回调函数，回调函数的参数有两个，第一个表示数组元素，第二个表示元素下标（回调函数必须有返回值，返回一个判断条件）

```js
let arr = [4, 5, 68, 7, 51, 2, 0, 40, 7]
let b = arr.some(function (value, index) {
    return value < 6;
});
console.log(b);   // true
```

16. **arr.every()**
>判断数组中的每一个元素是否都满足条件，存在返回true，不存在返回false 
>参数是回调函数，回调函数的参数有两个，第一个表示数组元素，第二个表示元素下标（回调函数必须有返回值，返回一个判断条件）

```js
let arr = [4, 5, 68, 7, 51, 2, 0, 40, 7]
let b = arr.every(function (value, index) {
    return value < 6;
});
console.log(b);   // false
```

17. **arr.reverse()**
>数组倒序
>
>会影响原数组

```js
let arr = [4, 5, 68, 7, 51, 2, 0, 40, 7]
let b = arr.reverse();
console.log(b);   // [7, 40, 0, 2, 51, 7, 68, 5, 4]
console.log(arr);   //  [7, 40, 0, 2, 51, 7, 68, 5, 4]
```

18. **arr.includes()**
>判断某一个数据是否存在于数组中，存在返回true，不存在返回false 
>可以有两个参数，第一个表示被检索的元素，第二个是检索开始的元素

```js
let arr = [4, 5, 68, 7, 51, 2, 0, 40, 7]
let b = arr.includes(5)
console.log(b);   // true

//两个参数
let arr = [4, 5, 68, 7, 51, 2, 0, 40, 7]
let b = arr.includes(5, 2)
console.log(b);   // false
```
#### String对象
**字符串：** 使用单引号或者双引号包裹起来的内容就是一个字符串 
单双引号可以相互嵌套，但是不能交叉使用，单引号不能嵌套单引号，双引号不能嵌套双引号    

###### 属性
>**length**:表示字符串的长度（字符个数）

###### 方法
1. **str.charAt(index)**
>返回字符串中下标所对应的字符 
>参数是下标（数字） 
>返回值是对应的字符 
>不会影响原字符串  

```js
let str = "abcdef123abcdef";
let s = str.charAt(3);
console.log(s);  // d
console.log(atr)  // abcdef123abcdef
```

2. **str.charCodeAt(index)**
>返回字符串中下标所对应的字符的ASCII编码 
>参数是下标（数字） 
>返回值是对应的字符的ASCII编码 
>不会影响原字符串  

```js
let str = "abcdef123abcdef";
let s = str.charCodeAt(0);
console.log(s);  // 97
```

3. **String.fromCharCode(ASCII)**
>返回ASCII编码对应的字符，一般用于字符与数字之间的转换 
>参数是ASCII编码 
>返回值是编码对应的字符

```js
let s = String.fromCharCode(65);
console.log(s);   //A
```

4. **str.indexOf()**
>返回字符在字符串中第一次出现的位置（从前往后） 
>参数是需要寻找的字符 
>返回值是对应的下标 
>如果不存在返回-1

```js
let str = "abcdef123abcdef";
let s = str.indexOf('a');
console.log(s);  // 0
```

5. **str.lastIndexOf()**
>返回字符在字符串中最后一次出现的位置（从后往前） 
>参数是需要寻找的字符 
>返回值是对应的下标 
>如果不存在返回-1

```js
let str = "abcdef123abcdef";
let s = str.lastIndexOf('a');
console.log(s);  // 9
```

6. **str.replace(替换的字符,替换后的字符)**
>将匹配到的字符进行替换
>参数1：被替换的内容 
>参数2：替换后的内容 
>replace支持正则匹配

```js
let str = "abcdef123abcdef";
let s = str.replace('abc', 'xyz');
console.log(s);  // xyzdef123abcdef
console.log(str);  // abcdef123abcdef

//正则匹配
let str = "abcdef123abcdef";
let s = str.replace(/abc/g, 'xyz');
console.log(s);  // xyzdef123xyzdef
console.log(str);  // abcdef123abcdef
```

7. **str.slice(起始下标,结束下标)**
>截取对应的字符 
>参数1：截取开始的位置 
>参数2：截取结束的位置 
>截取的内容包括开始位置，不包括结束位置 
>支持负数

```js
let str = "abcdef123abcdef";
let s = str.slice(0, 6);
console.log(s);  // abcdef
console.log(str);  // abcdef123abcdef

let str = "abcdef123abcdef";
let s = str.slice(-6, -1);
console.log(s);  // abcde
console.log(str);  // abcdef123abcdef
```

8. **str.substring(起始下标,结束下标)**
>截取对应的字符 
>参数1：截取开始的位置 
>参数2：截取结束的位置 
>截取的内容包括开始位置，不包括结束位置 
>不支持负数

```js
let str = "abcdef123abcdef";
let s = str.substring(0, 6);
console.log(s);  // abcdef
console.log(str);  // abcdef123abcdef
```

9. **str.substr(起始下标，截取的长度)**
>根据截取的字符长度进行截取 
>参数1：截取开始的位置
>参数2：截取的字符长度 

```js
let str = "abcdef123abcdef";
let s = str.substr(6, 3);
console.log(s);  // 123
console.log(str);  // abcdef123abcdef
```

10. **str.split()**
>根据给定字符将字符串分割成一个数组 
>参数是分隔符 
>返回值是一个分割后的字符组成的数组，被用作分隔符的字符串不会出现在数组中

```js
let str = "abcdef123abcdef";
let s = str.split('b');
console.log(s);  // ["a", "cdef123a", "cdef"]
console.log(str);  // abcdef123abcdef
```

11. **str.toLowerCase()**
>将字符串中的字符转为小写 

```js
let str = "ABCDEF123abcdef";
let s = str.toLowerCase();
console.log(s);  // abcdef123abcdef
console.log(str);  // ABCDEF123abcdef
```

12. **str.toUpperCase()**
>将字符串中的字符转为大写

```js
let str = "abcdef123abcdef";
let s = str.toUpperCase();
console.log(s);  // ABCDEF123ABCDEF
console.log(str);  // abcdef123abcdef
```

13. **str.trim()**
>去除字符串前后的空格

```js
let str = "   abcdef   123   abcdef   ";
let s = str.trim();
console.log(s);  // abcdef   123   abcdef
console.log(str);  //    abcdef   123   abcdef   
```

14. **str.match()**
>检索指定的字符串，并将它放在一个数组中 
>参数：被检索的字符串 
>返回值：数组 
>支持正则查找

```js
let str = "abcdef123abcdef";
let s = str.match('abc');
console.log(s);  // ["abc", index: 0, input: "abcdef123abcdef", groups: undefined]
console.log(str);  // abcdef123abcdef
```

15. **str.concat()**
>用于连接一个或多个字符串 
>参数：被连接的字符串 
>返回值：连接之后的新字符串 
>对原来的字符串没有影响

```js
let str = "abcd";
let str1 = "efgh";
let str2 = "ijklmn";
let s = str.concat(str1, str2);
console.log(s);  // abcdefghijklmn
console.log(str);  // abcd
```

16. **str.padStart(),str.padEnd()**
>在字符串的开头或结尾添加字符到给定的字符串长度 
>参数1：新字符串的目标长度，如果目标长度小于或等于字符串的长度，那么返回字符串本身，不会添加字符 
>参数2：要添加的字符，如果参数2为空，默认使用空格添加 
>返回值：添加后的字符串

```js
// 一个参数
let str = "abcd";
let s = str.padStart(6);
console.log(s);    //   abcd
console.log(str);  // abcd

// 两个参数
let str = "abcd";
let s = str.padStart(6, 'abc');
console.log(s);    // ababcd
console.log(str);  // abcd
```

###### 对象与字符串之间的转换

1. JSON.stringify(对象)=>将对象转为一个字符串  
2. JSON.parse(字符串)=>将字符串转为一个对象  
>用处：可以进行深拷贝（除了方法以外）


####  数学对象
数学对象可以帮助我们进行一些数学运算，执行一些常见的算术运算  

###### 属性
| 属性    | 作用                          |
| :------ | :---------------------------- |
| PI      | 圆周率                        |
| E       | 常数e，自然对数的底数         |
| LN2     | 2的自然对数，以e为底2的对数   |
| LN10    | 10的自然对数，以e为底10的对数 |
| LOG2E   | 以2为底，e的对数              |
| LOG10E  | 以10为底，e的对数             |
| SQRT2   | 2的平方根                     |
| SQRT1_2 | 2的平方根的倒数               |


###### 方法
| 方法                | 属性               |
| :------------------ | :----------------- |
| Math.round()        | 四舍五入           |
| Math.ceil()         | 向上取整           |
| Math.floor()        | 向下取整           |
| Math.random()       | 取0-1之间的随机数  |
| Math.pow(x,y)       | 求x的y次幂         |
| Math.max()          | 求最大值           |
| Math.min()          | 求最小值           |
| numObj.toFixed(num) | 保留指定的小数位数 |

1. 获取x-y之间的随机数 
Math.random()*(y-x)+x
2. 获取x-y之间的随机整数
Math.floor(Math.random()*(y-x)+x)

#### 日期对象
>保存了从1970年1月1日到今天所经过的时间（毫秒数）  

###### 方法

| 方法              | 作用                                   |
| ----------------- | -------------------------------------- |
| getDate()         | 返回月份中的某一天                     |
| getDay()          | 返回星期中的某一天                     |
| getMonth()        | 返回月份，是0~11                       |
| getFullYear()     | 以四位数字返回年份                     |
| getHours()        | 返回小时                               |
| getMinutes()      | 返回分钟                               |
| getSeconds()      | 返回秒                                 |
| getMilliseconds() | 返回毫秒                               |
| getTime()         | 返回从1970年1月1日到现在经历过的毫秒数 |

###### 设置时间
>在实例化对象的过程中传入相应的参数设置时间   

```js
new Date(12345679)   // 传入一段毫秒数
new Date('December 17,1996 08:24:00')  // 传入一段标准的表示时间的字符串
new Date('1996-02-06T03:24:00')
new Date(2019,5,24)
new Date(2019,5,24,0,0,0)  // 将年月日时分秒按顺序传参
```
#### Object对象

###### 内置顶层对象
> 由JS内置好的对象，可以直接使用，不需要实例化
* Math对象

###### 本地对象
> 需要实例化之后才能使用
* Objext
* Array
* String
* 正则对象
* Function

###### Object对象的方法

1. **Object.assign(obj1,obj2,obj3)** 
用于对象的拼接。将多个对象拼接在一起，将obj2，obj3，拼接在obj1上  

==可用于深拷贝==

```js
let obj1={
    name:"张三"
}
let obj2={
    sex:"男"
}
let obj3={
    say(){
        console.log("ssss")
    }
}
let obj=Object.assign(obj1,obj2,obj3)
console.log(obj)  //{name: "张三", sex: "男", say: ƒ}
console.log(obj1) //{name: "张三", sex: "男", say: ƒ}
```

2. **Object.is()** 
判断两个数据是否相等，与===类似，但是有区别

```js
0 === -0  //true
Object.is(0,-0) //false
NaN === NaN   //false
Object.is(NaN,NaN) // true
```

3. **obj.prototype.isPrototypeOf(obj1)** 
判断一个对象是否存在于另一个对象的原型链中

```js
function Animal(){
        
}
var dog = new Animal();
console.log(Animal.prototype.isPrototypeOf(dog));      //true
```

4. **Object.defineProperty()** 
给对象添加一个新的属性，或者修改对象的一个属性  

```js
let obj = new Object();
Object.defineProperty(obj, 'name', {
    configurable: false,
    writable: true,
    enumerable: true,           //该属性是否可枚举
    value: '张三'
})
console.log(obj.name)  //张三
console.log(obj)  //{name: "张三"}
```
5. **Object.defineProperties(obj,props)** 
给对象添加或修改多个属性，方法

```js
let obj = new Object();
Object.defineProperties(obj, {
    name: {
        value: '张三',
        configurable: false,
        writable: true,
        enumerable: true
    },
    age: {
        value: 18,
        configurable: true
    }
})
console.log(obj.name, obj.age) // 张三, 18
```

6. **Object.freeze(obj)** 
防止对象被修改

```js
var obj={name:'张三',age:18};
Object.freeze(obj)
obj.name='李四';
obj.sex='男';
console.log(obj)                //{name: "张三", age: 18}
```

###### 对象的遍历

1. `for...in`

2. `Object.keys(obj) `
返回一个数组，数组中有对象obj所有的可枚举属性的键名（属性名）

3. `Object.values(obj) `
返回一个数组中，包含对象obj所有的可枚举属性的键值（属性值）

4. `Object.getOwnPropertyNames(obj) `
返回一个数组，包含除了symbol外的所有属性

5. `Reflect.ownKeys(obj) `
返回一个数组包含对象自身的所有属性


#### 正则表达式

* 作用：正则表达式通常被用来检索、替换那些符合某个模式(规则)的文本。  

- 执行字符串方法无法完成的特殊的匹配、拆分、替换功能
- 数据验证，文本替换，内容检索、过滤内容

###### 正则对象的创建

1. `new RegExp(正则表达式,模式修正符)  `
>模式修正符

| 名称 | 作用                     |
| ---- | ------------------------ |
| i    | 执行对大小写不敏感的匹配 |
| g    | 执行全局匹配             |
| m    | 执行多行匹配             |

2. 字面量方式创建正则表达式
`let reg=/正则表达式/模式修正符;`

###### 正则对象方法

1. `reg.test(str) `
判断字符串是否符合正则匹配

2. `reg.exec(str) `
查询字符串中，符合正则匹配的内容，返回值数组，如果没有返回null

3. `reg.compile(正则表达式[,flag]) `
在脚本执行中编译正则表达式，也可用于修改或重新编译正则表达式。

###### 原子，量词，边界

**原子**  ：是正则表达式最小的组成部分，包括英文，标点符号等。
| 原子 | 作用                               |
| ---- | ---------------------------------- |
| \d   | 匹配0-9的数字，等价于[0-9]         |
| \D   | 匹配除0-9以外的数字，等价于[^0-9]  |
| \w   | 匹配数字、字母、下划线             |
| \W   | 匹配除数字、字母、下划线以外的字符 |
| \s   | 匹配空格                           |
| \S   | 匹配非空格                         |
| .    | 查找单个字符，除了换行和行结束符   |
| \n   | 查找换行符                         |
| \f   | 匹配换页字符                       |
| \r   | 回车符                             |
| \t   | 制表符                             |
| \v   | 垂直制表符                         |

| 原子表 | 作用                             |
| ------ | -------------------------------- |
| []     | 只匹配其中的一个原子             |
| [^]    | 只匹配除了其中字符的任意一个原子 |
| [0-9]  | 匹配0-9之间的任意一个字符        |
| [a-z]  | 匹配a-z之间的任意一个字符        |
| [A-Z]  | 匹配A-Z之间的任意一个字符        |


| 量词  | 作用                              |
| ----- | --------------------------------- |
| {n}   | 表示前面的原子重复n次             |
| {n,}  | 表示前面的原子重复n次或n次以上    |
| {n,m} | 表示前面的原子是重复n-m次         |
| *     | 表示前面的一个原子重复0到无数次   |
| +     | 表示前面一个原子重复1到无数次     |
| ?=n   | 匹配任何其后紧跟字符串n的字符串   |
| ?!n   | 匹配任何其后不紧跟字符串n的字符串 |


| 符号 | 含义                                 |
| :--: | ------------------------------------ |
|  ^   | 从字符串的开头开始匹配               |
|  $   | 匹配到字符串的结尾                   |
|  \b  | 匹配单词边界                         |
|  \B  | 匹配非单词边界                       |
|  ¦   | 符号两侧符合一个就可以，和逻辑或类似 |

# BOM

Browser Object Model 浏览器对象模型
为我们提供了一些操作浏览器窗口的接口

### window对象

> Window对象是BOM的核心

###### 属性

| 属性          | 方法                             |
| ------------- | -------------------------------- |
| innerWidth    | 浏览器窗口的宽度                 |
| innerHeight   | 浏览器窗口的高度                 |
| screen.width  | 屏幕的宽度                       |
| screen.height | 屏幕的高度                       |
| top           | 返回窗口体系中的最顶层窗口的引用 |

###### 方法

| 方法名        | 作用                               |
| ------------- | ---------------------------------- |
| alert         | 弹出带有一段文本警示框             |
| confirm       | 弹出带有确认和取消的对话框         |
| prompt        | 弹出一个输出框                     |
| open          | 通过脚本打开一个页面               |
| close         | 关闭当前页面                       |
| scrollBy      | 按照指定的偏移量移动文档           |
| scrollTo      | 使文档滚动到指定的位置             |
| setInterval   | 时间函数，每过一段时间执行一次代码 |
| clearInterval | 清除由setInterval开启的定时器      |
| setTimeout    | 计时器，过一段时间之后再执行代码   |
| clearTimeout  | 清除由setTimeout开启的计时器       |

### console对象

console对象是window子对象，提供了对浏览器控制台的接入，可以在任何全局对象中访问

### location对象

location对象是window对象的子对象，包括当前加载页面的所有信息。除了这些信息之外，location还将当前页面的url解析成块。我们可以根据属性去访问路径不同的块。

###### location对象的属性

以‘http://www.baidu.com:80/javascript/001/BOM/?file=README.md#location对象’这个url为例
一个完整的网页url包括9个部分
协议://用户名：密码@域名：端口号/url路径；？search(参数)#hash(标识)

| 名字     | 作用域                         | 案例                                                         |
| -------- | ------------------------------ | ------------------------------------------------------------ |
| href     | 返回整个网页url地址的字符串    | http://www.baidu.com:80/javascript/001/BOM/?file=README.md#location对象 |
| origin   | 返回包含协议域名端口号的字符串 | http://www.baidu.com:80                                      |
| protocol | 返回网页协议的字符串           | http:                                                        |
| host     | 包含域名和端口号的字符串       | [www.baidu.com:80](http://www.baidu.com:80)                  |
| hostname | 包含域名的字符串               | [www.baidu.com](http://www.baidu.com)                        |
| port     | 端口号的字符串                 | 80                                                           |
| pathname | 网页的路径                     | javascript/001/BOM                                           |
| search   | url参数部分，开头是?           | ?[file=README.md](http://file=README.md)                     |
| hash     | 网页的标识符#开头              | #location对象                                                |

###### location对象的方法

| 名字     | 参数    | 作用                                                         |
| -------- | ------- | ------------------------------------------------------------ |
| assign   | url     | 加载给定url地址的资源                                        |
| reload   | boolean | 重新加载当前页面的资源                                       |
| replace  | url     | 用给定url的资源替换当前页面的资源                            |
| toString | 无      | 返回包含整个url地址的字符串，功能与location.href相同，但是获取的地址不能修改 |

**reload参数：** 当参数flase或不写时，页面会跟服务器确定当前页面的资源是否进行了更新，如果更新就重新加载，如果没有就使用本地的存储进行刷新；当参数为true时，无论页面资源是否更新都会从服务器重新加载页面资源

### history对象

是window对象的子对象，保存当前页面的所有历史记录。

###### history的属性

length:返回包含当前页面的历史记录的个数

###### history的方法

| 名字         | 参数            | 功能                                             |
| ------------ | --------------- | ------------------------------------------------ |
| back         | 无              | 返回到历史记录的上一个url，等价于history.go(-1)  |
| forward      | 无              | 进入到历史记录中的下一个url，等价于history.go(1) |
| go           | number          | 通过当前页面的相对位置加载不同的历史记录         |
| pushState    | state,title,url | 无刷新的将历史记录的最前方插入一条历史记录       |
| replaceState | state,title,url | 无刷新的将历史记录替换成新的历史记录             |

**history.go()参数：** 参数为-1，返回到上一页面；参数为1，进入到下一个页面；参数为0，刷新页面

# DOM

Document Object Model 文档对象模型

提供了操作文档的接口（API）

### DOM的属性

| 属性            | 描述                               |
| --------------- | ---------------------------------- |
| URL             | 返回网页的地址url                  |
| charset         | 返回字符集                         |
| title           | 返回网页的标题                     |
| forms           | 返回页面中所有的form表单           |
| images          | 返回页面中所有的img标签            |
| body            | 返回body标签，包含标签内的其他内容 |
| head            | 返回head标签，包含标签内的其他内容 |
| documentElement | 返回html标签，包含内部的其他内容   |
| cookie          | 返回当前页面的cookie，是一个字符串 |

### DOM 获取元素的方法

| 方法                                  | 描述                                                   |
| ------------------------------------- | ------------------------------------------------------ |
| document.getElementsByTagName(标签名) | 根据标签名获取html中的元素                             |
| document.getElementsByClassName(类名) | 根据类名获取html中的元素                               |
| document.getElementById(id名)         | 根据id名获取html中的元素                               |
| document.getElementsByName(name)      | 通过name属性获取html元素，返回值是一个NodeList节点属性 |
| document.querySelectorAll(css选择器)  | 通过css选择器获取html元素（结果是一个节点集合）        |
| document.querySelector(css选择器)     | 通过css选择器获取html元素（结果是单一的元素节点）      |

### 操作元素的内容

1. 元素.innerHTML
   获取或修改元素的内容，识别标签
2. 元素.innerText
   获取或修改元素的文本的内容，只识别文本
3. 元素.textContent
   获取或修改元素的文本内容，保留文本格式

### 操作元素样式

1. 元素.style.样式名="样式值"；
2. 元素.style.cssText="css样式组成的字符串"；

- 添加行内样式：`obj.style.attr=value;`
- 获取元素的样式：`window.getComputedStyle(ele,null).attr;`

### 操作元素的类名

```js
obj.classList.add("box");     //添加类
obj.classList.remove("box");   //移除类
obj.classList.toggle("box");   //切换类
```

**className**：表示所有的类名

```js
obj.className="box";
obj.className='';    //清空类名
```

### 操作id

### 操作属性

###### 标准属性（操作标签自带的属性）

- 设置：`obj.attr=value`
- 获取：`obj.attr`

###### 非标准属性（自定义的属性）

- 设置：`obj.setAttribute(name,value)`
- 获取：`obj.getAttribute(name)`
- 判断自定义属性是否存在：`obj.hasAttribute(name)`
- 移除：`obj.removeAttribute(name)`

### 元素的尺寸与位置

###### 元素的偏移量

1. offsetWidth：元素的实际宽度
2. offsetHeight：元素的实际高度
3. offsetTop：元素的左上角距离最近的具有定位属性的祖先元素的左上角垂直距离
4. offsetLeft：元素的左上角距离最近的具有定位属性的祖先元素的左上角水平距离
5. offsetParent：距离元素最近的具有定位属性的祖先元素

**上面的几种方法只能读取、不能修改，返回的是具体的数字（不带单位）**

- 返回元素的所有相关位置的尺寸信息：元素.getBoundingClientRect();

  | 返回值 | 作用                         |
  | ------ | ---------------------------- |
  | x/y    | 元素左上角和视口左上角的距离 |
  | bottom | 元素的下边距离视口上边的距离 |
  | top    | 元素的上边距离视口上边的距离 |
  | left   | 元素的左边距离视口左边的距离 |
  | right  | 元素的右边距离视口左边的距离 |
  | width  | 元素的实际宽度               |
  | height | 元素的实际高度               |

###### 滚动条位置

1. 对象.scrollTop：内部元素超出元素顶部的距离（获取有滚动体的元素滚动时垂直方向的距离）

2. 对象.scrollLeft：内部元素超出元素左侧的距离（获取有滚动体的元素滚动时水平方向的距离）

   ```js
   window.onscroll=function(){
       if(document.docunment.documentElement.scrollTop>100){
           document.querySelector(".box").style.top=0;
       }
   }
   ```

###### 元素的内尺寸

1. clientWidth/clientHeight：元素除去边框外的宽度/高度
2. clientTop/clientLeft：元素上边框和左边框的宽度

###### 页面的实际大小

1. document.documentElement.scrollWidth
2. document,documentElement.scrollHeight

###### 窗口左上角距离屏幕左上角的距离

1. window.screenX
2. window.screenY

###### 窗口的内宽、内高

1. window.innerWidth
2. window.innerHeight

###### 窗口的外宽、外高

1. window.outerWidth
2. window.outerHeight

### 节点

> 整个页面就是一个文档树

###### 节点分类

1. 元素节点 （html中的元素）
2. 属性节点 （html中的属性）
3. 文本节点 （html中的文本）
4. 注释节点 （html中的注释）
5. 文档节点 （DOM）

###### 节点的详细信息

 	通过节点的名称，类型，内容可以方便我们更好的去操作节点

| 节点     | 节点名称（nodeName） | 节点的类型（nodeType） | 节点内容（nodeValue） |
| -------- | -------------------- | ---------------------- | --------------------- |
| 元素节点 | 大写的标签名         | 1                      | null                  |
| 属性节点 | 属性名               | 2                      | 属性值                |
| 文本节点 | `#text`              | 3                      | 文本                  |
| 注释节点 | `#comment`           | 8                      | 注释的文本            |
| 文档节点 | `#document`          | 9                      | null                  |

###### 节点的属性

1. node.parentNode：获取父节点
2. node.childNodes：获取子节点（包括元素、文本、注释）
3. node.firstChild：第一个子节点
4. node.lastChild：最后一个子节点
5. node.nextSibling：下一个兄弟节点
6. node.previousSibling：上一个兄弟节点

> 获取元素节点的属性

1. element.parentElement：获取元素的父元素节点
2. parentNode.children：获取所有的子元素节点
3. parentNode.firstElementChild：获取第一个子元素节点
4. parentNode.lastElementChild：获取最后一个子元素节点
5. ele.nextElementSibling：获取下一个兄弟元素节点
6. ele.previousElementSibling：获取上一个兄弟元素节点
7. parentNode.childElementCount：获取子元素节点的数量

###### 节点的方法

1. 创建：
   创建元素节点：document.createElement("标签名")；
   创建文本节点：document.createTextNode();
2. 插入：
   给父元素的最后插入一个子节点：父节点.appendChild(子节点);
   在某一个节点的前面插入子节点：父节点.insertBefore(要插入的节点,被插入的节点);
3. 删除：父节点.removeChild(子节点);
4. 替换：父节点.replaceChild(新节点，旧节点)；
5. 克隆：节点.cloneNode()
   - true：克隆子节点
   - false:只克隆本节点，不克隆子节点

### 事件

> 能够被JS检测到的行为就叫做事件，比如鼠标的单击、双击、键盘按下等。

###### 事件三要素

- 事件源：触发事件的目标
- 事件：触发事件本身
- 事件处理程序：一般是一个函数，用于处理事件触发后的操作

###### 常见的事件

- 鼠标：click, dblclick, mouseenter, mouseleave, mousemove, mousedown, mouseup,mouseover,mouseout, contextmenu
- 键盘：keydown, keyup, keypress(按下，只有数字能触发)
- 表单：submit, input, change, reset, focus, blur
- window：scroll, resize, load

###### 添加事件的方式

1. 行内添加
2. DOM元素绑定（on+type)：事件源.事件=事件处理函数
3. 事件监听：给同一个事件源的同一个事件添加不同的事件处理函数
   - `addEventListener(type,fn,false)`
   - `removeEventListener(type,fn)`

#### 事件监听

> 给一个事件添加多个事件处理程序

###### 添加方式

​	`element.addEventListener(event,callback,bool);`
​	event：事件，要监听的事件，前面没有on
​	callback：回调函数，事件处理函数
​	boolean：true支持捕获型事件流，false支持冒泡型事件流，默认是false

###### 删除方式

​	`element.removeEventListener(event,callback,bool);`
​	event：事件，要监听的事件，前面没有on
​	callback：回调函数，事件处理函数(使用removeEventListener移除事件监听，事件处理函数必须是一个具名函数，不能使用匿	名函数)
​	boolean：true支持捕获型事件流，false支持冒泡型事件流，默认是false

#### 事件对象

> 记录事件发生时的详细信息。事件处理函数的第一个参数就是事件对象

###### 属性

- 鼠标
  - offsetX：点击的位置距事件源左上角水平方向的距离
  - offsetY：点击的位置距事件源左上角垂直方向的距离
- 键盘
  - key：按下的键
  - keyCode：按键所对应的ASCII码

###### 方法

- 阻止浏览器的默认行为 `e.preventDefault()`
- 阻止冒泡型事件流传播 `e.stopPropagation()`

#### 事件流

> 给页面添加事件时，其他元素发生的一系列事件

> 事件发生时会在事件元素和根节点之间以某种方式进行传递，在这个过程中经过的所有的节点都会接收这个事件，这就叫做DOM的事件流

###### 事件流的分类

1. 冒泡型事件流：从最明确的元素到最不明确的元素；
   - on+type
   - 事件监听：false
2. 捕获型事件流：从最不明确的元素到最明确的元素；
   - 事件监听：true

###### 阶段

1. 捕获阶段
2. 目标阶段
3. 冒泡阶段

#### 事件委派

> 当给多个元素添加同一个事件的时候，可以将事件添加给他们的父元素，根据事件对象的target属性来确定当前点击的是哪一个元素，来执行相应的代码。

> 原理：冒泡型事件流

`e.target`

```js
// 网页优化： 减少dom操作  、减少数据库操作 

document.querySelector("ul").onclick=function(e){
    let ele=e.target;
    ele.classList.add("box")
}
```
### 本地存储

- cookie

  > 最多能存储4KB,每一个web站点最多能存储20个
  > 保存时效：可以人为设置cookie的有效期，cookie的使用必须有服务器环境
  > 可以使用warmpserver去帮助我们搭建服务器

- localStorage：永久存储

  > 存储的数据很多，有5Mb到10Mb，并且只要我们不去删除那么存储下来的内容就会永久保存
- sessionStorage：一次会话

  > 会话型存储，当我们关闭浏览器以后，存储的内容就删除了
  > 常用于：
  > 1.登录状态
  > 2.具有时效性的网站
  > 3.搜索记录

###### 方法

- **[存]** 设置：
  - `localStorage.setItem("key","value")` 
  - `localStorage.key = "value"` 
- **[取]** 获取
  - `localStorage.getItem("key")` 
  - `localStorage.key` 
- **[删]** 删除
  - `localStorage.removeItem("key")`

###### 数据格式转换

> json 是一种数据交换的格式

- 将对象转为字符串：JSON.stringify( )
- 将字符串转为对象：JSON.parse( )



# 异步编程Ajax

### 什么是Ajax
>ajax是一种创建快速动态网页的技术

### ajax的特性
>异步：在发送请求的时候，用户可以在浏览器端做其他的操作，不会影响请求的进行

**发送或者接收数据的格式**

json,XML,HTML,或者文本

### ajax的作用
>唯一的功能：发送和接收数据

**根据ajax的特性做以下两部分事情**

1. 在不刷新整个页面的情况下请求数据
2. 接收并使用从服务器发送回来的数据

### ajax的工作原理
在客户端与服务器之间加了一个中间层（ajax引擎），使用户操作和服务器响应异步，不需要每一个请求都发送到服务器，就像数据验证和数据处理等都由ajax引擎完成，当确定需要从服务器获取数据的时候再由ajax引擎代为发送请求。

### ajax的使用方法
1. 实例化XMLHttpRequest()对象 
let xml =new XMLHttpRequest();

2. 使用open()方法设置请求信息

| 参数         | 作用                             |
| ------------ | -------------------------------- |
| request-type | 有get和post                      |
| url          | 发送请求的地址                   |
| asynch       | 是否使用异步                     |
| username     | 需要身份验证可以在这里设置用户名 |
| password     | 需要身份验证可以在这里设置密码   |

3. 使用send()方法发送请求

| 类型 | 特点                                                         |
| ---- | ------------------------------------------------------------ |
| get  | 如果不需要send传递参数，只需要传入null作为send的参数，其他的参数可以跟在url地址后面 |
| post | 必须先设置头信息，需要传递的参数放在send的参数中             |

```js
//get
xml.open(url+"?name=张三&age=20")
xml.send(null);

//post
xml.open(url);
xml.setRequestHeader("Content-Type","application/x-www-form-urlencoded"
);
xml.send("name=张三&age=20")
```

4. onreadystatechange 
当每一次请求状态发生改变的时候都会触发这个事件 
readystate的状态有五个  

| 状态码 | 状态                               |
| ------ | ---------------------------------- |
| 0      | 还没有调用send方法，发送前         |
| 1      | 调用send方法，发送中等待响应       |
| 2      | 响应成功                           |
| 3      | 解析响应中                         |
| 4      | 响应解析完成，可以在客户端使用数据 |

设置接收数据的格式，一般为json格式，如果没有这个数据，需要在接收到的数据中心使用JSON.parse()方法将返回来的数据字符串转为json格式。
xml.responseType="json"







# Css3新特性

- 2d：transfrom 
- 过渡：transition
- 弹性布局：display: flex
- 阴影：box-shadow
- 边框
- 渐变
- 动画
- 自定义字体  @font-face
- 新选择器   
- 媒体查询 ：@media 用一个页面相应不同的终端

# Html5新特性

- 语义化标签 
  header, nav, aside, section, footer

- 表单标签 
  日期：date, time,month,week,  颜色color,电话tel,邮箱email，数字number,滑块

- 本地存储  

- 音视频标签    

  ```js
  <video src="" controls></video>
  <audio src="" controls></audio>
  ```

- 画布


