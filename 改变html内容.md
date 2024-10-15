JS能干什么？

# 改变html内容

```html
document.getElementById("demo").innerHTML = "Hello JavaScript"
```



将js放在body底部可以提高显示速度，因为解释脚本会拖慢显示速度。

# JS位置

- js写在`<script>`和`</script>`之间。

```html
<script>
document.getElementById("demo").innerHTML = "My First JavaScript";
</script>
```

script可以放在`<head>`或`<body>`中。

- js写在外部文件中，然后用src属性引用。

  ```html
  <script src="myScript.js"></script>
  <script src="myScript2.js"></script>
  ```

# JS输出

`innerHTML`属性定义html的内容。

`document.write()`写内容到html中。

`window.alert()`写入警告窗。

`console.log()`写入console。

`window.print()`弹出打印窗口。

# JS声明

```html
var a = 100; //过时的用法
let x = "abc";
let y = 123.1;
const pi = 3.14 ; //常量，不可变
let person = "John Doe", carName = "Volvo" ,price = 200;
let person = "John Doe",
carName = "Volvo",
price = 200;
let carName ; //carName未定义，值为undefined
let _x = 2; //以_开头通常用于表示私有变量
let $$$ = 2; //以$开头通常用于表示主函数的别名
```

JS有Global Scope，Function Scope.

ES6引入的let和const有Block Scope。

var声明的变量总是有Global Scope，没有Block Scope。

```
let x = 10;
// Here x is 10

{
let x = 2;
// Here x is 2
}

// Here x is 10



var x = 10;
// Here x is 10

{
var x = 2;
// Here x is 2
}

// Here x is 2
```



let有Block Scope；使用之前必须先声明；不能重新声明。

const有Block Scope；使用之前必须先声明；不能重新声明；必须分配且不能重新分配；

# JS数据类型

## 基本数据类型

### number

JS只有1个类型：double(64bit浮点数)

没有小数点或指数的整数的最大精确度为15位。

浮点数计算是不精确的，需要转成整数计算。

```
let x = 0.2 + 0.1; //不总是准确
let x = (0.2 * 10 + 0.1 * 10) / 10; //总是准确
```



NaN: 保留字，指示该数字不是合法的数字

```
let x = 100 / "Apple"; //和字符串进行代数运算得到NaN
isNaN(x);  //isNaN判断变量是否不是数字(Not a Number)，这里返回true
typeof NaN; //返回number

//NaN进行运算依然是NaN
let x = NaN;
let y = 5;
let z = x + y;  //z为NaN
```



Infinity: 数字大小超出允许的最大值

-Infinity: 数字大小超出允许的最小值

```
typeof Infinity; //返回number
```

- 方法

```
let myNumber = 32;
myNumber.toString(); //转换成string
myNumber.toString(32); //转换成32进制的string：'10'
myNumber.toString(16);  //转换成16进制的string: '20'
myNumber.toString(12);
myNumber.toString(10);
myNumber.toString(8);
myNumber.toString(2);

Number.isInteger(10);  //true
Number.isInteger(10.5); //false

Number.MAX_SAFE_INTEGER; // 9007199254740991
Number.MIN_SAFE_INTEGER;  // -9007199254740991

Number.isSafeInteger(10); //true
Number.isSafeInteger(12345678901234567890); //false

let x = 9.656;
x.toExponential(); //'9.656e+0'
x.toExponential(2); //'9.66e+0'
x.toExponential(4); //'9.6560e+0'

let x = 9.656;
x.toFixed(0); //'10'
x.toFixed(2); //'9.66'
x.toFixed(4); //'9.6560'

let x = 9.656;
x.toPrecision(); //'9.656'
x.toPrecision(2); //'9.66'
x.toPrecision(4); //'9.656'

//valueof()用于将object转成primitive
let x = new Number(42);
x.valueOf();  //42

//Number(x) 将x转换成number类型
Number(true); //1
Number(false); //0
Number("10");  //10
Number("  10"); //10
Number("10  "); //10
Number(" 10  "); //10
Number("10.33"); //10.33
Number("10,33"); //NaN
Number("10 33"); //NaN
Number("John"); //NaN

Number(new Date("1970-01-01")) //0
Number(new Date("1970-01-02")) //86400000

//parseInt将string转换成number，只有第一个数字会转换
parseInt("-10"); //-10
parseInt("-10.33"); //-10
parseInt("10"); //10
parseInt("10.33"); //10
parseInt("10 20 30"); //10
parseInt("10 years"); //10
parseInt("years 10"); //NaN

//parseFloat将string转换成number，只有第一个数字会转换
parseFloat("10"); //10
parseFloat("10.33"); //10.33
parseFloat("10 20 30"); //10
parseFloat("10 years"); //10
parseFloat("years 10"); //NaN

Number.parseFloat("10"); //10
Number.parseFloat("10.33"); //10.33
Number.parseFloat("10 20 30"); //10
Number.parseFloat("10 years"); //10
Number.parseFloat("years 10"); //NaN

Number.parseInt("-10"); //-10
Number.parseInt("-10.33"); //-10
Number.parseInt("10"); //10
Number.parseInt("10.33"); //10
Number.parseInt("10 20 30"); //10
Number.parseInt("10 years"); //10
Number.parseInt("years 10"); //NaN
```



