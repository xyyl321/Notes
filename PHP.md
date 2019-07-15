# PHP

>  PHP 是一种创建动态交互性站点的强有力的服务器端脚本语言。
>
> PHP 脚本在服务器上执行。

**wamp:**

> windows, apache, mysql, php 集成开发环境

**lamp:**

> linux, apache, mysql, php 集成开发环境

## PHP 能够做什么？

- PHP 能够生成动态页面内容
- PHP 能够创建、打开、读取、写入、删除以及关闭服务器上的文件
- PHP 能够接收表单数据
- PHP 能够发送并取回 cookies
- PHP 能够添加、删除、修改数据库中的数据
- PHP 能够限制用户访问网站中的某些页面
- PHP 能够对数据进行加密

# PHP基础

## PHP 语法

> PHP 脚本可放置于文档中的任何位置。

```php
<?php
// 此处是 PHP 代码
?>
```

### 大小写敏感

- 在 PHP 中，所有用户定义的函数、类和关键词（例如 if、else、echo 等等）都对大小写不敏感。 
- 不过在 PHP 中，所有变量都对大小写敏感。

### 注释

- 单行注释 `//`
- 单行注释 `#`
- 多行注释 `/*  */`



## PHP 变量

### PHP 变量作用域

- local（局部）

- global（全局）

  - PHP  global 关键词
  - global 关键词用于在函数内访问全局变量。 

- static（静态）

  - PHP static 关键词

  - 通常，当函数完成/执行后，会删除所有变量。不过，有时我需要不删除某个局部变量。实现这一点需要更进一步的工作。

    要完成这一点，请在您首次声明变量时使用 *static* 关键词：

```php
function myTest() {
    static $x=0;
    echo $x;
    $x++;
  }
  
myTest();
myTest();
myTest();
```

### Local 和 Global 作用域

- 函数*之外*声明的变量拥有 Global 作用域，只能在函数以外进行访问。
- 函数*内部*声明的变量拥有 LOCAL 作用域，只能在函数内部进行访问。



## PHP 常量

常量是一个简单值的标识符。该值在脚本中不能改变。

**注意：** 常量在整个脚本中都可以使用。

```js
define ( string $name , mixed $value [, bool $case_insensitive = false ] )
```

该函数有三个参数:

- **name：**必选参数，常量名称，即标志符。
- **value：**必选参数，常量的值。
- **case_insensitive** ：可选参数，如果设置为 TRUE，该常量则大小写不敏感。默认是大小写敏感的。



## PHP数据类型

String(字符串)、Integer(整型)、Float(浮点型)、Boolean(布尔型)、Array(数组)、Object(对象)、NULL(空值)



## PHP 字符串

### 1. strlen()函数

> 返回字符串的长度，以字符计。 

```php
echo strlen("Hello world!");   // 12
```

### 2. strpos()函数

> 在字符串内查找一个字符或一段指定的文本
>
> 如果在字符串中找到匹配，该函数会返回第一个匹配的字符位置。如果未找到匹配，则返回 FALSE。

```php
echo strpos("Hello world!","world");  //6
```

### 3. str_replace() 函数 

> 用一些字符串替换字符串中的另一些字符  

```php
echo str_replace("world", "Kitty", "Hello world!"); // Hello Kitty!
```

### 4. str_word_count()函数

> 对字符串中的单词进行计数

```php
echo str_word_count("Hello world!"); // 2
```

### 5. strrev() 函数

> 反转字符串

```php
echo strrev("Hello world!"); // !dlrow olleH
```



## PHP 数组

### 在 PHP 中创建数组  

> 在 PHP 中，array() 函数用于创建数组：

```php
array();
```

> **数组能够在单独的变量名中存储一个或多个值。** 

### 数组类型

1. 索引数组(数值数组)： 带有数字索引的数组

   - 创建方式一：索引是自动分配的（索引从 0 开始）

     ```php
     $cars=array("porsche","BMW","Volvo");
     ```

   - 创建方式二：手动分配索引

     ```php
     $cars[0]="porsche";
     $cars[1]="BMW";
     $cars[2]="Volvo";
     ```

2. 关联数组 ：带有指定键的数组

   - 创建方式一：

     ```php
     $age=array("Bill"=>"35","Steve"=>"37","Elon"=>"43");
     ```

   - 创建方式二：

     ```php
     $age['Bill']="63";
     $age['Steve']="56";
     $age['Elon']="47";
     ```

3. 多维数组 ：包含一个或多个数组的数组

- 获得数组的长度：count()函数

```php
$cars=array("porsche","BMW","Volvo");
echo count($cars);//3
```



## PHP 数组排序

###  数组的排序函数

