
# JSON教程


## JSON 简介

JSON：Java Script Object Notation  

JavaScript对象表示法  

是一种轻量级的数据交换格式，类似XML。  

它基于ECMAScript（欧洲计算机协会制定的JS规范）的一个子集，采用完全独立于编程语言的文本格式来存储和表示数据。

在JSON出现之前，大家一直用XML来传递数据。因为XML是一种纯文本格式，所以它适合在网络上交换数据。XML本身不算复杂，但是，加上DTD、XSD、XPath、XSLT等一大堆复杂的规范以后，任何正常的软件开发人员碰到XML都会感觉头大了，最后大家发现，即使你努力钻研几个月，也未必搞得清楚XML的规范。

终于，在2002年的一天，道格拉斯·克罗克福特（Douglas Crockford）同学为了拯救深陷水深火热同时又被某几个巨型软件企业长期愚弄的软件工程师，发明了JSON这种超轻量级的数据交换格式。

### JSON与XML相同之处

> JSON是纯文本   
> JSON具有自我描述性  
> JSONN具有层级结构  
> JSON可通过JavaScript进行解析  
> JSON数据可使用AJAX进行传输  

### JSON与XML不同之处

> 没有结束标签  
> 更短  
> 读写速度更快  
> 能够使用内建的JavaSript eval()方法进行解析  
> 使用数组  
> 不适用保留字  

### 为什么使用JSON？

JSON 比 XML 更小、更快，更易解析。

并且，JSON还定死了字符集必须是UTF-8，表示多语言就没有问题了。

对于AJAX应用程序来说，JSON比XML更快更易使用。

## JSON语法

在JS语言中，一切皆为对象，因此，任何支持的类型都可以通过JSON 来表示。

JSON实际上是JavaScript的一个子集。



### 语法表示

JSON数据的书写格式`键/值对`形式

SON 键值对是用来保存 JS 对象的一种方式，和 JS 对象的写法也大同小异，键/值对组合中的键名写在前面并用双引号 `""` 包裹，使用冒号 `:` 分隔，然后紧接着值


```json
{"firstName": "Json", "secondName": "Script Object Notation"}
```

其等价于JavaScript语句：

```javascript
{firstName: "Json", secondName: "Script Object Notation"}
```

**JSON 是 JS 对象的字符串表示法，它使用文本表示一个 JS 对象的信息，本质是一个字符串。**

```javascriptvar
 obj = {a: 'Hello', b: 'World'}; //这是一个对象，注意键名也是可以使用引号包裹的
```

```json
var json = '{"a": "Hello", "b": "World"}'; //这是一个 JSON 字符串，本质是一个字符串
```


### 数据类型
- `number`：和JavaScript的`number`完全一致；  
- `boolean`：就是JavaScript的`true`或`false`；  
- `string`：就是JavaScript的`string`；  
- `null`：就是JavaScript的`null`；  
- `array`：就是JavaScript的`Array`表示方式——`[]`；  
- `object`：就是JavaScript的`{ ... }`表示方式。  


### number

JSON数字可以是整型或者浮点型

```json
{"age":20}
```

### boolean

JSON 布尔值可以是 `true` 或者 `false`：

```json
{"flag":true}
```

### string

```json
{"firstName": "Json"}
```

### null

JSON 可以设置 `null` 值：

```json
{"none":null}
```

### array

JSON 数组在中括号`[]`中书写,数组可包含多个对象：

```json
{
"sites": [
{ "name":"百度" , "url":"www.baidu.com" }, 
{ "name":"google" , "url":"www.google.com" }, 
{ "name":"微博" , "url":"www.weibo.com" }
]
}
```

对象 "sites" 是包含三个对象的数组。每个对象代表一条关于某个网站（name、url）的记录。

### object

JSON 对象在大括号`{}`中书写，对象可以包含多个键/值对：

```json
{"a": "Hello", "b": "World"}
```

## JSON对象
JSON 对象使用在大括号`{}`中书写。

对象可以包含多个 `key/value` 键/值对。

`key` 必须是字符串，`value` 可以是合法的 JSON 数据类型（字符串, 数字, 对象, 数组, 布尔值或 null）。

`key` 和 `value` 中使用冒号`:`分割。

每个 `key/value` 对使用逗号`,`分割。

### 访问对象值

使用点号`.`来访问对象的值:

```javascript
var myObj, x;
myObj = { "name":"json", "alexa":10000, "site":null };
x = myObj.name;
```

也可以使用中括号`[]`来访问对象的值:

```javascript
var myObj, x;
myObj = { "name":"json", "alexa":10000, "site":null };
x = myObj["name"];
```

### 循环对象

可以使用 `for-in` 来循环对象的属性

```javascript
var myObj = { "name":"runoob", "alexa":10000, "site":null };
for (x in myObj) {
    document.getElementById("demo").innerHTML += x + "<br>";
}
```

在 `for-in` 循环对象的属性时，使用中括号`[]`来访问属性的值：

```javascript
var myObj = { "name":"runoob", "alexa":10000, "site":null };
for (x in myObj) {
    document.getElementById("demo").innerHTML += myObj[x] + "<br>";
}
```

### 嵌套JSON对象

JSON 对象中可以包含另外一个 JSON 对象：

```json
myObj = {
    "name":"runoob",
    "alexa":10000,
    "sites": {
        "site1":"www.baidu.com",
        "site2":"www.google.com",
        "site3":"www.weibo.com"
    }
}
```

可以使用点号`.`或者中括号`[]`来访问嵌套的 JSON 对象。

```json
x = myObj.sites.site1;
// 或者
x = myObj.sites["site1"];
```

### 修改值
你可以使用点号`.`或者使用中括号`[]`来修改 JSON 对象的值：

```json
myObj.sites.site1 = "www.163.com";
// 或者
myObj.sites["site1"] = "www.163.com";
```

### 删除对象属性

我们可以使用 `delete` 关键字来删除 JSON 对象的属性：

```json
delete myObj.sites.site1;
delete myObj.sites["site1"];
```

## JSON数组

JSON 数组在中括号`[]`中书写。

JSON 中数组值必须是合法的 JSON 数据类型（字符串, 数字, 对象, 数组, 布尔值或 null）。

JavaScript 中，数组值可以是以上的 JSON 数据类型，也可以是 JavaScript 的表达式，包括函数，日期，及 `undefined`。

### 访问数组值

我们可以使用索引值来访问数组：

```json
{
"name":"网站",
"num":3,
"sites":[ "Google", "baidu", "Taobao" ]
}

x = myObj.sites[0];
```

### 循环数组

```json
for (i in myObj.sites) {
    x += myObj.sites[i] + "<br>";
}
```

```json
for (i = 0; i < myObj.sites.length; i++) {
    x += myObj.sites[i] + "<br>";
}
```

### 修改数组值

```json
myObj.sites[1] = "Github";
```

### 删除数组元素

我们可以使用 delete 关键字来删除数组元素：

```json
delete myObj.sites[1];
```

## JSON.parse()

JSON 通常用于与服务端交换数据。

在接收服务器数据时一般是字符串。

我们可以使用 JSON.parse() 方法将数据转换为 JavaScript 对象。

### 语法

```json
JSON.parse(text[, reviver])
```

参数说明：  
- text:必需， 一个有效的 JSON 字符串。  
- reviver: 可选，一个转换结果的函数， 将为对象的每个成员调用此函数。  

### 实例

我们从服务器接收到了一下数据

```
{ "name":"runoob", "alexa":10000, "site":"www.runoob.com" }
```

我们使用 JSON.parse() 方法处理以上数据，将其转换为 JavaScript 对象：

```javascript
var obj = JSON.parse('{ "name":"runoob", "alexa":10000, "site":"www.runoob.com" }');
```

解析完成后，我们就可以在网页上使用 JSON 数据了：

```html
<p id="demo"></p>
 
<script>
var obj = JSON.parse('{ "name":"runoob", "alexa":10000, "site":"www.runoob.com" }');
document.getElementById("demo").innerHTML = obj.name + "：" + obj.site;
</script>
```

运行结果

```
runoob：www.runoob.com
```

## JSON.stringify()

JSON 通常用于与服务端交换数据。

在向服务器发送数据时一般是字符串。

我们可以使用 JSON.stringify() 方法将 JavaScript 对象转换为字符串。

### 语法

```json
JSON.stringify(value[, replacer[, space]])
```