### string

- 方法

```
let text = "ABCDEFGHIJKLMNOPQRSTUVWXYZ";
let length = text.length; //字符串长度

let text = "HELLO WORLD";
let char = text.charAt(0); //返回索引处的字符“H”

let text = "HELLO WORLD";
let char = text.charCodeAt(0); //返回索引处的字符的utf-16编码“72”

const name = "W3Schools";
let letter = name.at(2); //返回索引处的字符“S”，at支持负索引，比如at(-2)
let letter = name[2]; //返回索引处的字符“S”（把字符作为array看）

let text = "Apple, Banana, Kiwi";
let part = text.slice(-12, -6); //slice(start, end)，不包括end

let str = "Apple, Banana, Kiwi";
let part = str.substring(7, 13); //与slice类似，但将负数视为0

let str = "Apple, Banana, Kiwi";
let part = str.substr(7, 6); //与slice类似，但第2位是长度

let text1 = "Hello";
let text2 = "World";
let text3 = text1.concat(" ", text2);

let text1 = "      Hello World!      ";
let text2 = text1.trim();

let text1 = "     Hello World!     ";
let text2 = text1.trimStart(); //去除左边的空格

let text1 = "     Hello World!     ";
let text2 = text1.trimEnd(); //去除右边的空格

let text = "5";
let padded = text.padStart(4,"0"); //左填充0，直到长度为4

let text = "5";
let padded = text.padEnd(4,"0"); //右填充0，直到长度为4

let text = "Hello world!";
let result = text.repeat(2);

let text = "Please visit Microsoft and Microsoft!";
let newText = text.replace("Microsoft", "W3Schools"); //replace只替换第一个匹配的

let text = "Please visit Microsoft!";
let newText = text.replace(/MICROSOFT/i, "W3Schools"); //不区分大小写

let text = "Please visit Microsoft and Microsoft!";
let newText = text.replace(/Microsoft/g, "W3Schools"); //全部替换

text = text.replaceAll(/cats/g,"dogs"); //支持正则

//string转array
text.split(",")    // Split on commas
text.split(" ")    // Split on spaces
text.split("|")    // Split on pipe
text.split("")     // 分割成单个字符
text.split()       // 字符串作为array第一个值

let text1 = "Hello World!";
let text2 = text1.toUpperCase();

let text1 = "Hello World!";       // String
let text2 = text1.toLowerCase();  // text2 is text1 converted to lower

```

- 查找

```
//indexOf不支持正则
let text = "Please locate where 'locate' occurs!";
let index = text.indexOf("locate"); //返回第1个匹配的字符串的索引：7

let text = "Please locate where 'locate' occurs!";
let index = text.lastIndexOf("locate"); //返回最后1个匹配的字符串的索引：21

indexOf和lastIndexOf如果没有找到，返回-1。

let text = "Please locate where 'locate' occurs!";
let index = text.indexOf("locate", 15); //返回21

let text = "Please locate where 'locate' occurs!";
text.lastIndexOf("locate", 15); //从第15位开始向前查找，返回7

//search支持正则，不支持指定位置
let text = "Please locate where 'locate' occurs!";
text.search("locate"); //7

let text = "Please locate where 'locate' occurs!";
text.search(/locate/); //7

//match支持正则，返回一个数组
let text = "The rain in SPAIN stays mainly in the plain";
text.match(/ain/gi);  //返回["ain","AIN","ain","ain"]

//matchAll支持正则，返回一个迭代器
let text = "I love cats. Cats are very easy to love. Cats are very popular."
const iterator = text.matchAll(/Cats/gi);

//includes查找是否包含指定字符，包含返回true，不包含返回false
let text = "Hello world, welcome to the universe.";
text.includes("world", 12); //false

//startsWith查找是否以指定字符开头，是返回true，否返回false
let text = "Hello world, welcome to the universe.";
text.startsWith("world", 6) //true

//endsWith查找是否以指定字符结束，是返回true，否返回false
let text = "Hello world, welcome to the universe.";
text.endsWith("world", 11); //true


//String Template支持字符串插值
let firstName = "John";
let lastName = "Doe";

let text = `Welcome ${firstName}, ${lastName}!`;


```



### bigint

```
let x = BigInt(999999999999999); //或者let x = 999999999999999n;
let type = typeof x; // 'bigint'
```



### boolean

```
Boolean(10 > 9) //true
(10 > 9) //true
10 > 9 //true

```

| **Operator** | **Description**                   |
| ------------ | --------------------------------- |
| ==           | equal to                          |
| ===          | equal value and equal type        |
| !=           | not equal                         |
| !==          | not equal value or not equal type |
| >            | greater than                      |
| <            | less than                         |
| >=           | greater than or equal to          |
| <=           | less than or equal to             |
| &&           | and                               |
| \|\|         | or                                |
| !            | not                               |