1. **sort()** - 以升序对数组排序

```php
$numbers=array(3,5,1,22,11);
sort($numbers);
```

2. **rsort()** - 以降序对数组排序

```php
$numbers=array(4,6,2,22,11);
rsort($numbers);
```

3. **asort()** - 根据值，以升序对关联数组进行排序

```
$age=array("Peter"=>"35","Ben"=>"37","Joe"=>"43");
asort($age);
```

4. **ksort()** - 根据键，以升序对关联数组进行排序

```php
$age=array("Peter"=>"35","Ben"=>"37","Joe"=>"43");
ksort($age);
```

5. **arsort()** - 根据值，以降序对关联数组进行排序

```php
$age=array("Peter"=>"35","Ben"=>"37","Joe"=>"43");
arsort($age);
```

6. **krsort()** - 根据键，以降序对关联数组进行排序

```php
$age=array("Peter"=>"35","Ben"=>"37","Joe"=>"43");
krsort($age);
```



# PHP表单

## PHP表单处理

> PHP 中的 `$_GET` 和 `$_POST` 变量用于检索表单中的信息，比如用户输入。
>
> PHP 超全局变量 `$_GET` 和 `$_POST` 用于收集表单数据（form-data）。 

### GET vs. POST

- GET 和 POST 都创建数组（例如，array( key => value, key2 => value2, key3 => value3, ...)）。此数组包含键/值对，其中的键是表单控件的名称，而值是来自用户的输入数据。 
- GET 和 POST 被视作 $_GET 和 $_POST。它们是超全局变量，这意味着对它们的访问无需考虑作用域 - 无需任何特殊代码，您能够从任何函数、类或文件访问它们。 
- $_GET 是通过 URL 参数传递到当前脚本的变量数组。 
- $_POST 是通过 HTTP POST 传递到当前脚本的变量数组。 

### 何时使用GET?

- 通过 GET 方法从表单发送的信息*对任何人都是可见的*（所有变量名和值都显示在 URL 中）。GET 对所发送信息的数量也有限制。限制在大约 2000 个字符。不过，由于变量显示在 URL 中，把页面添加到书签中也更为方便。 
- GET 可用于发送非敏感的数据 

**注释**：绝不能使用 GET 来发送密码或其他敏感信息！ 

### 何时使用 POST？

- 1、通过 POST 方法从表单发送的信息*对其他人是不可见的*（所有名称/值会被嵌入 HTTP 请求的主体中），并且对所发送信息的数量也*无限制* 。
- 2、此外 POST 支持高阶功能，比如在向服务器上传文件时进行 multi-part 二进制输入 。
- 3、不过，由于变量未显示在 URL 中，也就无法将页面添加到书签。 



## PHP表单验证

### 文本字段

name、email 和 website 属于文本输入元素，comment 字段是文本框。HTML 代码是这样的：

```html
Name: <input type="text" name="name">
E-mail: <input type="text" name="email">
Website: <input type="text" name="website">
Comment: <textarea name="comment" rows="5" cols="40"></textarea>
```

### 单选按钮

gender 字段是单选按钮，HTML 代码是这样的：

```html
Gender:
<input type="radio" name="gender" value="female">Female
<input type="radio" name="gender" value="male">Male
```

### 表单元素

表单的 HTML 代码是这样的：

```html
<form method="post" action="<?php echo htmlspecialchars($_SERVER["PHP_SELF"]);?>">
```

当提交此表单时，通过 method="post" 发送表单数据。

**什么是 $_SERVER["PHP_SELF"] 变量？**

$_SERVER["PHP_SELF"] 是一种超全局变量，它返回当前执行脚本的文件名。

因此，$_SERVER["PHP_SELF"] 将表单数据发送到页面本身，而不是跳转到另一张页面。这样，用户就能够在表单页面获得错误提示信息。

**什么是 htmlspecialchars() 函数？**

htmlspecialchars() 函数把特殊字符转换为 HTML 实体。这意味着 < 和 > 之类的 HTML 字符会被替换为 &lt; 和 &gt; 。这样可防止攻击者通过在表单中注入 HTML 或 JavaScript 代码（跨站点脚本攻击）对代码进行利用。

**如何避免 $_SERVER["PHP_SELF"] 被利用？**

- 通过使用 **htmlspecialchars() **函数能够避免 $_SERVER["PHP_SELF"] 被利用。 

- ```php
  <form method="post" action="<?php echo htmlspecialchars($_SERVER["PHP_SELF"]);?>">
  ```

- **htmlspecialchars()** 函数把特殊字符转换为 HTML 实体。现在，如果用户试图利用 PHP_SELF 变量，会导致如下输出： 

