### 1、JS 的作用

cookie, BS,CS

Node.js

### 2、语法特点

基于对象和事件驱动是什么意思；

js可以做什么；

单线程？

异步？  异步操作有哪些？

### 3、JS的引入方式

重定向

### 4、变量

 1.预解析 2.解析

关键字和保留字有哪些？





JSON？

对象的一个属性`__proto__`指向    原型对象



es6属性：
name属性，rest参数，箭头函数，let，块级作用域，class，模板字符串、解构赋值、给参数赋默认值、



创建对象的方式

















**1.原型模式**

function Father(){

this.property = true;



}

Father.prototype.getValue = function(){



return this.property;

}

function Son(){

this.Sonproperty = false;

}

//继承Father

Son.prototype = new Father();//原型重写，contructor被改写

Son.prototype.construtor = Son;//重新指向Son

Son.prototype.getSonValue = function(){

return this.property;

}

var instance = new Son();

console.log(instance.getValue());

/*缺点：

1.引用原型值会被所有实例共享

2.子类无法向父类传参

*/

**2.借用函数继承（经典继承）**

 

//基本思想：在子类型构造函数中调用超类型的构造函数

function Father(){

this.colors = ["red","blue","green"];

name = "haha";

}



function Son(){

Father.call(this);//继承Father，并向父类型传参



}

Son.prototype = new Father;

var instance1 = new Son();

instance1.colors.push("black");

console.log(instance1.colors);



instance2 = new Son();

instance2.colors.push("pink");

console.log(instance2.colors);

/*

解决了原型链所存在的两个问题

但是依然存在构造函数方法无法复用的问题

*/


**3.组合继承（伪经典继承)---经常使用**

 

// //集合原型和构造两者之长

// //基本思想： 使用原型链实现对原型属性和方法的继承,通过借用构造函数来实现对实例属性的继承.

function Father(name){

this.name = name;

this.colors = ["red","pink","green"];

}



Father.prototype.sayname = function(){

console.log(this.name);

}



function Son(name,age){

Father.call(this,name);//使用构造函数进行实例属性的继承

this.age = age;

}



Son.prototype = new Father();//使用原型链继承超类型方法

Son.prototype.constructor = Son;//重新指向Son

Son.prototype.sayage = function(){

console.log(this.age);

}



var instance1 = new Son("lisi",12);

instance1.colors.push("brown");

console.log(instance1.colors);

instance1.sayname();

instance1.sayage();



var instance2 = new Son("hah",22);

instance2.colors.push("black");

console.log(instance2.colors);

instance2.sayname();

instance2.sayage();

**4.原型式继承（浅拷贝）**

//原型式继承

/*基本思想：在object()函数内部, 先创建一个临时性的构造函数,

然后将传入的对象作为这个构造函数的原型,最后返回了这个临时类型

的一个新实例.*/

var person = {

name : "van",

friends : ["hah","yisi"]

};

var anotherPerson = Object.create(person);

anotherPerson.friends.push("yixiu");

console.log(person.friends);

/*

和原型模式相同的是所有新对象依然共享含有引用类型值的属性

*/

**5.寄生式继承**

 

/*寄生式继承的思路与(寄生)构造函数和工厂模式类似,

即创建一个仅用于封装继承过程的函数,该函数在内部以

某种方式来增强对象,最后再像真的是它做了所有工作一样返回对象.*/

function createAnother(original){

var clone = Object.create(original);//先进行浅复制后增强对象

clone.sayhi = function(){//进行增强

console.log(1);

}

return clone;

}

var person = {

friends : ["hah","yisi"]

};

//缺点：无法进行函数复用，只能使用父类中的方法

// person.prototype.say = function(){

// console.log(2);

// }

var anotherPerson = createAnother(person);

anotherPerson.friends.push("yixiu");

console.log(person.friends);

anotherPerson.sayhi();

// anotherPerson.say();

**6.寄生组合式继承(结合前面的所有优点)**

 

//寄生组合式继承就是为了降低调用父类构造函数的开销而出现的

//基本思路是: 不必为了指定子类型的原型而调用超类型的构造函数

function extend(subClass,superClass){

var F = function(){};

F.prototype = superClass.prototype;

//subClass.prototype =superClass.prtotype相当于原型共享而非继承

subClass.prototype = new F();//继承superClass的原型

subClass.prototype.constructor = subClass;//原型重写，手动绑定



subClass.superclass = superClass.prototype;//将superClass.prototype缓存起来，方便后续访问

if(superClass.prototype.constructor == Object.prototype.constructor){

superClass.prototype.constructor = superClass;

}

}

function Father(name){

this.name = name;

this.colors = ["red","pink","green"];

}



Father.prototype.sayname = function(){

console.log(this.name);

}



function Son(name,age){

Father.call(this,name);//使用构造函数进行实例属性的继承，调用第一次

this.age = age;

}



extend(Son,Father);//

Son.prototype.constructor = Son;//重新指向Son

Son.prototype.sayage = function(){

console.log(this.age);

}



var instance1 = new Son("lisi",12);

instance1.colors.push("brown");

console.log(instance1.colors);

instance1.sayname();

instance1.sayage();



var instance2 = new Son("hah",22);

instance2.colors.push("black");

console.log(instance2.colors);

instance2.sayname();

instance2.sayage();