```
// 三元操作
let voteable = 20;
let voteable = (age < 18) ? "Too young":"Old enough";
  // text = "Old enough"



age = Number(age);
if (isNaN(age)) {
  voteable = "Input is not a number";
} else {
  voteable = (age < 18) ? "Too young" : "Old enough";
}

//??如果左边不为null或undefined，返回左边的，否则返回右边的
let name = null;
let text = "missing";
let result = name ?? text; // result = "missing"
```



- undefined

- null

- symbol

## 引用数据类型（Reference Types）

 引用数据类型共享相同的内存地址。

 JS中，一切皆对象。

### build-in object

#### objects

```
const person = {firstName:"John", lastName:"Doe", age:50, eyeColor:"blue"};
```

使用const关键字声明objects是一种常见的做法。

```
// Create an Object
const person = {
  firstName: "John",
  lastName: "Doe",
  id: 5566,
  fullName: function() {
  return this.firstName + " " + this.lastName;
  }
};

name = person.fullName(); //调用方法

// Create an Array
const person = {
  name: "John",
  age: 30,
  city: "New York"
};
const myArray = Object.values(person); //myArray = ["John",30,"New York"]

//添加方法
person.changeName = function (name) {
  this.lastName = name;
}
```

​       object.values()获取对象的值为数组

​       object.entries()获取对象的key和value

​       JSON.stringify()转换对象成json对象

```
// Create an Object
const person = {
  name: "John",
  age: 30,
  city: "New York"
};

// Stringify Object
let myString = JSON.stringify(person); //myString的值为{"name":"John","age":30,"city":"New York"}

```

使用构造函数创建新的type：

```
//type通常大写第一个字母
function Person(first, last, age, eyecolor) {
  this.firstName = first;
  this.lastName = last;
  this.age = age;
  this.eyeColor = eyecolor;
  this.fullName = function() {
    return this.firstName + " " + this.lastName;
  };
}

const myFather = new Person("John", "Doe", 50, "blue");
const myMother = new Person("Sally", "Rally", 48, "green");
const mySister = new Person("Anna", "Rally", 18, "green");

myFather.fullName()

//添加属性
Person.prototype.haircolor = "Black"; 

//添加方法
Person.prototype.changeName = function (name) {
  this.lastName = name;
}
```







#### arrays

使用const关键字声明数组是一种常见的做法。

```
const cars = ["Saab", "Volvo", "BMW"]

const cars = [
  "Saab",
  "Volvo",
  "BMW"
];

const cars = [];
cars[0]= "Saab";
cars[1]= "Volvo";
cars[2]= "BMW";


//判断是否是array
const fruits = ["Banana", "Orange", "Apple"];
let type = typeof fruits; // object

//方法1
const fruits = ["Banana", "Orange", "Apple"];
Array.isArray(fruits); //true

//方法2
const fruits = ["Banana", "Orange", "Apple"];
(fruits instanceof Array); //true
```

##### 方法