- ```php
  <form method="post" action="test_form.php/&quot;&gt;&lt;script&gt;alert('hacked')&lt;/script&gt;">
  ```



## PHP表单必填

```php
<?php
// 定义变量并设置为空值
$nameErr = $emailErr = $genderErr = $websiteErr = "";
$name = $email = $gender = $comment = $website = "";

if ($_SERVER["REQUEST_METHOD"] == "POST") {
  if (empty($_POST["name"])) {
    $nameErr = "Name is required";
  } else {
    $name = test_input($_POST["name"]);
  }

  if (empty($_POST["email"])) {
    $emailErr = "Email is required";
  } else {
    $email = test_input($_POST["email"]);
  }

  if (empty($_POST["website"])) {
    $website = "";
  } else {
    $website = test_input($_POST["website"]);
  }

  if (empty($_POST["comment"])) {
    $comment = "";
  } else {
    $comment = test_input($_POST["comment"]);
  }

  if (empty($_POST["gender"])) {
    $genderErr = "Gender is required";
  } else {
    $gender = test_input($_POST["gender"]);
  }
}
?>
```



## PHP表单  URL/E-mail

### 验证名称

以下代码将通过简单的方式来检测 name 字段是否包含字母和空格，如果 name 字段值不合法，将输出错误信息

```php
$name = test_input($_POST["name"]);
if (!preg_match("/^[a-zA-Z ]*$/",$name)) {
  $nameErr = "只允许字母和空格"; 
}
```

### 验证邮件

以下代码将通过简单的方式来检测 e-mail 地址是否合法。如果 e-mail 地址不合法，将输出错误信息

```php
$email = test_input($_POST["email"]);
if (!preg_match("/([\w\-]+\@[\w\-]+\.[\w\-]+)/",$email)) {
  $emailErr = "非法邮箱格式"; 
}
```

### 验证 URL

以下代码将检测URL地址是否合法 (以下正则表达式运行URL中含有破折号:"-")， 如果 URL 地址不合法，将输出错误信息：

```php
$website = test_input($_POST["website"]);
if (!preg_match("/\b(?:(?:https?|ftp):\/\/|www\.)[-a-z0-9+&@#\/%?=~_|!:,.;]*[-a-z0-9+&@#\/%=~_|]/i",$website)) {
  $websiteErr = "非法的 URL 的地址"; 
}
```



# PHP高级教程

> 文件，文件上传，cookie，session，JSON

## 文件

### 打开文件

fopen() 函数用于在 PHP 中打开文件。

此函数的第一个参数含有要打开的文件的名称，第二个参数规定了使用哪种模式来打开文件：

```PHP
$file=fopen("welcome.txt","r");
```

文件可能通过下列模式来打开：

| 模式 | 描述                                                         |
| :--- | :----------------------------------------------------------- |
| r    | 只读。在文件的开头开始。                                     |
| r+   | 读/写。在文件的开头开始。                                    |
| w    | 只写。打开并清空文件的内容；如果文件不存在，则创建新文件。   |
| w+   | 读/写。打开并清空文件的内容；如果文件不存在，则创建新文件。  |
| a    | 追加。打开并向文件末尾进行写操作，如果文件不存在，则创建新文件。 |
| a+   | 读/追加。通过向文件末尾写内容，来保持文件内容。              |
| x    | 只写。创建新文件。如果文件已存在，则返回 FALSE 和一个错误。  |
| x+   | 读/写。创建新文件。如果文件已存在，则返回 FALSE 和一个错误。 |

**注释：**如果 fopen() 函数无法打开指定文件，则返回 0 (false)。


### 关闭文件

fclose() 函数用于关闭打开的文件：

```php
fclose($file);
```


### 检测文件末尾（EOF）

feof() 函数检测是否已到达文件末尾（EOF）。

在循环遍历未知长度的数据时，feof() 函数很有用。

**注释：**在 w 、a 和 x 模式下，您无法读取打开的文件！

```php
if (feof($file)) echo "文件结尾";
```

### 逐行读取文件

fgets() 函数用于从文件中逐行读取文件。

**注释：**在调用该函数之后，文件指针会移动到下一行。

下面的实例逐行读取文件，直到文件末尾为止：

```php
file = fopen("welcome.txt", "r") or exit("无法打开文件!");
// 读取文件每一行，直到文件结尾
while(!feof(file))
{
    echo fgets(file). "<br>";
}
fclose(file);
```

### 逐字符读取文件

fgetc() 函数用于从文件中逐字符地读取文件。

**注释：**在调用该函数之后，文件指针会移动到下一个字符。

下面的实例逐字符地读取文件，直到文件末尾为止：

