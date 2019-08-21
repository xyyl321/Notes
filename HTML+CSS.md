#### 前端布局: html css

# 一、html: 超文本标记语言

###### html结构

```
<!DOCTYPE html>  document type html  
<html lang="en"> 网页根元素 
<head>           头部:网页配置信息
    <meta charset="UTF-8">    charset 文字编码 
    <meta name="viewport" content="width=device-width, initial-scale=1.0">       视口，略过
    <meta http-equiv="X-UA-Compatible" content="ie=edge"> 略过
    <title>Document</title>   标题
</head>
<body>          身体: 网页内容
    <div> </div>
</body>
</html>
```

###### 概述

**超文本**: img 超链接 video audio canvas(画板)
**标记**: , “” 《优逸客》
**标签**：

```
<div></div>
```

### 1、标签

**标签语法**：被<>所包裹的标签名，整体称之为标签。

###### 1-1 标签分类

(1) 按照语法分类:

- 单标签：只有开始标签
- 双标签：有开始标签也有结束标签。
- 开始标签 <标签名>
- 结束标签 </标签名>

*注意*：标签不能交叉嵌套,例如：

```
<body><div></body></div>
```

(2) 按照在页面中的呈现效果分类：

- 行内元素:在一行内显示不可以设置宽高

```
a   span    em  i   strong
```

- 块元素：可以设置宽高,独占一行(自动为列)

```
div p   pre h1  h6  body    html    ul li   ol li dl dt dd
```

- 行内块元素：在一行内显示，可以设置宽高 （一行中会有间隔）

```
img     表单控件
```

###### 1-2 标签转换

```
display:block;  转化为块元素
display:inline;  转化为行内元素
display：inline-block; 转化为行内块元素
```

###### 1-3 标签的嵌套规则

- 块元素：可嵌套块元素 行内块元素 行内元素
- 行内块元素：可嵌套行内块元素 行内元素
- 行内元素：可嵌套行内元素
  **注意**
  a链接不能嵌套a链接，也不能嵌套块元素，需要转换为块元素才可
  p不能嵌套p

###### 1-4 常用标签

### 2、属性

**属性位置**：开始标签内，标签名空格之后

###### 2-1 属性的语法

- 单个属性单个属性值： 属性名="属性值"

```
<div class="box"></div>
```

- 单个属性多个属性值: 属性名="属性值1 属性值2 属性值值3"

```
<div class="box1 box2 box3"></div>
```

- 多个属性: 多个属性之间要空格

```
<div class="box1 box2" style="width:200px;height:200px;"></div>     
```

### 3、文件路径

1. 绝对路径：基于根目录/盘符开始的路径（用的少 服务器配置时会用到）
2. 相对路径：用来描述两个文件之间的位置关系的路径

```
./ 当前目录 （可有可无）
../ 上一级目录
dir1/dir2/ 下一级
```

### 常用标签

```
<!-- 注释内容 -->
<!--link 引入样式表-->  
<link rel="stylesheet" href="">
```

###### 行内元素

```
<a href="">外链接</a>
<span>着重字体</span> 
<em>斜体</em>
<i>斜体</i>
<strong>粗体</strong>
<s>自带删除线</s>
```

###### 块元素

```
<div></div>
<h1>一级标题</h1>
<h2>二级标题</h2>
<h3>三级标题</h3>
<h4>四级标题</h4>
<h5>五级标题</h5>
<h6>六级标题</h6>
<!--无序列表-->
<ul>
    <li>第一天</li>
    <li>第二天</li>
    <li>第三天</li>
</ul>
<!--有序列表-->
<ol>
    <li>第一点</li>
    <li>第二点</li>
    <li>第三点</li>
</ol>
<!--项目列表-->
<dl>
    <dt>标题</dt>
    <dd>列表</dd>
    <dd>列表</dd>
</dl>
<!--段落标签-->
<p>文本段落</p>
<pre>文本段落</pre>
```

###### 行内块元素

**img**

```
<img src="" alt="" title='' width='' height=''>
src 图片路径
title 图片标题，图片提示
alt 图片提示(出错情况下)
width 不需要写单位
height   (图片必须设置宽高)
```

**table 表格**
标签: table tr th td
属性:

```
border   width   height   bgcolor='red'
cellspacing 空隙   cellpadding 内填充
align valign 
rowspan 竖跨几行colspan 横跨几列
<table border='1' cellspacing="0" cellpadding='0' bgcolor='red'>
    <!-- 表头 -->
     <tr bgcolor='blue'>
        <th width='100' height='30' valign='bottom' rowspan="2">姓名</th>
        <th>性别</th>
        <th>年龄</th>
    </tr>
    <tr>
        <td>小白</td>
        <td>男</td>
        <!-- <td>18</td> -->
    </tr>
    <tr>
        <td>小白</td>
        <td>男</td>
        <td>18</td>
    </tr>
</table>
```

