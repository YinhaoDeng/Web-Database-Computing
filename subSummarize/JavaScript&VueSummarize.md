# week 3 精炼

## 1.0 JavaScript

### 1.0 定义：
- Dynamic
  - Code is interpreted as it is executed
- Weakly Typed
  - Types are associated with individual objects.
  - Can store ANY type in a variable/const.
  - Can pass ANY variable to ANY function (that accepts parameters)
- Event Driven
  - Concurrency can result in unexpected behaviour

分为客户端和服务端两部分。
- Server Side
  - Generate customised content on a web server and send to client
- Client Side
  - Execute code in client's Browser
### 1.1 Syntax & Semantics 语法语义
C-Style Syntax:
- Lines end in **;**
- Code blocks enclosed in **{ }**
- Comments:
  - Single line comments start with **//**
  - Multiline comments wrapped in /* */
- Variables:
  - Declared using **var**
  - Variable scope only at **global** and **function** level
  - Variables are not typed, so anything can be passed
anywhere
- Constants:
  - Declared using **const**
```javascript
/*
* Displays an alert showing whether it's Monday or not
*/
  function isItMonday() {
    const MONDAY = 1;
    var now = new Date();
    if (now.getDay() == MONDAY){
        alert("It's Monday!");
    } else {
        alert("It's not Monday...");
    }
  }
  // Run the function.
  isItMonday();
```
use the `<script>` tag 内嵌于HTML，来执行JS命令。


#### 1.1.1 _inline_ 表示法:
```html
<script>
    // Some javascript...
</script>
```
```html
<!DOCTYPE html>
<html>
  <head>
    <title>Monday</title>
  </head>
  <body>
     <h1>Is it Monday?</h1>
    <script>
    function isItMonday() {
        const MONDAY = 1;
        var now = new Date();
        if (now.getDay() == MONDAY){
            alert("It's Monday!");
        } else {
            alert("It's not Monday...");
        }
    }
    isItMonday();
  </script>
  </body>
</html>
```


#### 1.1.2 _external_ 表示法：
`<script src="file.js"></script>`
```html
<!DOCTYPE html>
<html>
    <head>
        <title>Monday</title>
    </head>
    <body>
        <h1>Is it Monday?</h1>
        <script src="monday.js"></script>
    </body>
</html>
```

事件驱动Javasript：
短例：
```html
    <button onclick="alert('Hello')">
        Let's find out!
    </button>
```
大例：
```javascript
<!DOCTYPE html>
<html>
    <head>
        <title>Monday</title>
        <script src="monday.js"></script>
    </head>
    <body>
        <h1>Is it Monday?</h1>
        <button onclick="isItMonday()">
         Let's find out!
        </button>
    </body>
</html>
```


#### 1.1.3 `<script>` Tag 的位置哲学
下面给出垃圾案例和优秀案例：(两个案例共用同样的JS file.)
JavaScript:
```Javascript
var array1 = ['I','think',"it's", 'Monday'];
var str1 = '';
for (var i=0; i<array1.length; i++) {
    str1 = str1 + array1[i] + ' ';
    console.log(array1[i]);
}
var heading = document.getElementById('my_heading');
heading.innerHTML = str1;
```
HTML:
```html
<!---垃圾案例：（不能正确运行）--->
<html>
    <head>
        <title>Monday</title>
        <script src="monday.js"></script>
    </head>
    <body>
        <h1 id="my_heading">Is it Monday?</h1>
    </body>
</html>

<!------优秀案例：------->
<html>
    <head>
        <title>Monday</title>
    </head>
    <body>
        <h1 id="my_heading">Is it Monday?</h1>
        <script src="monday.js"></script>
    </body>
</html>
```
小结：`<script>` tag应该和它对应的功能放在HTML文件里的同一个板块。不能出现以上情况：`<script>` tag 放在`<head>` tag里，而真正用到JS是在`<body>` tag里。