```php
$file=fopen("welcome.txt","r") or exit("无法打开文件!");
while (!feof(file))
{
    echo fgetc(file);
}
fclose(file);
```



## 文件上传

https://www.runoob.com/php/php-file-upload.html



## cookie

### cookie定义

> cookie 常用于识别用户。cookie 是一种服务器留在用户计算机上的小文件。每当同一台计算机通过浏览器请求页面时，这台计算机将会发送 cookie。通过 PHP，您能够创建并取回 cookie 的值。

### 创建 Cookie

**setcookie() 函数用于设置 cookie。**
**注释：setcookie()函数必须位于<"html">标签之前。**

### 语法

```
setcookie(name, value, expire(到期), path(路径), domain(域));
```

```
实例 1
在下面的例子中，我们将创建名为 "user" 的 cookie，并为它赋值 "runoob"。我们也规定了此 cookie 在一小时后过期：

<?php
setcookie("user", "runoob", time()+3600);
?>

<html>
.....
注释：在发送 cookie 时，cookie 的值会自动进行 URL 编码，在取回时进行自动解码。（为防止 URL 编码，请使用 setrawcookie() 取而代之。）


实例 2
您还可以通过另一种方式设置 cookie 的过期时间。这也许比使用秒表示的方式简单。

<?php
$expire=time()+60*60*24*30;
setcookie("user", "runoob", $expire);
?>

<html>
.....
在上面的实例中，过期时间被设置为一个月（60 秒 * 60 分 * 24 小时 * 30 天）。
```

### 如何取回 Cookie 的值？

> PHP  的 **$_COOKIE** 变量用于取回 cookie 的值。    

```
在下面的实例中，我们使用 isset() 函数来确认是否已设置了 cookie：

<html>
<head>
<meta charset="utf-8">
<title>菜鸟教程(runoob.com)</title>
</head>
<body>

<?php
if (isset($_COOKIE["user"]))
    echo "欢迎 " . $_COOKIE["user"] . "!<br>";
else
    echo "普通访客!<br>";
?>

</body>
</html>
```

### 删除 Cookie

> 当删除 cookie 时，您应当使过期日期变更为过去的时间点。

```
<?php
// 设置 cookie 过期时间为过去 1 小时
setcookie("user", "", time()-3600);
?>
```

**如果浏览器不支持使用cookie，可用通过表单传递数据的方式进行识别用户**



## session

### 定义

PHP session 变量用于存储关于用户会话（session）的信息，或者更改用户会话（session）的设置。Session 变量存储单一用户的信息，并且对于应用程序中的所有页面都是可用的。

### PHP Session 变量   

> 定义：您在计算机上操作某个应用程序时，您打开它，做些更改，然后关闭它。这很像一次对话（Session）。计算机知道您是谁。它清楚您在何时打开和关闭应用程序。然而，在因特网上问题出现了：由于 HTTP 地址无法保持状态，Web 服务器并不知道您是谁以及您做了什么。 

> PHP session 解决了这个问题，它通过在服务器上存储用户信息以便随后使用（比如用户名称、购买商品等）。然而，会话信息是临时的，在用户离开网站后将被删除。如果您需要永久存储信息，可以把数据存储在数据库中。  

> Session 的工作机制是：为每个访客创建一个唯一的 id (UID)，并基于这个 UID 来存储变量。UID 存储在 cookie 中，或者通过 URL 进行传导。   

### 开始 PHP Session

- 首先在把用户信息存储到PHP session中之前，首先必须启动对话。
- 注释:session_start()函数必须位于<html>标签之前：

```
<?php session_start(); ?>
 
<html>
<body>
 
</body>
</html>
上面的代码会向服务器注册用户的会话，以便您可以开始保存用户信息，同时会为用户会话分配一个 UID。
```

### 存储session 变量   

> 存储和取回session变量的正确方法是使用PHP$_SESSION变量：

```
<?php
session_start();
// 存储 session 数据
$_SESSION['views']=1;
?>
 
<html>
<head>
<meta charset="utf-8">
<title>菜鸟教程(runoob.com)</title>
</head>
<body>
 
<?php
// 检索 session 数据
echo "浏览量：". $_SESSION['views'];//1
?>
 
</body>
</html>
```

### 销毁 Session

**销毁Session使用的函数**

1. 通过unset()进行销毁

```
<?php
session_start();
if(isset($_SESSION['views']))
{
    unset($_SESSION['views']);
}
?>
```

2. session_destory(销毁)()函数

```
<?php
session_destroy();
?>
```

**注释：session_destroy() 将重置 session，您将失去所有已存储的 session 数据。**

### 实例笔记

关于验证登陆用户是否有 admin(管理员) 权限的例子