```
const fruits = ["Banana", "Orange", "Apple", "Mango"];
let size = fruits.length; //4

const fruits = ["Banana", "Orange", "Apple", "Mango"];
document.getElementById("demo").innerHTML = fruits.toString(); //Banana,Orange,Apple,Mango

const fruits = ["Banana", "Orange", "Apple", "Mango"];
let fruit = fruits.at(2); //等同fruits[2]
let fruit = fruits.at(-1); //at支持负数

const fruits = ["Banana", "Orange", "Apple", "Mango"];
document.getElementById("demo").innerHTML = fruits.join(" * "); //Banana * Orange * Apple * Mango

const fruits = ["Banana", "Orange", "Apple", "Mango"];
fruits.pop(); //删除最后一个元素

const fruits = ["Banana", "Orange", "Apple", "Mango"];
fruits.push("Kiwi"); //在最后添加一个元素

const fruits = ["Banana", "Orange", "Apple", "Mango"];
fruits.shift(); //左移所有元素

const fruits = ["Banana", "Orange", "Apple", "Mango"];
fruits.unshift("Lemon"); //左边插入元素

const fruits = ["Banana", "Orange", "Apple", "Mango"];
fruits[fruits.length] = "Kiwi"; //在最后添加一个元素

const fruits = ["Banana", "Orange", "Apple", "Mango"];
delete fruits[0]; //delete会造成undefined holes，使用pop或shift替代

//concat()不改变原有的数组，而是生成1个新数组
const arr1 = ["Cecilie", "Lone"];
const arr2 = ["Emil", "Tobias", "Linus"];
const arr3 = ["Robin", "Morgan"];
const myChildren = arr1.concat(arr2, arr3);


const arr1 = ["Emil", "Tobias", "Linus"];
const myChildren = arr1.concat("Peter");  // ["Emil", "Tobias", "Linus","Peter"];


const fruits = ["Banana", "Orange", "Apple", "Mango", "Kiwi"];
fruits.copyWithin(3, 0, 2); //将[0,2)的元素拷贝覆盖到从3开始：["Banana", "Orange", "Apple", "Banana", "Orange"]
// copyWithin()覆盖已经存在的值，不增加array的元素，不改变array的长度


const myArr = [[1,2],[3,4],[5,6]];
const newArr = myArr.flat(); // [1, 2, 3, 4, 5, 6]

const myArr = [1, 2, 3, 4, 5, 6];
const newArr = myArr.flatMap(x => [x, x * 10]); // [1, 10, 2, 20, 3, 30, 4, 40, 5, 50, 6, 60]

//splice(x,y,z) 从第x索引处，移除y个元素，添加z元素
const fruits = ["Banana", "Orange", "Apple", "Mango"];
fruits.splice(2, 0, "Lemon", "Kiwi"); // ["Banana", "Orange", "Lemon", "Kiwi","Apple", "Mango"]

const fruits = ["Banana", "Orange", "Apple", "Mango"];
fruits.splice(2, 2, "Lemon", "Kiwi"); // ["Banana", "Orange", "Lemon", "Kiwi"]

const fruits = ["Banana", "Orange", "Apple", "Mango"];
fruits.splice(0, 1); //  ["Orange", "Apple", "Mango"]

//toSpliced()不会修改原数组，而是创建一个新数组
const months = ["Jan", "Feb", "Mar", "Apr"];
const spliced = months.toSpliced(0, 1); //["Feb", "Mar", "Apr"]

//slice(x,y)从原数组x索引复制到y索引元素到新数组，不改变原数组
const fruits = ["Banana", "Orange", "Lemon", "Apple", "Mango"];
const citrus = fruits.slice(1); //["Orange", "Lemon", "Apple", "Mango"]

const fruits = ["Banana", "Orange", "Lemon", "Apple", "Mango"];
const citrus = fruits.slice(1, 3); //["Orange", "Lemon"]


const fruits = ["Apple", "Orange", "Apple", "Mango"];
let position = fruits.indexOf("Apple") + 1; // 1
// indexOf查找不到返回-1

const fruits = ["Apple", "Orange", "Apple", "Mango"];
let position = fruits.lastIndexOf("Apple") + 1; // 3

const fruits = ["Banana", "Orange", "Apple", "Mango"];
fruits.includes("Mango"); // is true
//Array.includes()允许查找NaN，而Array.indexOf()不允许

//find查找第一个匹配函数的值
const numbers = [4, 9, 16, 25, 29];
let first = numbers.find(myFunction);  //25

function myFunction(value, index, array) {
  return value > 18;
}

//findIndex查找第一个匹配函数的值的索引
const numbers = [4, 9, 16, 25, 29];
let first = numbers.findIndex(myFunction); //3

function myFunction(value, index, array) {
  return value > 18;
}

//findLast从右向左查找第一个满足条件的值
const temp = [27, 28, 30, 40, 42, 35, 30];
let high = temp.findLast(x => x > 40); //42

const temp = [27, 28, 30, 40, 42, 35, 30];
let pos = temp.findLastIndex(x => x > 40); //4


const fruits = ["Banana", "Orange", "Apple", "Mango"];
fruits.sort();  //原数组排序

const fruits = ["Banana", "Orange", "Apple", "Mango"];
fruits.reverse(); //原数组取反

const months = ["Jan", "Feb", "Mar", "Apr"];
const sorted = months.toSorted(); //不改变原数组

const months = ["Jan", "Feb", "Mar", "Apr"];
const reversed = months.toReversed(); //不改变原数组

const points = [40, 100, 1, 5, 25, 10];
points.sort(function(a, b){return a - b}); //由小到大数字排序

const points = [40, 100, 1, 5, 25, 10];
points.sort(function(a, b){return b - a}); //由大到小数字排序

const points = [40, 100, 1, 5, 25, 10];
points.sort(function(){return 0.5 - Math.random()}); //随机排序

//查找数组中的最大或最小值
//方法1：排序后取索引的第1或最后1位，效率较低
const points = [40, 100, 1, 5, 25, 10];
points.sort(function(a, b){return a - b}); 

//方法2：
function myArrayMin(arr) {
  return Math.min.apply(null, arr);
}

function myArrayMax(arr) {
  return Math.max.apply(null, arr);
}

//方法3：
function myArrayMin(arr) {
  let len = arr.length;
  let min = Infinity;
  while (len--) {
    if (arr[len] < min) {
      min = arr[len];
    }
  }
  return min;
}

function myArrayMax(arr) {
  let len = arr.length;
  let max = -Infinity;
  while (len--) {
    if (arr[len] > max) {
      max = arr[len];
    }
  }
  return max;
}

//排序对象数组
const cars = [
  {type:"Volvo", year:2016},
  {type:"Saab", year:2001},
  {type:"BMW", year:2010}
];

cars.sort(function(a, b){return a.year - b.year}); //cars依据数字大小升序排序

//cars依据string排序
cars.sort(function(a, b){
  let x = a.type.toLowerCase();
  let y = b.type.toLowerCase();
  if (x < y) {return -1;}
  if (x > y) {return 1;}
  return 0;
});


//foreach
const numbers = [45, 4, 9, 16, 25];
let txt = "";
numbers.forEach(myFunction);

function myFunction(value, index, array) {
  txt += value + "<br>";
}

//map
const numbers1 = [45, 4, 9, 16, 25];
const numbers2 = numbers1.map(myFunction); // numbers2 = [90,8,18,32,50]

function myFunction(value, index, array) {
  return value * 2;
}

//flatmap
const myArr = [1, 2, 3, 4, 5,6];
const newArr = myArr.flatMap(x => [x, x * 10]); //[1,10,2,20,3,30,4,40,5,50,6,60]

//filter
const numbers = [45, 4, 9, 16, 25];
const over18 = numbers.filter(myFunction);  //[45,25]

function myFunction(value, index, array) {
  return value > 18;
} 

//reduce
const numbers = [45, 4, 9, 16, 25];
let sum = numbers.reduce(myFunction); //从左往右：99

function myFunction(total, value, index, array) {
  return total + value;
}


const numbers = [45, 4, 9, 16, 25];
let sum = numbers.reduce(myFunction, 100); //199

function myFunction(total, value) {
  return total + value;
}

//reduceRight
const numbers = [45, 4, 9, 16, 25];
let sum = numbers.reduceRight(myFunction); //从右向左：99

function myFunction(total, value, index, array) {
  return total + value;
}

//every判断所有元素是否满足函数
const numbers = [45, 4, 9, 16, 25];
let allOver18 = numbers.every(myFunction); //false

function myFunction(value, index, array) {
  return value > 18;
}

//some判断部分元素是否满足函数
const numbers = [45, 4, 9, 16, 25];
let someOver18 = numbers.some(myFunction); //true

function myFunction(value, index, array) {
  return value > 18;
}

//Array.from从有length属性的对象或iterable对象中创建数组
Array.from("ABCDEFG"); //['A', 'B', 'C', 'D', 'E', 'F', 'G']


//Array.keys()返回iterator
const fruits = ["Banana", "Orange", "Apple", "Mango"];
const keys = fruits.keys(); //

let text='';
for (let x of keys) {
  text += x + "<br>";
}

//Array.entries()返回带索引的iterator
const fruits = ["Banana", "Orange", "Apple", "Mango"];
const f = fruits.entries();  
//[0, "Banana"]
//[1, "Orange"]
//[2, "Apple"]
//[3, "Mango"]

for (let x of f) {
  document.getElementById("demo").innerHTML += x;
}

//不修改原数组的情况下安全的更新元素
const months = ["Januar", "Februar", "Mar", "April"];
const myMonths = months.with(2, "March"); //["Januar", "Februar", "March", "April"];



```