**iframe 内联框架**

```
<a href="https://www.baidu.com" target="iframe">百度</a>
<iframe src="" frameborder="0" name='iframe'></iframe>
```

**表单控件**

```
表单属性: 
    action 提交数据的地址
    method: 表单提交方式 get post
表单控件属性:
    type 表单控件类型
    name: 数据的键 比如 username password
    value: 数据的值 
    disabled 不可用
    readonly 只读
    required 必填
常用的表单控件:
    text 文本框
    file 文件框
    password 密码框
    submit 相当于 <button></button> 表单提交按钮
    button 按钮,默认不会提交表单
    radio 单选按钮
    checkbox 复选框
    textarea 文本域
    select 下拉框
html5:
    日期:
        date
        time
        month
        week
    颜色
    电话 tel
    邮箱 email
    数字 number
    滑块
<input type="text" name="username2">
<form action="asdf.asdf" method="post">
    <input type="text" name="username" value=''>
    <input type="password" name="password" value='123456'>
    <!-- 输入框 -->
    <button>提交</button>
    <input type="button"> 
    男  <input type="radio" name="sex"> 
    女  <input type="radio" name="sex">
    <input type="checkbox" name="hippy" value='0'> 编程
    <input type="checkbox" name="hippy" value='1'> 游泳
    <textarea name="" id="" cols="30" rows="10"></textarea>
        
    <select name="" id="">
        <option value="0">杭州</option>
        <option value="1" selected>上海</option>
    </select>
    <br> <!-- br 换行 -->
    <input type="date">
    <input type="time">
    <input type="month">
    <input type="week">

    <input type="color">
    <input type="tel">
    <input type="email">
    <br>
    <input type="number" min="0" max='10' step="2">
    <input type="range" min="0" max='10' step="2">
</form>
```

修改默认提示效果

```
<input type="text" placehoder="默认内容">
/* 修改默认提示效果 */
input::-webkit-input-placehoder{
    color:red;    
}
```

获取焦点（适用于表单中）

```
input:focus{
    outline:none;
}
```

### 多媒体标签（H5新标签）

视频

```
<video src="" controls></video>
```

音频

```
<audio src="" controls></audio>
```

src 引入内容的地址
controls 显示控件，比如播放按钮
autoplay

### 多媒体标签（H5新增）

1. 为什么使用？

> 可以更好的理解网页的框架。

1. header(头部)、nav(导航栏)、aside(侧边栏)、section(一部分)、footer(底部)

## icon图标的使用

（1）在阿里巴巴矢量图标库中找到对应的icon图标
（2）点击添加购物车——>加入到项目中（如果没有 新建项目）——>在我的项目中选择font class，点击生成在线的CSS地址——>在html页面中通过link标签引入（加https:）——>在页面需要引入图标的位置通过i标签使用
（3）在线地址要时刻更新

```
<link     https://...>
<i class="iconfont icon-gouwuchekong">
</i>
```

### 标题前面加logo

在head标签中

```
<link rel="shortcut icon" href="favicon.ico" type="image/x-icon">
```

href 引入图标的地址
图片大小设为16*16

# 二、css: 层叠样式表

### 1、常用样式（总结）

### 2、常用选择器(10)

1. 标签选择器
   作用：选择页面中所有***的标签

```
/* 语法 */
标签名{
    样式名1:样式值1;
    样式名2:样式值2;
    ...
}
/* 举例 */
div{
    width:200px;
    height:200px;
    background-color:yellow;
}
```

1. 通用选择器
   作用：选择页面中所有的标签，常用来做默认样式清除

```
/* 语法 */
*{
    样式名1:样式值1;
    样式名2:样式值2;
    ...
}
/* 举例 */
*{
    margin:0;  /* 外间距 */
    padding:0;  /* 内填充 */
    list-style:none;   /* 列表样式 */
}
```

1. 类名选择器
   作用：通过类名选择页面中所有匹配的标签

```
/* 语法 */
.类名{
    样式名1:样式值1;
    ...
}
```

1. ID选择器
   作用：通过ID选择页面中匹配的标签

```
/* 语法 */
#ID名{
    样式名1:样式值1;
    ...
}
```

1. 后代选择器
   作用：选择后代元素

```
/* 语法 */
父元素选择器 后代元素选择器{
    样式名1:样式值1;
    ...
}
```