参数说明：  
- value:必需， 一个有效的 JSON 对象。
- replacer:可选。用于转换结果的函数或数组。  
> 如果 replacer 为函数，则 JSON.stringify 将调用该函数，并传入每个成员的键和值。使用返回值而不是原始值。如果此函数返回 undefined，则排除成员。根对象的键是一个空字符串：""。  
> 如果 replacer 是一个数组，则仅转换该数组中具有键值的成员。成员的转换顺序与键在数组中的顺序一样。当 value 参数也为数组时，将忽略 replacer 数组。  
- space:可选，文本添加缩进、空格和换行符。
> 如果 space 是一个数字，则返回值文本在每个级别缩进指定数目的空格，如果 space 大于 10，则文本缩进 10 个空格。space 有可以使用非数字，如：\t。

### 实例

我们要向服务器发送以下数据：

```javascript
var obj = { "name":"runoob", "alexa":10000, "site":"www.runoob.com"};
```

我们使用 `JSON.stringify()` 方法处理以上数据，将其转换为字符串：

```javascript
var myJSON = JSON.stringify(obj);
```

myJSON 为字符串。  
我们可以将 myJSON 发送到服务器：

```javascript
var obj = { "name":"runoob", "alexa":10000, "site":"www.runoob.com"};
var myJSON = JSON.stringify(obj);
document.getElementById("demo").innerHTML = myJSON;
```


## JSON使用

### 把 JSON 文本转换为 JavaScript 对象

JSON 最常见的用法之一，是从 web 服务器上读取 JSON 数据（作为文件或作为 HttpRequest），将 JSON 数据转换为 JavaScript 对象，然后在网页中使用该数据。

为了更简单地为您讲解，我们使用字符串作为输入进行演示（而不是文件）。

### JSON解析器

eval() 函数可编译并执行任何 JavaScript 代码。这隐藏了一个潜在的安全问题。

使用 JSON 解析器将 JSON 转换为 JavaScript 对象是更安全的做法。JSON 解析器只能识别 JSON 文本，而不会编译脚本。

在浏览器中，这提供了原生的 JSON 支持，而且 JSON 解析器的速度更快。

较新的浏览器和最新的 ECMAScript (JavaScript) 标准中均包含了原生的对 JSON 的支持。

## Python JSON

### JSON函数

使用 JSON 函数需要导入 json 库：

```python
import json。
```

- json.dumps() 将Python对象编码成JSON字符串
- json.loads() 将已编码的JSON字符串解码成Python对象

### json.dumps 

**Python转JSON**

json.dumps 用于将 Python 对象编码成 JSON 字符串。

#### 语法

```python
json.dumps(obj, skipkeys=False, ensure_ascii=True, check_circular=True, allow_nan=True, cls=None, indent=None, separators=None, encoding="utf-8", default=None, sort_keys=False, **kw)
```

#### 实例

以下实例将数组编码为 JSON 格式数据：

```python
import json

data = [ { 'a' : 1, 'b' : 2, 'c' : 3, 'd' : 4, 'e' : 5 } ]

json = json.dumps(data)
print json
```

以下代码执行结果为：

	[{"a": 1, "c": 3, "b": 2, "e": 5, "d": 4}]

使用参数让 JSON 数据**格式化输出**：

```python
import json
print(json.dumps({'a': 'Runoob', 'b': 7}, sort_keys=True, indent=4, separators=(',', ': ')))
# 
# {
#     "a": "Runoob",
#     "b": 7
# }
```

Python原始类型向JSON类型的转化对照表：

| Python         | JSON   |
| -------------- | ------ |
| dict           | object |
| list,tuple     | array  |
| str,unicode    | string |
| int,long,float | number |
| True           | true   |
| False          | false  |
| None           | null   |


### json.loads

**JSON转成Python**

json.loads 用于解码 JSON 数据。该函数返回 Python 字段的数据类型。

#### 语法

```python
json.loads(s[, encoding[, cls[, object_hook[, parse_float[, parse_int[, parse_constant[, object_pairs_hook[, **kw]]]]]]]])
```

#### 实例

以下实例展示了Python 如何解码 JSON 对象：

```python
import json

jsonData = '{"a":1,"b":2,"c":3,"d":4,"e":5}';

text = json.loads(jsonData)
print text

# 
# {u'a': 1, u'c': 3, u'b': 2, u'e': 5, u'd': 4}
```

json 类型转换到 python 的类型对照表：

| JSON         | Python   |
| ------------ | -------- |
| object       | dict     |
| array        | list     |
| string       | unicode  |
| number(int)  | int,long |
| number(real) | float    |
| true         | True     |
| false        | False    |
| null         | None     |