#### 1.1.4 NUll空字符
抛出问题：通常在无法找到要求的元素时发生。
解决方案：通过使用if check 或者 try-catch block来避免。
```html
<!DOCTYPE html>
<html>
    <head>
        <title>Null</title>
    </head>
    <body>
        <h2>null test</h2>
        <p id="nodemo"></p>

        <script>
        try {
            document.getElementById("demo").innerText = "Hello World!";
            alert("It worked!");
        } catch (e) {
            alert("It broke!");
        }
        </script>
    </body>
</html>
```
#### 1.1.5 区分 == 和 ===
- JavaScript does automatic type conversions.
- Comparing two equivalent values will yield a **true** result
- Can result in unexpected behaviour
  - 一般例子： 检查某个变量是否等于0， 可以这么写：
    `if (x == 0) { ... }`
  - 但如果输入**null**检验其是否等于0 ,计算机会抛出**True**,很奇怪对吧？
- 所以为了避免以上不确定性发生，我们用 **===** 而不是 **==**
  - 因为 === 会检验左右两端的值(value)和类型(type)。
    `if (x === 0) { ... }`
- 还搞不清楚？那就用 **===**对了。

### 1.2 Javascript Object
JavaScript里的原始类型：
1. string
2. number
3. boolean
4. null
5. undefined
除此之外，其他所有的都是对象(object). _原文：All JavaScript values, except primitives, are objects._

其他Object篇章,略。详见[Javascript Object课堂PPT](../PPT课件汇集/week3/W03L08.pdf)



------------------------------------------------

## 2.0 DOM 文档对象模型
the Docment Object Model
### 2.1 定义
![DOM tree](../pictureOfSummarize/DOMTree.png)
1. Object based representation of an XML document.
2. Tree Structure
3. Provides a way for us to naviate a document in
Javascript.

### 2.2 DOM的使用
#### 2.2.1 用DOM来选择元素
1. 用 ID     只影响一个
   `var element = document.getElementByID('SomeID');`
2. 用 类名(className)   会影响一堆
   `var elements = document.getElementsByClassName('SomeClass');`
3. 用 标签名   会影响一堆
   `var elements = document.getElementsByTagName('sometag');`
4. 用CSS选择器     会影响一堆
   `var elements = document.querySelectorAll('p.class div i');`
5. Using an element we already have to get it's parent:
   `var parent_element = element.parentElement;`
6. Using an element we already have to get its children:
   `var child_elements = element.children;`

#### 2.2.2 用DOM来操控
1. 得到content
   ```javascript
   var text = element.innerText;
   var html = element.innerHTML;
   ```
2. 得到attributes
   `var attr = element.getAttribute('someattribute');`
3. Some attributes have their own direct values
   `var title = element.title;`
4. 直接操控style, 隶属CSS范畴
   `var color = element.style.color;`
5. 修改内容
   ```javascript
   element.innerText = 'Some <text>';
   element.innerHTML = 'Some <text>';
   ```
6. 修改attributes
   `element.setAttribute('someattribute', "value");`
7. Direct values don't work for all attributes:
   ```javascript
   element.title = "This title works";
   element.class = "may not work";
   ```
8. 直接设置style    _注意与4相比较_
   `element.style.color = "red";`

DOM大例：
```javascript
function byId() {
    var item = document.getElementById("demo");
    item.style.backgroundColor = "yellow";
}

function byClass() {
    var items = document.getElementsByClassName("test");
    for (var i=0; i<items.length; i++){
    items[i].style.backgroundColor = "yellow";
    }
}

function byTag() {
    var items = document.getElementByTagName("p");
    for (var i=0; i<items.length; i++){
    items[i].style.backgroundColor = "yellow";
    }
}

function byCSS() {
    var items = document.querySelectorAll("p#demo,span.test");
    for (var i=0; i<items.length; i++){
    items[i].style.backgroundColor = "yellow";
    }
}
```
### 2.3 操控DOM树例子
1. 创建新元素
   `var newElement = document.createElement('P');`
2. 把一个元素和另一个元素连接
   ```javascript
   var parent = document.getElementById('parent');
   parent.appendChild(newElement); 
   ```
3. 移除子元素
   `parent.removeChild(newElement);`

---

## VUE