#### dates

默认情况下，js使用浏览器的时区，将时间显示为string

**Sun Oct 13 2024 13:53:20 GMT+0800 (中国标准时间)**

UTC时间等同GMT时间

当设置时间时没有设置时区，JS使用浏览器时区；

当获取时间时没有指定时区，JS使用浏览器时区；

```
// 创建时间
new Date()
new Date(date string)

new Date(year,month)
new Date(year,month,day)
new Date(year,month,day,hours)
new Date(year,month,day,hours,minutes)
new Date(year,month,day,hours,minutes,seconds)
new Date(year,month,day,hours,minutes,seconds,ms)

new Date(milliseconds)

// 举例
const d = new Date(); //返回本时区时间
const d = new Date("2022-03-25") //返回指定日期时间+时区
const d = new Date(2018, 11, 24, 10, 33, 30, 0); //year, month, day, hour, minute, second, and millisecond ，month从0-11，所以这里的11实际上是12月
const d = new Date("2015-03-25T12:00:00Z"); //Z表示UTC时间

// JS存储时间为1970.1.1号之后的毫秒数。
const d = new Date(86400000); //1970.1.2

// 时间显示
JS默认使用toString()显示时间，包含时区信息。
const d = new Date();
d.toString(); //Sun Oct 13 2024 14:08:07 GMT+0800 (中国标准时间)
d.toDateString(); //Sun Oct 13 2024
d.toTimeString(); //15:53:45 GMT+0800 (中国标准时间)
d.toUTCString(); //Sun, 13 Oct 2024 06:09:20 GMT
d.toISOString(); //2024-10-13T06:10:00.662Z


// 方法
let msec = Date.parse("March 21, 2012"); //距离1970.1.1的毫秒数
const d = new Date(msec); // March 21, 2012

```

| Method            | Description                                       |
| :---------------- | :------------------------------------------------ |
| getFullYear()     | Get **year** as a four digit number (yyyy)        |
| getMonth()        | Get **month** as a number (0-11)                  |
| getDate()         | Get **day** as a number (1-31)                    |
| getDay()          | Get **weekday** as a number (0-6)                 |
| getHours()        | Get **hour** (0-23)                               |
| getMinutes()      | Get **minute** (0-59)                             |
| getSeconds()      | Get **second** (0-59)                             |
| getMilliseconds() | Get **millisecond** (0-999)                       |
| getTime()         | Get **time** (milliseconds since January 1, 1970) |