1. 子类选择器
   作用：选择后代元素

```
/* 语法 */
父元素选择器>子元素选择器{
    ...
}
```

1. 群组选择器
   作用：选择匹配的所有标签

```
div,p,h1,.box,#id{
    ...
}
```

1. 交叉选择器
   作用：选择匹配的所有标签

```
div.box{
    ...
}
```

1. 属性选择器
   作用：通过属性进行匹配标签

```
/* attribute属性 */
[属性名]{
    ...
}
[属性名=属性值]{
    ...
}
```

1. 伪类选择器

```
/* 选择元素的状态，鼠标移入的状态 */
:hover{      
    ...
}
```

伪类选择器：操作的是真实的DOM元素和用户交互

```
.box:nth-child(2) 父元素的所有子元素中，类名为box的并且为第二个的，否则失败
:first-child(第一个)
：last-child(最后一个)
:nth-last-child() 倒数第几个

.box:nth-of-type(2) 类名为box的元素，视其他元素而不见，在类名为box的元素中找到第二个元素添加样式
:first-of-type  这种类型的第一个
:last-of-type 这种类型的最后一个
:hover 鼠标移入
:focus 获取焦点
```

1. 伪元素选择器 伪元素选择器：操作的是页面中非真实的DOM元素。有标签的是真实的DOM.没有标签的是非真实的

```
::first-letter 选中第一字母
::first-line  选中第一行文本

在div中(可以解决浮动的bug)
::before 插入到元素内部，作为第一个元素出现
::after 插入到元素内部，作为最后一个元素出现  

.box::before{
    content:"";
    display:block;
}
.box::after{
    content:"";
    display:block;
}
```

### 3、选择器的优先级

- 宗旨：越具体优先级越高，相同优先级，后定义的样式会覆盖之前定义的样式
- 简单计算：ID(100)>class(10)>tab(1)

### 4、选择样式的几种方法

（1）行内样式： 行内样式的优先级最高

```
<div style="width:200px;height:200px;background-color:red;">
```

（2）外链接 外部式

```
<link rel="stylesheet" href="">
```

（3）嵌入式

```
<style>  
    *{
        ...
    }
    .box{
        background:#fff;
    }
    ...
</style>
```

（4）导入式 @import

```
@import "day.css";  
```

优先级

1. 行内样式优先级最高
2. 其他的样式表，优先级一样，按照导入的顺序来确定他们是否起作用。

# 常用样式

```
width:200px;    /* 宽度 */
height:200px;   /* 高度 */
background-color:red;    /* 背景颜色 */
border:1px solid red;   /* 边框粗细 实线 颜色 */
margin:0 auto;    /* 让块元素在父元素中居中 */
overflow:hidden;   /* 超出部分隐藏 */
cursor:pointer;   /* 手势 */
outline:0;
text-indent:1em; /* 缩进一个字符 */
```

###### a链接

```
a{
    text-decoration:none;  /* 去掉下划线 */
}
```

###### 字体

所有的字体样式可以被继承 但继承过来的优先级低

```
font  /*设置字体*/
color  /* 字体颜色*/
font-size:20px;  /*字体大小*/
line-height:90px;     /*字体在行高内垂直居中*/
text-align:center;  /*文本水平居中*/
```

###### margin外间距

```
margin:10px;  上右下左
margin:10px 20px;  上下10  左右20
margin:10px 20px 30px;  上10 左右20  下30
margin:10px 20px 30px 40px;  上 右 下 左
margin-top:10px;
margin-right:20px;
margin-bottom:30px;
margin-left:40px;
```

###### padding内间距

同margin

##### width height

```
width:数值;
width:父元素的百分比;
width:auto;  参照于父元素

height：数值；
height：父元素的百分比；
height：auto；由内容撑开，参照与子元素。内容有多高，高度就有多高。
```

auto！=100%
auto 可能比100%小 要看margin padding border的值
100% 内容宽度值width

###### box-sizing:border-box;

```
width 内容的宽度
box-sizing:border-box;  width:200px;  实际宽度
```

###### background 背景图

