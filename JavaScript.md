# JavaScript

##### JS的作用

1. 嵌入动态文本于网页中
2. 对浏览器事件做出响应    （用户的动作，行为   比如：点击、触摸、滑动）
3. 读写html元素
4. 在数据提交到服务器之前验证服务器     （注册、登录）
5. 控制cookie，包括创建和修改
6. 基于Node.js技术进行服务器端编程

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
2. BOM浏览器对象模型：可以对浏览器窗口进行访问和操作。
3. DOM文档对象模型：通过创建树来表示文档，从而使开发者对文档的内容和结构具有控制力。用DOM API可以轻松操作文档。

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

### 运算符

### 控制流程

### 数组

### 函数



# BOM

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

### DOM的方法

| 方法                                  | 描述                                                   |
| ------------------------------------- | ------------------------------------------------------ |
| document.write()                      | 在页面中写入内容（识别标签）                           |
| document.getElementsByTagName(标签名) | 根据标签名获取html中的元素                             |
| document.getElementsByClassName(类名) | 根据类名获取html中的元素                               |
| document.getElementById(id名)         | 根据id名获取html中的元素                               |
| document.getElementsByName(name)      | 通过name属性获取html元素，返回值是一个NodeList节点属性 |
| document.querySelectorAll(css选择器)  | 通过css选择器获取html元素（结果是一个节点集合）        |
| document.querySelector(css选择器)     | 通过css选择器获取html元素（结果是单一的元素节点）      |



   