```
//上面的get方法返回Local time
//获取文字版month
const months = ["January", "February", "March", "April", "May", "June", "July", "August", "September", "October", "November", "December"];

const d = new Date("2021-03-25");
let month = months[d.getMonth()];


//获取文字版weekday
const days = ["Sunday", "Monday", "Tuesday", "Wednesday", "Thursday", "Friday", "Saturday"];

const d = new Date("2021-03-25");
let day = days[d.getDay()];

//getTime()返回unix时间毫秒数
const d = new Date("1970-01-01");
d.getTime();  //0

//Date.now()返回此刻的unix时间毫秒数
let ms = Date.now();

//getTimezoneOffset()返回本地时间和UTC时间相差的分钟数
const d = new Date();
let diff = d.getTimezoneOffset();

```

| Method            | Description                                       |
| :---------------- | :------------------------------------------------ |
| setDate()         | Set the day as a number (1-31)                    |
| setFullYear()     | Set the year (optionally month and day)           |
| setHours()        | Set the hour (0-23)                               |
| setMilliseconds() | Set the milliseconds (0-999)                      |
| setMinutes()      | Set the minutes (0-59)                            |
| setMonth()        | Set the month (0-11)                              |
| setSeconds()      | Set the seconds (0-59)                            |
| setTime()         | Set the time (milliseconds since January 1, 1970) |

```
const d = new Date();
d.setFullYear(2020);
d.setFullYear(2020, 11, 3);
d.setMonth(11);
d.setDate(15);
d.setDate(d.getDate() + 30);
d.setHours(22);
d.setMinutes(30);
d.setSeconds(30);
```



#### maps

key-value键值对。key可以是任意类型。key是有序的（按插入）。

```
// Create a Map
const fruits = new Map([
  ["apples", 500],
  ["bananas", 300],
  ["oranges", 200]
]);



// Create a Map
const fruits = new Map();
// Set Map Values
fruits.set("apples", 500);
fruits.set("bananas", 300);
fruits.set("oranges", 200); 
fruits.set("apples", 200); //修改值
fruits.get("apples");    // Returns 200

typeof fruits; // Returns object
fruits instanceof Map; // Returns true

fruits.size //3
fruits.delete("apples"); //删除
fruits.clear(); //全删
fruits.has("apples"); //false


const fruits = new Map([
  ["apples", 500],
  ["bananas", 300],
  ["oranges", 200]
]);

let text = "";
fruits.forEach (function(value, key) {
  text += key + ' = ' + value + "<br>"
})  
// apples = 500
// bananas = 300
// oranges = 200



// List all entries,entries()返回一个包含key,value的iterator object
let text = "";
for (const x of fruits.entries()) {
  text += x;
}

// List all keys，keys()返回一个只包含key的iterator object
let text = "";
for (const x of fruits.keys()) {
  text += x;
}



// List all values，values()返回一个只包含value的iterator object
let text = "";
for (const x of fruits.values()) {
  text += x;
}



//map可以使用object作为key
// Create Objects
const apples = {name: 'Apples'};
const bananas = {name: 'Bananas'};
const oranges = {name: 'Oranges'};

// Create a Map
const fruits = new Map();

// Add new Elements to the Map
fruits.set(apples, 500);
fruits.set(bananas, 300);
fruits.set(oranges, 200);



// Create an Array
const fruits = [
  {name:"apples", quantity:300},
  {name:"bananas", quantity:500},
  {name:"oranges", quantity:200},
  {name:"kiwi", quantity:150}
];
// Callback function to Group Elements
function myCallback({ quantity }) {
  return quantity > 200 ? "ok" : "low";
}
// Group by Quantity
const result = Map.groupBy(fruits, myCallback);


```







#### sets

唯一值的集合。

```
//创建方法1
// Create a Set
const letters = new Set(["a","b","c"]);


//创建方法2
// Create a Set
const letters = new Set();
// Add Values to the Set
letters.add("a");
letters.add("b");
letters.add("c");

typeof letters;      // Returns object
letters instanceof Set;  // Returns true


// Does the Set contain "d"?
answer = letters.has("d");  //false


// Create a Set
const letters = new Set(["a","b","c"]);
// List all Elements
let text = "";
letters.forEach (function(value) {
  text += value + "<br>";
})



// Create a Set
const letters = new Set(["a","b","c"]);
// values()返回set中的值为Iterator,keys()返回set中的值为Iterator
const myIterator = letters.values();  //等同letters.keys()
// const myIterator = letters.entries();  //entries返回set值组成的数组[value,value]
// List all Values
let text = "";
for (const entry of myIterator) {
  text += entry;
}

```







- intarrays

- floatarrays

- promises