```
图片与背景图：背景图是个样式  图片是个元素
            页面中经常需要换的图用图片；   作为样式的  用背景图 
background-image:url("相对路径")；  背景图

background-size:100px 100px;  会重复 平铺
background-size:100px；如果只设置一个宽 则高按比例缩放；
background-size:auto 100px；只设置高
background-size:百分比；
background-size:cover; 覆盖  放大到正好把盒子给覆盖住 等比例放大的  可能会超出
background-size:contain;  保证图形是完整的 而且保证尽可能大

background-repeat:no-repeat;  一般设为不重复 （默认为repeat）
background-repeat:repeat;  重复 平铺
background-repeat:repeat-x; 横向重复排列
background-repeat:repeat-y; 


background-position:100px 0;  背景图的定位 两个参数 x轴 和 y轴（具体值  方位值top left bottom right center可省略）
        
background-color:center;
        
 background-origin:;  背景图开始的位置
                border-box;
                padding-box; 默认
                content-box;
background-clip:; 背景图被裁剪的位置
                border-box;
                padding-box; 默认
                content-box;
background-attachment
```

### 渐变

##### 1、分类

- 线性渐变（linear gradients） 向下/向上/向左/向右/对角方向
- 径向渐变（radial gradients）由他们的中心定义

##### 2、浏览器内核

```
-webkit- 谷歌
-moz-   火狐
-ms-    ie
-o- 欧鹏
```

##### 3、线性渐变

- 简单线性渐变
- 简单渐变，方向从上到下

```
.box{
    background:-webkit-linear-gradient(red,blue);  /*谷歌兼容*/
    background:-o-linear-gradient(red,blue);/*欧鹏兼容**/
    background:-moz-linear-gradient(red,blue);/*火狐*/
    background:linear-gradient(red,blue)；/*标准语法，需要兼容，不写方向，默认从上到下渐变*/
}
```

- 简单方向渐变

```
.box{
    background:-webkit-linear-gradient(left top,red,blue);  /*谷歌兼容*/
    background:-o-linear-gradient(to right,red,blue);/*欧鹏兼容**/
    background:-moz-linear-gradient(30deg,red,blue);/*火狐*/
    background:linear-gradient(red,blue)；/*标准语法，需要兼容，不写方向，默认从上到下渐变*/
}
```

第一个参数：渐变开始的方向
关键字：left right top bottom //to right to left...//to right=left
角度：30deg
第二个参数：渐变开始的颜色
关键字、十六进制、rgb、 rgba

- 不均匀的线性渐变

```
background:内核+linear-gradient(left,red 10%,yellow,green 20%);  
background:linear-gradient(left,red 10%,yellow,green 20%); 
  
background:linear-gradient(left,red 5rem,yellow,green);  
```

可以使用百分比或者像素值

- 重复性的线性渐变

```
background:内核+repeating-linear-gradient(45deg,red,yellow,green 20%);  
background:repeating-linear-gradient(45deg,red,yellow,green 20%); 
```

##### 4、径向渐变

- 简单的径向渐变

```
background:内核+radial-gradient(red,blue);
```

- 不均匀的径向渐变

```
background:内核+radial-gradient(red 10%,blue 20%,yellow);  
```

- 重复性的径向渐变

```
background:内核+repeating-radial-gradient(red,blue,pink 50%);
```

###### 颜色的表示方式

```
1. 预定义：red  green black
2. 十六进制： #000  #333  #D02D53
3. rgb
    红色  rgb(255,0,0)
    白色 rgb(255,255,255)  
    黑色 rgb(0,0,0)
    rgba(255,0,0,0.2)  不透明度0到1 （0为不透明）
    rgba(0-255,0-255,0-255,0-1)
```

###### rgba和opacity的区别

> rgba只作用与背景颜色，其他内容不会透明
> opacity作用在全部地方，其它内容也会变透明

###### 文字颜色渐变

把文本内容之外的背景给裁剪掉（谷歌）

```
.div{
    background-color:linear-gradient(to right,red,blue);   
    background-color:-webkit-linear-gradient(to right,red,blue);   //将背景设为渐变，注意兼容
    -webkit-background-clip:text;  //规定背景的绘制区域
    color:transparent;  将文字设为透明
}
```

**注意**clip写在background属性下面才会显示作用，运行从上到下，

## 2D动画效果

###### 鼠标移入：平移

```
:hover{
    transform:translateX(100px);   水平移动  正右 负左
    transform:translateY(100px);  垂直移动  正下 负上
    transition:1s;    过度时间
    transform:translate(100px,100px); 两参数x轴和y轴
    transform:translate(100px);  x轴
}
```

###### 鼠标移入：旋转

```
:hover{
    transform:rotate(90deg);  正顺时针  负逆时针  角度无限制
    
}
```

###### 鼠标移入：缩放

```
:hover{
    transform:scaleX(2);  x轴放大2倍  大于1的放大 小于1的缩小 
    transform:scaleX(-1);  x轴翻转
    transform:scale(2,2); 两参数x轴和y轴
}
```

###### 鼠标移入：斜切