```
<?php
//  表单提交后...
$posts = $_POST;
//  清除一些空白符号
foreach ($posts as $key => $value) {
    $posts[$key] = trim($value);
}
$password = md5($posts["password"]);
$username = $posts["username"]; 

$query = "SELECT `username` FROM `user` WHERE `password` = '$password' AND `username` = '$username'";
//  取得查询结果
$userInfo = $DB->getRow($query); 

if (!empty($userInfo)) {
    //  当验证通过后，启动 Se
index.html

> 验证 session里的`admin`是否为 `true`

<?php
//  防止全局变量造成安全隐患
$admin = false;
//  启动会话，这步必不可少
session_start();
//  判断是否登陆
if (isset($_SESSION["admin"]) && $_SESSION["admin"] === true) {
    echo "您已经成功登陆";
} else {
    //  验证失败，将 $_SESSION["admin"] 置为 false
    $_SESSION["admin"] = false;
    die("您无权访问");
}
?>

```



## JSON

### JSON函数

|      函数       |                   描述                    |
| :-------------: | :---------------------------------------: |
|   json_encode   |            对变量进行JSON编码             |
|   json_decode   | 对JSON格式的字符串进行解码，转换为PHP变量 |
| json_last_error |            返回最后发送的错误             |

#### 1. json_encode()

> 定义：PHP json_encode() 用于对变量进行 JSON 编码，该函数如果执行成功返回 JSON 数据，否则返回 FALSE 。

- 语法：

```
string json_encode ( $value [, $options = 0 ] )
```

- 参数：value: 要编码的值。该函数只对 UTF-8 编码的数据有效。
- - options:由以下常量组成的二进制掩码：JSON_HEX_QUOT, JSON_HEX_TAG, JSON_HEX_AMP, JSON_HEX_APOS, JSON_NUMERIC_CHECK,JSON_PRETTY_PRINT, JSON_UNESCAPED_SLASHES, JSON_FORCE_OBJECT

```
实例
以下实例演示了如何将 PHP 数组转换为 JSON 格式数据：

<?php
   $arr = array('a' => 1, 'b' => 2, 'c' => 3, 'd' => 4, 'e' => 5);
   echo json_encode($arr);
?>
以上代码执行结果为：

{"a":1,"b":2,"c":3,"d":4,"e":5}

以下实例演示了如何将 PHP 对象转换为 JSON 格式数据：

<?php
   class Emp {
       public $name = "";
       public $hobbies  = "";
       public $birthdate = "";
   }
   $e = new Emp();
   $e->name = "sachin";
   $e->hobbies  = "sports";
   $e->birthdate = date('m/d/Y h:i:s a', "8/5/1974 12:20:03 p");
   $e->birthdate = date('m/d/Y h:i:s a', strtotime("8/5/1974 12:20:03"));

   echo json_encode($e);
?>
以上代码执行结果为：

{"name":"sachin","hobbies":"sports","birthdate":"08\/05\/1974 12:20:03 pm"}
```

#### 2. json_decode

> 定义：PHP json_decode()函数用于对JSON格式的字符串进行编码，并转换为PHP变量    

- 语法：

```
mixed json_decode ($json_string [,$assoc = false [, $depth = 512 [, $options = 0 ]]])
```

- 参数：
- json_string: 待解码的 JSON 字符串，必须是 UTF-8 编码数据
- assoc: 当该参数为 TRUE 时，将返回数组，FALSE 时返回对象。
- depth: 整数类型的参数，它指定递归深度
- options: 二进制掩码，目前只支持 JSON_BIGINT_AS_STRING 。

```
实例
以下实例演示了如何解码 JSON 数据：
<?php
   $json = '{"a":1,"b":2,"c":3,"d":4,"e":5}';

   var_dump(json_decode($json));
   var_dump(json_decode($json, true));
?>
以上代码执行结果为：

object(stdClass)#1 (5) {
    ["a"] => int(1)
    ["b"] => int(2)
    ["c"] => int(3)
    ["d"] => int(4)
    ["e"] => int(5)
}

array(5) {
    ["a"] => int(1)
    ["b"] => int(2)
    ["c"] => int(3)
    ["d"] => int(4)
    ["e"] => int(5)
}
```



# PHP数据库







# PHP AJAX 基础

## Ajax简介

> 定义：AJAX 是一种在无需重新加载整个网页的情况下，能够更新部分网页的技术。

#### Ajax基于因特网标准

AJAX 基于因特网标准，并使用以下技术组合：

- XMLHttpRequest 对象（与服务器异步交互数据）
- JavaScript/DOM（显示/取回信息）
- CSS（设置数据的样式）
- XML（常用作数据传输的格式）



