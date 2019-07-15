# PHP 数据库

## 连接 MySQL

### 连接 MySQL

> 在我们访问 MySQL 数据库前，我们需要先连接到数据库服务器： 

```php
实例 (MySQLi - 面向对象)
<?php
$servername = "localhost";
$username = "username";
$password = "password";
 
// 创建连接
$conn = new mysqli($servername, $username, $password,'数据库的表单名');
 
// 检测连接
if ($conn->connect_error) {
    die("连接失败: " . $conn->connect_error);
} 
echo "连接成功";
?>
```
### 关闭连接
```
实例 (MySQLi - 面向对象)
$conn->close();
```



## 创建数据库

数据库存有一个或多个表。你需要CREATE 权限来创建或产出MySQL数据库

使用MySQL和PDO创建MySQL数据库

- create database语句用于在MySQL中创建数据库。



## 插入数据

在创建完数据库和表后，我们可以向表中添加数据。

以下为一些语法规则：

- PHP 中 SQL 查询语句必须使用引号
- 在 SQL 查询语句中的字符串值必须加引号
- 数值的值不需要引号
- NULL 值不需要引号     
**insert into**语言通常用于向MySQL表添加新的记录
```
INSERT INTO table_name (column1, column2, column3,...)
VALUES (value1, value2, value3,...)
```
 ```php
<?php
$servername = "localhost";
$username = "username";
$password = "password";
$dbname = "myDB";
 
// 创建连接
$conn = new mysqli($servername, $username, $password, $dbname);
// 检测连接
if ($conn->connect_error) {
    die("连接失败: " . $conn->connect_error);
} 
 
$sql = "INSERT INTO MyGuests (firstname, lastname, email)
VALUES ('John', 'Doe', 'john@example.com')";
 
if ($conn->query($sql) === TRUE) {
    echo "新记录插入成功";
} else {
    echo "Error: " . $sql . "<br>" . $conn->error;
}
 
$conn->close();
?>
 ```
### 插入多条数据   

使用 MySQLi 和 PDO 向 MySQL 插入多条数据

>mysqli_multi_query()函数可用来执行多条SQL语句。



### 预处理语句及绑定参数   
- 预处理语句的工作原理如下：
- 1、预处理：创建SQL语句模板并发送到数据库，预处理的值使用参数“？”标记，例如：
```
INSERT INTO MyGuests (firstname, lastname, email) VALUES(?, ?, ?)
```
**MySQL预处理语句**

```
以下实例在 MySQLi 中使用了预处理语句，并绑定了相应的参数:

实例 (MySQLi 使用预处理语句)
<?php
$servername = "localhost";
$username = "username";
$password = "password";
$dbname = "myDB";
 
// 创建连接
$conn = new mysqli($servername, $username, $password, $dbname);
 
// 检测连接
if ($conn->connect_error) {
    die("连接失败: " . $conn->connect_error);
}
 
// 预处理及绑定
$stmt = $conn->prepare("INSERT INTO MyGuests (firstname, lastname, email) VALUES (?, ?, ?)");
$stmt->bind_param("sss", $firstname, $lastname, $email);
 
// 设置参数并执行
$firstname = "John";
$lastname = "Doe";
$email = "john@example.com";
$stmt->execute();
 
$firstname = "Mary";
$lastname = "Moe";
$email = "mary@example.com";
$stmt->execute();
 
$firstname = "Julie";
$lastname = "Dooley";
$email = "julie@example.com";
$stmt->execute();
 
echo "新记录插入成功";
 
$stmt->close();
$conn->close();
?>

```


## 读取数据    

#### 从MySQL数据库读取数据
**select**语句用于从数据表中读取数据
```
SELECT column_name(s) FROM table_name(数据库中表单的名称)
```
可以使用"*"号来读取所以数据表中的字段：
```
SELECT * FROM table_name
```


## Where子句

>定义：**WHERE** 子句用于提取满足指定标准的的记录。
- 语法
```
SELECT * FROM table_name WHERE column_name operator value
```


## Order By 关键词

定义：

1、ORDER BY 关键词用于对记录集中的数据进行排序。     
2、ORDER BY 关键词默认对记录进行升序排序。  
3、如果你想降序排序，请使用 DESC 关键字。

```
SELECT column_name(s) FROM table_name ORDER BY column_name(s) ASC|DESC
```


## Update

>UPDATE 语句用于中修改数据库表中的数据。
- 语法
```
UPDATE table_name  SET column1=value, column2=value2,... WHERE some_column=some_value
```


## Delete

>定义：DELETE 语句用于从数据库表中删除行。
- 语法
```
DELETE FROM table_name  WHERE some_column = some_value
```


## ODBC

>定义：ODBC是一种应用编程接口（Application Programming Interface，API），使我们有能力连接到某个数据源（比如一个 MS Access 数据库）。
### 创建ODBC连接
**创建到达 MS Access 数据库的 ODBC 连接的方法：**

- 1、在控制面板中打开管理工具图标
- 2、双击其中的数据源(ODBC)图标。
- 3、选择系统 DSN 选项卡。
- 4、点击系统 DSN 选项卡中的添加。
- 5、选择Microsoft Access Driver。点击完成。
- 6、在下一个界面，点击选择来定位数据库。
- 7、为数据库起一个数据源名(DSN)。
- 8、点击确定
### 连接到 ODBC
**odbc_connect()** 函数用于连接到 ODBC 数据源。该函数有四个参数：数据源名、用户名、密码以及可选的指针类型。    
**odbc_exec()** 函数用于执行SQL语句。
```
实例
下面的实例创建了到达名为 northwind 的 DSN 的连接，没有用户名和密码。然后创建并执行一条 SQL 语句：

$conn=odbc_connect('northwind','','');
$sql="SELECT * FROM customers";
$rs=odbc_exec($conn,$sql);
```
### 取回记录
**odbc_fetch_row()** 函数用于从结果集中返回记录。如果能够返回行，则函数返回 true，否则返回 false。该函数有两个参数：ODBC结果标识符和可选的行号
```
odbc_fetch_row($rs)
```
### 从记录中取回字段  
**odbc_result()** 函数用于从记录中读取字段。该函数有两个参数：ODBC 结果标识符和字段编号或名称。

下面的代码行从记录中返回第一个字段的值：
```
$compname=odbc_result($rs,1);
```
### 关闭 ODBC 连接
**odbc_close()** 函数用于关闭 ODBC 连接。