```
:hover{
    transform:skewX(45deg);  x轴
    transform:skewY(45deg);  y轴 
    transform:skewY(30deg,30deg); 
}
```

###### 阴影

```
box-shadow:10px 0 15px 15px #333;   x  y  模糊程度值越大越模糊  阴影的大小值越大阴影越大
box-shadow:10px 0 15px 15px #333 inset; 内阴影
```

### 单行文本溢出

```
white-space:nowrap;   限制换行
overflow:hidden;    超出隐藏
text-overflow:ellispsis;  将超出的文本内容显示为圆点
```

### 多行文本溢出

```
display:-webkit-box;   定义为盒子显示
-webkit-box-orient:vertical;  定义框内子元素的排列方式为垂直排列
-webkit-line-clamp:2;  限制一个块元素显示的文本行数
overflow:hidden;    超出隐藏
text-overflow:ellispsis;  将超出的文本内容显示为圆点
```

### 文本域

```
textarea{
    resize:none;  禁止调整
    resize:both;  默认的
    resize:vertical;  垂直方向调整
    resize:horizontal; 水平方向调整
}
```

### display

display:none;隐藏
display:block;显示

### overflow

overflow:hidden;超出隐藏
overflow:auto;超出内容会出现滚动条，否则不会
overflow:scroll;始终出现滚动条

```
选择器::-webkit-scrollbar{
    width:0; height:0;
    或者  display:none;    
}
```

# 三、布局方式

### 1、浮动

浮动的作用：解决块元素的横排排列的问题。
**整个页面分为两层：文档层 浮动层**

###### 1-1 文档流

文档的排列方式: 从左向右 从上到下。

###### 1-2 浮动原理

浮动的元素，脱离了文档流，从文档层浮动到了浮动层。

###### 1-3 浮动引发的问题

浮动的子元素撑不开父元素。（父元素在文档层 子元素在浮动层）
解决方式一：设置父元素的高度。
解决方式二：给父元素设置overflow：hidden；（超出部分隐藏）
解决方式三：在父元素内容最后添加一个拥有清除浮动样式的子元素。

```
clear:both;  /*  left  right*/
```

解决方式四：创建伪元素清除浮动样式

```
.box::after{
    content:"";
    display:block;
    clear:both;
}
```

不解决的后果：会出现行的重叠。

###### 1-4 浮动卡住问题

不断测试 从

### 2、盒子模型

###### 2-1 构成部分(四部分)

margin
border
padding
content(width*height)

###### 2-2 盒子的宽高

盒子的实际宽度：border-left + padding-left + width + padding-right + border-right

###### 2-3 margin外间距

```
margin:10px;  上右下左
margin:10px 20px;  上下10  左右20
margin:10px 20px 30px;  上10 左右20  下30
margin:10px 20px 30px 40px;  上 右 下 左
margin-top:10px;
margin-right:20px;
margin-bottom:30px;
margin-left:40px;
```

###### 2-4 padding内间距

同margin

###### 2-5 width height

```
width:数值;
width:父元素的百分比;
width:auto;  参照于父元素

height：数值；
height：父元素的百分比；
height：auto；由内容撑开，参照与子元素。内容有多高，高度就有多高。
```

auto！=100%
auto 可能比100%小 要看margin padding border的值
100% 内容宽度值width

###### 2-6 box-sizing:border-box;

```
width 内容的宽度
box-sizing:border-box;  width:200px;  实际宽度
```

###### 2-7 盒子模型所引发的问题

1. 大部分元素的margin值和padding值都为0，但部分元素的padding值和margin值不为0
   eg:body
2. margin值可以为负数，但padding值不可以。
3. 相邻的两个块元素的margin值可以重合。值会取最大值
4. 行内元素的margin值只有左右没有上下。padding值是有的
5. 发生嵌套关系的两个元素，如果父元素没有上边框，上padding,父元素和子元素之间没有别的内容，此时 子元素的marging-top会加到父元素身上。
   解决办法：破坏任意一个条件
   子元素没有浮动

> 1.给父元素加上边框
> border-top:1px solid transparent; 透明
> 2.给父元素加上padding
> padding-top:100px;
> (盒子的实际高度会+100) 解决办法：box-sizing:border-box;
> 3.父元素中加 overflow：hidden;
> 4.两个元素之间可以加一个内容：比如 加一个空格 `&nbsp;`

### 3、定位

图片，内容等重叠在一起情况下，使用定位

###### 3-1 常用的定位

相对定位
绝对定位
固定定位

###### 3-2 定位特点