# PHP HTTP

> 定义：HTTP 函数允许您在其他输出被发送之前，对由 Web 服务器发送到浏览器的信息进行操作。  

|      函数      |                     描述                     |
| :------------: | :------------------------------------------: |
|    header()    |          向客户端发送原始的HTTP报头          |
| headers_list() | 返回已发送的（或待发送的）响应头部的一个列表 |
| headers_sent() |      检查HTTP报头是否发送/已发送到何处       |
|  setcookie()   |         向客户端发送一个HTTP cookie          |
| setrawcookie() | 不对cookie值进行URL编码，发送一个HTTP cookie |

### 1. header()函数        

- 语法

```
header(string,replace,http_response_code)
```

|        参数        |                             描述                             |
| :----------------: | :----------------------------------------------------------: |
|       string       |                 必需，规定要发送的报头字符串                 |
|      replace       | 可选，指示该报头是否替换之前的报头。或添加第二个报头。默认是 TRUE（替换）。FALSE（允许相同类型的多个报头） |
| http_response_code |             可选。把HTTP响应代码强制为指定的值。             |

### 2. headers_list()

> 定义：headers_list() 函数返回已发送的（或待发送的）响应头部的一个列表。
> 该函数返回包含报头的数组。

- 语法

```
headers_list()
```

- 提示：如需确定是否已发送报头，请使用 headers_sent() 函数。

### 3. headers_sent() 函数

- 定义：headers_sent() 函数检查 HTTP 报头是否发送/已发送到何处。
  如果报头已发送，该函数返回 TRUE，否则返回 FALSE     
- 语法

```
headers_sent(file,line)
参数：file，line。可选。如果设置 file 和 line 参数，headers_sent() 会把输出开始的 PHP 源文件名和行号存入 file 和 line 变量中。
```

### 4. setcookie() 函数

- 定义和用法：setcookie() 函数向客户端发送一个 HTTP cookie。
- 1、cookie 是由服务器发送到浏览器的变量。cookie 通常是服务器嵌入到用户计算机中的小文本文件。每当同一台计算机通过浏览器请求页面时，就会发送这个 cookie。
- 2、cookie 的名称自动指定为相同名称的变量。例如，如果被发送的 cookie 名为 "user"，则会自动创建一个名为 $user 的变量，包含 cookie 的值。
- 3、必须在任何其他输出发送到客户端前对 cookie 进行赋值。
- 4、如果成功，该函数返回 TRUE。如果失败则返回 FALSE。      
- 语法

```
setcookie(name,value,expire,path,domain,secure)
```

|  参数  |                             描述                             |
| :----: | :----------------------------------------------------------: |
|  name  |                    必需，规定cookie的名称                    |
| value  |                     必需，规定cookie的值                     |
| expire | 可选。规定cookie的过期时间，time()+3600*24*30 将设置 cookie 的过期时间为 30 天。如果这个参数没有设置，那么 cookie 将在 session 结束后（即浏览器关闭时）自动失效。 |
|  path  |                 可选。规定cookie的服务器路径                 |
| domain |                    可选。规定cookie的名称                    |
| secure |      可选。规定是否需要在安全的HTTPS连接来传输cookie。       |

##### 提示和注释

- 提示：可以通过 **$HTTP_COOKIE_VARS["user"]** 或 **$_COOKIE["user"]** 来访问名为 "user" 的 cookie 的值。
- 注释：在发送 cookie 时，cookie 的值会自动进行 URL 编码。接收时会自动进行 URL 解码。如果您不需要这样，可以使用 **setrawcookie()** 

```
实例1
设置并发送 cookie：
<?php
$value = "my cookie value";

// send a cookie that expires in 24 hours
setcookie("TestCookie",$value, time()+3600*24);
?>

<html>
<body>

...
...

实例2
检索 cookie 值的不同方法（在 cookie 设置之后）：
<html>
<body>

<?php
// Print individual cookies
echo $_COOKIE["TestCookie"];
echo "<br />";
echo $HTTP_COOKIE_VARS["TestCookie"];
echo "<br />";

// Print all cookies
print_r($_COOKIE);
?>

</body>
</html>
上面的代码将输出：

my cookie value
my cookie value
Array ([TestCookie] => my cookie value)
实例 3
通过把失效日期设置为过去的日期/时间，删除一个 cookie：

<?php
// Set the expiration date to one hour ago
setcookie ("TestCookie", "", time() - 3600);
?>

<html>
<body>

...
...

创建一个数组 cookie：

<?php
setcookie("cookie[three]","cookiethree");
setcookie("cookie[two]","cookietwo");
setcookie("cookie[one]","cookieone");

// print cookies (after reloading page)
if (isset($_COOKIE["cookie"]))
{
foreach ($_COOKIE["cookie"] as $name => $value)
{
echo "$name : $value <br />";
}
}
?>

<html>
<body>

...
...
上面的代码将输出：

three : cookiethree
two : cookietwo
one : cookieone
```

