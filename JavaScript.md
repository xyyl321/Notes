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

# ECMAScript



# BOM

# DOM





   