```
1. 相对定位 position:relative;    
    特点：相对于自身定位，保留原来的位置。
2. 绝对定位 position:absolute;
    特点：相对于最近的、定位的、祖先元素来定位，完全脱离文档流。  
（根据绝对定位的特点，在用绝对定位的时候要结合祖先元素的相对定位。而此时相对定位的保留原来的位置的特点就很重要！）
3. 固定定位 position:fixed; 
    特点：相对于浏览器定位，完全脱离文档流
4. 定位元素：脱离文档流，并且多出四个样式：top:; right;: bottom;: left:;
```

###### 3-3 定位元素的居中方式

方式一：

```
position:absolute;
left:50%;    /* 参照与父元素 */
margin-left:-自身宽度的一半;
top:50%;  
margin-top:-自身高度的一半;


position：absolute;
left:50%;
top:50%;
transform:translate(-50%,-50%);
```

方式二：

```
top:0;    /* top权重高 */
bottom:0;   /* left权重高 */
left:0;   
right:0;    
margin:auto;  /* 只写margin:auto; 不执行 */ 
```

### 4、层级

- 定位的元素会脱离文档层到定位层。
- 同一层级的元素，后面的元素高于前面的元素。
- 调整层级：z-index:; 大于0的数值 （没单位） z是z轴

### 5、响应式布局

媒体查询

```
@media screen and (min-width:1200px){
    .box{
        background-color:red;
    }
}
@media screen and (max-width:1200px){
    .box{
        background-color:salmon;
    }
}
@media screen and (max-width:800px){
    .box{
        background-color:darkcyan;
    }
}
```

十二栅格

```
<ul>
    <li class="col-lg-1 col-md-3 col-sm-4 col-xs-12" >1</li>
    <li class="col-lg-1 col-md-3 col-sm-4 col-xs-12" >2</li>
    <li class="col-lg-1 col-md-3 col-sm-4 col-xs-12" >3</li>
    <li class="col-lg-1 col-md-3 col-sm-4 col-xs-12" >4</li>
     <li class="col-lg-1 col-md-3 col-sm-4 col-xs-12" >5</li>
     <li class="col-lg-1 col-md-3 col-sm-4 col-xs-12" >6</li>
    <li class="col-lg-1 col-md-3 col-sm-4 col-xs-12" >7</li>
    <li class="col-lg-1 col-md-3 col-sm-4 col-xs-12" >8</li>
    <li class="col-lg-1 col-md-3 col-sm-4 col-xs-12" >9</li>
    <li class="col-lg-1 col-md-3 col-sm-4 col-xs-12" >10</li>
    <li class="col-lg-1 col-md-3 col-sm-4 col-xs-12" >11</li>
    <li class="col-lg-1 col-md-3 col-sm-4 col-xs-12" >12</li>
</ul>
/* lg md sm xs */
@media screen and (min-width: 1200px){
    .col-lg-12{ width: 100% }
    .col-lg-11{ width: 91.667% }
    .col-lg-10{ width: 83.333% }
    .col-lg-9{ width: 75% }
    .col-lg-8{ width: 66.667% }
    .col-lg-7{ width: 58.333% }
    .col-lg-6{ width: 50% }
    .col-lg-5{ width: 41.667% }
    .col-lg-4{ width: 33.333% }
    .col-lg-3{ width: 25% }
    .col-lg-2{ width: 16.667% }
    .col-lg-1{ width: 8.333% }
}
@media screen and (max-width: 1200px){
    .col-md-12{ width: 100% }
    .col-md-11{ width: 91.667% }
    .col-md-10{ width: 83.333% }
    .col-md-9{ width: 75% }
    .col-md-8{ width: 66.667% }
    .col-md-7{ width: 58.333% }
    .col-md-6{ width: 50% }
    .col-md-5{ width: 41.667% }
    .col-md-4{ width: 33.333% }
    .col-md-3{ width: 25% }
    .col-md-2{ width: 16.667% }
    .col-md-1{ width: 8.333% }
}
@media screen and (max-width: 992px){
    .col-sm-12{ width: 100% }
    .col-sm-11{ width: 91.667% }
    .col-sm-10{ width: 83.333% }
    .col-sm-9{ width: 75% }
    .col-sm-8{ width: 66.667% }
    .col-sm-7{ width: 58.333% }
    .col-sm-6{ width: 50% }
    .col-sm-5{ width: 41.667% }
    .col-sm-4{ width: 33.333% }
    .col-sm-3{ width: 25% }
    .col-sm-2{ width: 16.667% }
    .col-sm-1{ width: 8.333% }
}
@media screen and (max-width: 768px){
    .col-xs-12{ width: 100% }
    .col-xs-11{ width: 91.667% }
    .col-xs-10{ width: 83.333% }
    .col-xs-9{ width: 75% }
    .col-xs-8{ width: 66.667% }
    .col-xs-7{ width: 58.333% }
    .col-xs-6{ width: 50% }
    .col-xs-5{ width: 41.667% }
    .col-xs-4{ width: 33.333% }
    .col-xs-3{ width: 25% }
    .col-xs-2{ width: 16.667% }
    .col-xs-1{ width: 8.333% }
}
```

