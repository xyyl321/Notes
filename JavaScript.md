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

### DOM 获取元素的方法

| 方法                                  | 描述                                                   |
| ------------------------------------- | ------------------------------------------------------ |
| document.write()                      | 在页面中写入内容（识别标签）                           |
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

- localStorage：永久存储
- sessionStorage：一次会话

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

##### Css3新特性

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

##### Html5新特性

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





















