#### math

  ```
  //math常数
  Math.E        // returns Euler's number
  Math.PI       // returns PI
  Math.SQRT2    // returns the square root of 2
  Math.SQRT1_2  // returns the square root of 1/2
  Math.LN2      // returns the natural logarithm of 2
  Math.LN10     // returns the natural logarithm of 10
  Math.LOG2E    // returns base 2 logarithm of E
  Math.LOG10E   // returns base 10 logarithm of E
  
  //取整数值
  Math.round(4.6); //5
  Math.round(4.4); //4
  
  Math.ceil(4.9); //5
  Math.ceil(4.7); //5
  Math.ceil(4.4); //5
  Math.ceil(4.2); //5
  Math.ceil(-4.2); //-4
  
  Math.floor(4.9); //4
  Math.floor(4.7); //4
  Math.floor(4.4); //4
  Math.floor(4.2); //4
  Math.floor(-4.2); //-5
  
  Math.trunc(4.9); //4
  Math.trunc(4.7); //4
  Math.trunc(4.4); //4
  Math.trunc(4.2); //4
  Math.trunc(-4.2); //-4
  
  Math.sign(-4);  //-1
  Math.sign(0);   //0
  Math.sign(4);   //1
  
  Math.pow(8, 2); //64
  Math.sqrt(64);  //8
  Math.abs(-4.7);  //4.7
  
  Math.sin(90 * Math.PI / 180); //1
  Math.cos(0 * Math.PI / 180);  //1
  
  Math.min(0, 150, 30, 20, -8, -200); //-200
  Math.max(0, 150, 30, 20, -8, -200); //150
  
  Math.random(); //返回[0,1)之间的随机数
  Math.log2(8);  //3
  Math.log10(1000); //3
  
  
  // Returns a random integer from 0 to 9:
  Math.floor(Math.random() * 10);
  
  // Returns a random integer from 0 to 10:
  Math.floor(Math.random() * 11);
  
  // Returns a random integer from 0 to 99:
  Math.floor(Math.random() * 100);
  
  // Returns a random integer from 0 to 100:
  Math.floor(Math.random() * 101);
  
  // Returns a random integer from 1 to 10:
  Math.floor(Math.random() * 10) + 1;
  
  // Returns a random integer from 1 to 100:
  Math.floor(Math.random() * 100) + 1;
  
  // 返回[min,max)
  function getRndInteger(min, max) {
    return Math.floor(Math.random() * (max - min) ) + min;
  }
  
  // 返回[min,max]
  function getRndInteger(min, max) {
    return Math.floor(Math.random() * (max - min + 1) ) + min;
  }
  
  
  ```

  

```html
{};           // object object
[];           // array object
/()/          // regexp object
function(){}; // function
```



### user defined objects



# 测试数据类型

```
typeof "John"          // Returns "string"
typeof ("John"+"Doe")  // Returns "string"
typeof 3.14            // Returns "number"
typeof (33 + 66)       // Returns "number"
typeof NaN             // Returns "number"
typeof 1234n           // Returns "bigint"
typeof true            // Returns "boolean"
typeof false           // Returns "boolean"
typeof {name:'John'}   // Returns "object"
typeof [1,2,3,4]       // Returns "object"
typeof {}              // Returns "object"
typeof []              // Returns "object"
typeof new Object()    // Returns "object"
typeof new Array()     // Returns "object"
typeof new Date()      // Returns "object"
typeof new Set()       // Returns "object"
typeof new Map()       // Returns "object"
typeof function () {}  // Returns "function"
typeof x               // Returns "undefined"
typeof null            // Returns "object"


// Returns function Object() {[native code]}:
{name:'John',age:34}.constructor

// Returns function Array() {[native code]}:
[1,2,3,4].constructor

// Returns function Date() {[native code]}:
new Date().constructor

// Returns function Set() {[native code]}:
new Set().constructor

// Returns function Map() {[native code]}:
new Map().constructor

// Returns function Function() {[native code]}:
function () {}.constructor

//测试myArray是否是数组
(myArray.constructor === Array);




<a href="javascript:void(0);">
  Useless link
</a>

<a href="javascript:void(document.body.style.backgroundColor='red');">
  Click me to change the background color of body to red
</a>
```

# HTML Events

| Event       | Description                                        |
| :---------- | :------------------------------------------------- |
| onchange    | An HTML element has been changed                   |
| onclick     | The user clicks an HTML element                    |
| onmouseover | The user moves the mouse over an HTML element      |
| onmouseout  | The user moves the mouse away from an HTML element |
| onkeydown   | The user pushes a keyboard key                     |
| onload      | The browser has finished loading the page          |

#  逻辑判断