## 移动端布局前期工作

##### 1、添加修改视口

```
<meta name="viewport" content="width=device-width, user-scalable=no, initial-scale=1.0, maximum-scale=1.0, minimum-scale=1.0">
```

user-scalable=no 禁止用户调整窗口大小
initial-scale=1.0 窗口的初始缩放比例比例为1
maximum-scale=1.0 最大的调整比例为1
minimum-scale=1.0 最小的调整比例为1

##### 2、兼容不同的屏幕大小（响应式布局）

```
html{
    font-size:100px;  设计稿在750px下的
}
@media screen and (min-width:320px){
    html{
        font-size:42.6667px;
    }
}
@media screen and (min-width:360px){
    html{
        font-size:48px;
    }
}
@media screen and (min-width:375px){
    html{
        font-size:50px;
    }
}
@media screen and (min-width:411px){
    html{
        font-size:54.8px;
    }
}
@media screen and (min-width:414px){
    html{
        font-size:55.2px;
    }
}
.box{
    width:5rem;
    height:5rem;
}
```

**注意**
使用min-width时，屏幕尺寸从小往大排；使用max-widt时，屏幕从大往下排；

##### 3、单位介绍

（1）文本相对长度
em 相对于父元素文本字体大小
rem是相对于根元素html

```
1em=1*font-size(父元素)  
1rem=1*font-size(根元素) 
```

（2）视口相对长度
vw 相对于视口的宽度。视口被均分为100单位的vw
vh 相对于视口的高度。视口被均分为100单位的vh

##### 4、引入

1. 引入rem.css
2. 根元素中在lang="en"后面加一个rem="750"

### 响应式布局

媒体查询

```
@media screen and (min-width:1200px){
    .box{
        background-color:red;
    }
}
@media screen and (max-width:1200px){
    .box{
        background-color:salmon;
    }
}
@media screen and (max-width:800px){
    .box{
        background-color:darkcyan;
    }
}
```

十二栅格

```
<ul>
    <li class="col-lg-1 col-md-3 col-sm-4 col-xs-12" >1</li>
    <li class="col-lg-1 col-md-3 col-sm-4 col-xs-12" >2</li>
    <li class="col-lg-1 col-md-3 col-sm-4 col-xs-12" >3</li>
    <li class="col-lg-1 col-md-3 col-sm-4 col-xs-12" >4</li>
     <li class="col-lg-1 col-md-3 col-sm-4 col-xs-12" >5</li>
     <li class="col-lg-1 col-md-3 col-sm-4 col-xs-12" >6</li>
    <li class="col-lg-1 col-md-3 col-sm-4 col-xs-12" >7</li>
    <li class="col-lg-1 col-md-3 col-sm-4 col-xs-12" >8</li>
    <li class="col-lg-1 col-md-3 col-sm-4 col-xs-12" >9</li>
    <li class="col-lg-1 col-md-3 col-sm-4 col-xs-12" >10</li>
    <li class="col-lg-1 col-md-3 col-sm-4 col-xs-12" >11</li>
    <li class="col-lg-1 col-md-3 col-sm-4 col-xs-12" >12</li>
</ul>
/* lg md sm xs */
@media screen and (min-width: 1200px){
    .col-lg-12{ width: 100% }
    .col-lg-11{ width: 91.667% }
    .col-lg-10{ width: 83.333% }
    .col-lg-9{ width: 75% }
    .col-lg-8{ width: 66.667% }
    .col-lg-7{ width: 58.333% }
    .col-lg-6{ width: 50% }
    .col-lg-5{ width: 41.667% }
    .col-lg-4{ width: 33.333% }
    .col-lg-3{ width: 25% }
    .col-lg-2{ width: 16.667% }
    .col-lg-1{ width: 8.333% }
}
@media screen and (max-width: 1200px){
    .col-md-12{ width: 100% }
    .col-md-11{ width: 91.667% }
    .col-md-10{ width: 83.333% }
    .col-md-9{ width: 75% }
    .col-md-8{ width: 66.667% }
    .col-md-7{ width: 58.333% }
    .col-md-6{ width: 50% }
    .col-md-5{ width: 41.667% }
    .col-md-4{ width: 33.333% }
    .col-md-3{ width: 25% }
    .col-md-2{ width: 16.667% }
    .col-md-1{ width: 8.333% }
}
@media screen and (max-width: 992px){
    .col-sm-12{ width: 100% }
    .col-sm-11{ width: 91.667% }
    .col-sm-10{ width: 83.333% }
    .col-sm-9{ width: 75% }
    .col-sm-8{ width: 66.667% }
    .col-sm-7{ width: 58.333% }
    .col-sm-6{ width: 50% }
    .col-sm-5{ width: 41.667% }
    .col-sm-4{ width: 33.333% }
    .col-sm-3{ width: 25% }
    .col-sm-2{ width: 16.667% }
    .col-sm-1{ width: 8.333% }
}
@media screen and (max-width: 768px){
    .col-xs-12{ width: 100% }
    .col-xs-11{ width: 91.667% }
    .col-xs-10{ width: 83.333% }
    .col-xs-9{ width: 75% }
    .col-xs-8{ width: 66.667% }
    .col-xs-7{ width: 58.333% }
    .col-xs-6{ width: 50% }
    .col-xs-5{ width: 41.667% }
    .col-xs-4{ width: 33.333% }
    .col-xs-3{ width: 25% }
    .col-xs-2{ width: 16.667% }
    .col-xs-1{ width: 8.333% }
}
```