### 5. setrawcookie() 函数

> 定义：setrawcookie() 函数不对 cookie 值进行 URL 编码，发送一个 HTTP cookie。其他与setcookie()函数用法一致

##### 提示和注释

- 提示：同setcookie()函数
- 注释：setrawcookie() 函数与 setcookie()  函数几乎完全相同，不同的是不会在发往客户端时，对 cookie 值进行自动 URL 编码。



# PHP MAYSQLI

### PHP MySQLi 简介

PHP MySQLi = PHP MySQL Improved!

MySQLi 函数允许您访问 MySQL 数据库服务器。      

### 1. mysqli_affected_rows() 函数

> 定义和用法：mysqli_affected_rows() 函数返回前一次 MySQL 操作（SELECT、INSERT、UPDATE、REPLACE、DELETE）所影响的记录行数。

- 语法

```
mysqli_affected_rows(connection);
```

- 参数：connection(连接)，必需。规定要使用的 MySQL 连接。       
  返回值：一个 > 0 的整数表示所影响的记录行数。0 表示没有受影响的记录。-1 表示查询返回错误。

### 2. mysqli_autocommit() 函数

> 定义和用法：mysqli_autocommit() 函数开启或关闭自动提交数据库修改。

- 语法

```
mysqli_autocommit(connection,mode);

```

- 参数1：connection：必需。规定要使用的 MySQL 连接。
- 参数2：mode：必需。如果设置为 FALSE，则表示关闭 auto-commit。如果设置为 TRUE，则表示开启 auto-commit（提交任何等待查询）。
- 返回值：	如果成功则返回 TRUE，如果失败则返回 FALSE。

### 3. mysqli_change_user() 函数*

> 定义和用法：mysqli_change_user() 函数改变指定数据库连接的用户，并设置当前数据库。

- 语法：

```
mysqli_change_user(connection,username,password,dbname);
```

- 参数1：connection	必需。规定要使用的 MySQL 连接。
- 参数2：username	必需。规定 MySQL 用户名。
- 参数3：password	必需。规定 MySQL 密码。
- 参数4：dbname	必需。规定要改变的新数据库。
- 返回值：	如果成功则返回 TRUE，如果失败则返回 FALSE。

### 4. mysqli_character_set_name() 函数

> 定义和用法：mysqli_character_set_name() 函数返回数据库连接的默认字符集。

### 5. mysqli_close() 函数

> 定义和用法：mysqli_close() 函数关闭先前打开的数据库连接。

### 6. mysqli_commit()函数

> 定义和用法：mysqli_commit() 函数提交指定数据库连接的当前事务。

- 提示：请查看 **mysqli_autocommit()** 函数，用于开启或关闭自动提交数据库修改。请查看 **mysqli_rollback()** 函数，用于回滚当前事务。

### 7. mysqli_connect_errno() 函数

> 定义和用法：函数返回上一次连接错误的错误代码。

### 8. mysqli_connect_error() 函数

> 定义和用法：函数返回上一次连接错误的错误描述。

### 9. mysqli_connect() 函数

> 定义和用法：函数打开一个到 MySQL 服务器的新的连接

### 10. mysqli_data_seek() 函数

> 定义和用法：mysqli_data_seek() 函数调整结果指针到结果集中的一个任意行。

- 语法：

```
mysqli_data_seek(result,offset);
```

- 参数：result	必需。规定由 mysqli_query()、mysqli_store_result() 或 mysqli_use_result() 返回的结果集标识符。
- 参数2：必需。规定字段偏移。范围必须在 0 和 行总数 - 1 之间。

### 11. mysqli_debug() 函数

> 定义和用法：mysqli_debug() 函数用于执行调试操作。

```
在本地机上的 "/temp/client.trace" 中创建一个 trace 文件：

<?php
mysqli_debug("d:t:o,/temp/client.trace");
?>
```

### 12. mysqli_dump_debug_info() 函数

> 定义和用法:mysqli_dump_debug_info() 函数转储调试信息到日志中.

### 13. mysqli_errno() 函数

> 定义和用法:mysqli_errno() 函数返回最近调用函数的最后一个错误代码。

### 14. mysqli_fetch_all() 函数

> 定义和用法:mysqli_fetch_all() 函数从结果集中取得所有行作为关联数组，或数字数组，或二者兼有。

|             函数              |                             描述                             |
| :---------------------------: | :----------------------------------------------------------: |
|      mysqli_error_list()      |                 返回最近调用函数的错误列表。                 |
|        mysqli_error()         |             返回最近调用函数的最后一个错误描述。             |
|      mysqli_fetch_all()       |  从结果集中取得所有行作为关联数组，或数字数组，或二者兼有。  |
|     mysqli_fetch_array()      |   从结果集中取得一行作为关联数组，或数字数组，或二者兼有。   |
|     mysqli_fetch_assoc()      |               从结果集中取得一行作为关联数组。               |
|  mysqli_fetch_field_direct()  |   从结果集中取得某个单一字段的 meta-data，并作为对象返回。   |
|     mysqli_fetch_field()      |           从结果集中取得下一字段，并作为对象返回。           |
|     mysqli_fetch_fields()     |               返回结果中代表字段的对象的数组。               |
|    mysqli_fetch_lengths()     |              返回结果集中当前行的每个列的长度。              |
|     mysqli_fetch_object()     |             从结果集中取得当前行并作为对象返回。             |
|      mysqli_fetch_row()       |           从结果集中取得一行，并作为枚举数组返回。           |
|     mysqli_field_count()      |                      返回最近查询的列数                      |
|      mysqli_field_seek()      |               把字段指针设置为指定字段的偏移量               |
|      mysqli_field_tell()      |                  返回结果集中的指针的位置。                  |
|     mysqli_free_result()      |                        释放结果内存。                        |
|     mysqli_get_charset()      |                        返回字符集对象                        |
|   mysqli_get_client_info()    |                 函数返回 MySQL 客户端库版本                  |
|   mysqli_get_client_stats()   |                 返回有关客户端每个进程的统计                 |
|  mysqli_get_client_version()  |              将 MySQL 客户端库版本作为整数返回               |
| mysqli_get_connection_stats() |                   返回有关客户端连接的统计                   |
|    mysqli_get_host_info()     |              返回 MySQL 服务器主机名和连接类型               |
|    mysqli_get_proto_info()    |                    返回 MySQL 协议版本。                     |
|   mysqli_get_server_info()    |                   返回 MySQL 服务器版本。                    |
|  mysqli_get_server_version()  |               将 MySQL 服务器版本作为整数返回                |
|         mysqli_info()         |                  返回有关最近执行查询的信息                  |
|         mysqli_init()         |   初始化 MySQLi 并返回 mysqli_real_connect() 使用的对象。    |
|      mysqli_insert_id()       | 返回最后一个查询中自动生成的 ID（通过 AUTO_INCREMENT 生成）。 |
|         mysqli_kill()         | mysqli_kill() 函数请求服务器杀死一个由 processid 参数指定的 MySQL 线程。 |
|     mysqli_more_results()     |                检查一个多查询是否有更多的结果                |
|     mysqli_multi_query()      |    执行一个或多个针对数据库的查询。多个查询用分号进行分隔    |
|     mysqli_next_result()      |           为 mysqli_multi_query() 准备下一个结果集           |
|      mysqli_num_fields()      |                 返回结果集中字段（列）的数量                 |
|       mysqli_options()        |            设置额外的连接选项，用于影响连接行为。            |
|         mysqli_ping()         |       进行一个服务器连接，如果连接已断开则尝试重新连接       |
|        mysqli_query()         |                   执行某个针对数据库的查询                   |
|     mysqli_real_connect()     |               打开一个到 MySQL 服务器的新连接                |
|  mysqli_real_escape_string()  |          转义在 SQL 语句中使用的字符串中的特殊字符           |
|       mysqli_refresh()        |             刷新表或缓存，或者重置复制服务器信息             |
|       mysqli_rollback()       |                   回滚数据库中的当前事务。                   |
|      mysqli_select_db()       |                   用于更改连接的默认数据库                   |
|     mysqli_set_charset()      |     规定当与数据库服务器进行数据传送时要使用的默认字符集     |
|       mysqli_sqlstate()       |             返回最后一个错误的 SQLSTATE 错误代码             |
|       mysqli_ssl_set()        | 用于创建 SSL 安全连接。然而，该函数只有在启用 OpenSSL 支持时才有效 |
|         mysqli_stat()         |                       返回当前系统状态                       |
|      mysqli_stmt_init()       |      初始化声明并返回 mysqli_stmt_prepare() 使用的对象.      |
|      mysqli_thread_id()       | 返回当前连接的线程 ID，然后使用 mysqli_kill() 函数杀死该连接 |
|     mysqli_thread_safe()      |             返回是否将客户端库编译成 thread-safe             |



# PHP RESTful

> REST（英文：Representational State Transfer，简称REST) ，指的是一组架构约束条件和原则。