```
// if
if (hour < 18) {
  greeting = "Good day";
}


if (hour < 18) {
  greeting = "Good day";
} else {
  greeting = "Good evening";
}


if (time < 10) {
  greeting = "Good morning";
} else if (time < 20) {
  greeting = "Good day";
} else {
  greeting = "Good evening";
}

//switch
//使用strict比较（===）
switch (new Date().getDay()) {
  case 0:
    day = "Sunday";
    break;
  case 1:
    day = "Monday";
    break;
  case 2:
     day = "Tuesday";
    break;
  case 3:
    day = "Wednesday";
    break;
  case 4:
    day = "Thursday";
    break;
  case 5:
    day = "Friday";
    break;
  case 6:
    day = "Saturday";
}


switch (new Date().getDay()) {
  case 6:
    text = "Today is Saturday";
    break;
  case 0:
    text = "Today is Sunday";
    break;
  default:
    text = "Looking forward to the Weekend";
}



switch (new Date().getDay()) {
  case 4:
  case 5:
    text = "Soon it is Weekend";
    break;
  case 0:
  case 6:
    text = "It is Weekend";
    break;
  default:
    text = "Looking forward to the Weekend";
}


//for
for (let i = 0; i < 5; i++) {
  text += "The number is " + i + "<br>";
}

//for in 轮询对象的属性
const person = {fname:"John", lname:"Doe", age:25};
let txt = "";
for (let x in person) {
  txt += person[x] + " ";
} //John Doe 25


//for in 不保证顺序，如果需要保证顺序，使用for或for of或Array.forEach()
const numbers = [45, 4, 9, 16, 25];
let txt = "";
for (let x in numbers) {
  txt += numbers[x] + "<br>"; 
}

const numbers = [45, 4, 9, 16, 25];
let txt = "";
numbers.forEach(myFunction);
function myFunction(value, index, array) {
  txt += value;
}

const cars = ["BMW", "Volvo", "Mini"];
let text = "";
for (let x of cars) {
  text += x + "<br>";
}

let language = "JavaScript";
let text = "";
for (let x of language) {
  text += x + "<br>";
}


let text = "";
let i = 0;
while (i < 10) {
  text += "<br>The number is " + i;
  i++;
}


let text = ""
let i = 0;
do {
  text += "<br>The number is " + i;
  i++;
}
while (i < 10);  



for (let i = 0; i < 10; i++) {
  if (i === 3) { break; }
  text += "The number is " + i + "<br>";
}


for (let i = 0; i < 10; i++) {
  if (i === 3) { continue; }
  text += "The number is " + i + "<br>";
}




const cars = ["BMW", "Volvo", "Saab", "Ford"];
let text = "";


//label:statements
//{}定义代码块
//定义一个label
list: {
  text += cars[0] + "<br>"; 
  text += cars[1] + "<br>"; 
  break list; //跳出label
  text += cars[2] + "<br>"; 
  text += cars[3] + "<br>"; 
}
```

# iterable

实现了next()方法的对象称为**iterator**。next()方法return两个属性：value和done。当done为true时，结束轮询。

实现了`Symbol.iterator`方法的object才能使用for of。

# Destructuring

任何iterables都可以使用。

```
const person = {
  firstName: "John",
  lastName: "Doe",
  age: 50
};

// Destructuring an Object
let {firstName, lastName} = person; 
let {firstName, lastName, country = "US"} = person;
let {lastName : name} = person; //等同 let lastName = "John", name = lastName;


// Destructuring a String
let name = "W3Schools";
let [a1, a2, a3, a4, a5] = name; //等同let a1 = 'W',a2='3',a3='S',a4='c',a5='h';

// Destructuring an Array
const fruits = ["Bananas", "Oranges", "Apples", "Mangos"];
let [fruit1, fruit2] = fruits;

// Create an Array
const fruits = ["Bananas", "Oranges", "Apples", "Mangos"];
// Destructuring
let [fruit1,,,fruit2] = fruits;  // let fruit1 = "Bananas",fruit2="Mangos";

// Create an Array
const fruits = ["Bananas", "Oranges", "Apples", "Mangos"];
// Destructuring
let {[0]:fruit1 ,[1]:fruit2} = fruits;


// Create an Array
const numbers = [10, 20, 30, 40, 50, 60, 70];
// Destructuring
const [a,b, ...rest] = numbers ;//a=10,b=20,rest=[30, 40, 50, 60, 70]


// Create a Map
const fruits = new Map([
  ["apples", 500],
  ["bananas", 300],
  ["oranges", 200]
]);

// Destructing
let text = "";
for (const [key, value] of fruits) {
  text += key + " is " + value;
}


let firstName = "John";
let lastName = "Doe";

// Destructing
[firstName, lastName] = [lastName, firstName];

```

# Errors

```
try {
  Block of code to try
}
catch(err) {
  Block of code to handle errors
}
finally {
  Block of code to be executed regardless of the try / catch result
}
```



```
<!DOCTYPE html>
<html>
<body>

<p>Please input a number between 5 and 10:</p>

<input id="demo" type="text">
<button type="button" onclick="myFunction()">Test Input</button>
<p id="p01"></p>

<script>
function myFunction() {
  const message = document.getElementById("p01");
  message.innerHTML = "";
  let x = document.getElementById("demo").value;
  try {
    if(x.trim() == "") throw "empty";
    if(isNaN(x)) throw "not a number";
    x = Number(x);
    if(x < 5) throw "too low";
    if(x > 10) throw "too high";
  }
  catch(err) {
    message.innerHTML = "Input is " + err;
  }
}
</script>

</body>
</html>
```

# JS Scope

JS有3种类型的scope.

block scope

function scope

function中的变量是Local 变量，在function执行完后自动删除。



global scope

```
myFunction();

// code here can use carName

function myFunction() {
  carName = "Volvo";
}

//carName未声明，所以carName自动成为了全局变量
//"Strict Mode"下，未声明的变量不会变成全局变量。

```

使用var声明的全局变量属于窗口对象。

```
var carName = "Volvo";
// code here can use window.carName
window.carName ; // "Volvo"

let carName = "Volvo";
// code here can not use window.carName
```

不要声明全局变量，因为全局变量会覆盖window变量；window对象会覆盖你的全局变量。