## 弹性布局

##### 1、概念

- 容器：父元素
- 项目：子元素
- 两根轴：主轴=>默认水平方向     交叉轴=>默认垂直方向

##### 2、容器（写在父元素身上）的属性

- flex-direction:确定主轴的方向
  - row(默认值):主轴为水平方向，从左往右
  - row-reverse:主轴在水平方向，从右往左
  - column:主轴为垂直方向，从上到下
  - column-reverse:主轴为垂直方向，从下到上
- flex-wrap:子元素的换行
  - wrap:换行，从上到下
  - nowrap:不换行（默认）
  - wrap-reverse:换行，从下到上
- justify-content:子元素在主轴方向的对齐方式
  - flex-start:主轴的起点
  - center主轴的中点
  - flex-end:主轴的终点
  - space-between:两端对齐，子元素之间的间隔都相等
  - space-around:每个子元素左右两边的距离相等
- align-items:子元素在交叉轴方向的对齐方式（适用于一根轴线和多根轴线）
  - flex-start:交叉轴的起点
  - flex-end:交叉轴的终点
  - center：交叉轴的中点
- align-content:子元素在交叉轴方向的对齐方式（适用于多根轴线）
  - flex-start:交叉轴的起点
  - flex-end:交叉轴的终点
  - center：交叉轴的中点
  - space-between:两端对齐
  - space-around:每个项目右两侧的距离相等

##### 3、项目（写在子元素身上）的属性

以下6个属性设置在项目上。

- order：定义项目的排列顺序。数值越小，排列越靠前，默认为0。

```
.item {
  order: <integer>;
}
```

- flex-grow:定义项目的放大比例，默认为0，即如果存在剩余空间，也不放大。

```
.item {
  flex-grow: <number>; /* default 0 */
}
```

> 如果所有项目的flex-grow属性都为1，则它们将等分剩余空间（如果有的话）。如果一个项目的flex-grow属性为2，其他项目都为1，则前者占据的剩余空间将比其他项多一倍。

- flex-shrink:定义了项目的缩小比例，默认为1，即如果空间不足，该项目将缩小。

```
.item {
  flex-shrink: <number>; /* default 1 */
}
```

> 如果所有项目的flex-shrink属性都为1，当空间不足时，都将等比例缩小。如果一个项目的flex-shrink属性为0，其他项目都为1，则空间不足时，前者不缩小。 负值对该属性无效。

- flex-basis:定义了在分配多余空间之前，项目占据的主轴空间（main size）。浏览器根据这个属性，计算主轴是否有多余空间。它的默认值为auto，即项目的本来大小。

```
.item {
  flex-basis: <length> | auto; /* default auto */
}
```

> 它可以设为跟width或height属性一样的值（比如350px），则项目将占据固定空间。

- flex:属性是flex-grow, flex-shrink 和 flex-basis的简写，默认值为0 1 auto。后两个属性可选。

```
.item {
  flex: none | [ <'flex-grow'> <'flex-shrink'>? || <'flex-basis'> ]
}
```

> 该属性有两个快捷值：auto (1 1 auto) 和 none (0 0 auto)。
> 建议优先使用这个属性，而不是单独写三个分离的属性，因为浏览器会推算相关值。

- align-self:

