### 命名 : 大小写要注意区分

### 引入script标签以标签方式引入src

### $$ 这个不会再代码中出现, 但是浏览器环境里有

等价于querySelectorAll

```js
$$("*")//找到页面所有的元素
```

## 判断是不是NaN

```js
isNaN(NaN)//true
```



### 弹窗事件

#### 	alert弹出内容

#### 	confirm判断弹窗

#### 	prompt输入弹窗

focus: 表单输入框聚焦

```js
input.focus()
```



### 控制台输出console.log()

### 输出打开的内容console.dir()

#### document:整个页面的代码内容

.style样式名称

```js
document.querySelector("demo").style.backgroundColor="red";
```

### 鼠标事件

#### 	onclick:左键单击

#### 	ondblclick:左键双击

#### 	**onmouseenter**/onmouseover:鼠标移入

#### 	**onmouseleave**/onmuseout:鼠标移出

#### 	onmousedown:鼠标按下

#### 	onmouseup:鼠标抬起

#### 	onmousemove:鼠标移动

#### 	oncontextmenu:右键单击

#### `onmousewheel` :鼠标滚轮

### 元素的标签内部

#### innerHTML:会解析标签

#### innerText:全部为字符添加,存文本

### 数据类型

#### 数值(Number)		

12 , 32 , 3.1232,...
分为整数和浮点数
二进制: 0b100
八进制: 0开头
16进制是 0x打头
数值范围很大但是不是无限当一个数超过约1.79e+308的数时浏览器无法处理自动转换成infinity 正无穷, 也有负无穷
一些小数只能在内存中逼近 , 觉不能达到
可以  +  -  * /

##### 特例的数NaN(不是一个数)但属于数值

#### .toFixed() 方法 取小数点几位

会四舍五入

```js
let a = 12.321
console.log(a.toFixed(1))//12.3
```

#### parseInt()数值转换

传两个数值
	一个是转换的数值
	二是要解析的进制
只写一个数值是取整

```js
parseInt("23.2342")//23
parseInt("100",2)//4
```

#### parseFloat()浮点类型

会去解析一个字符串, 根据结果返回数
传入的可以是任意类型 但是在内部转化

#### 字符串(String)

**不是对象**但是可以使用对象的方法

##### length  长度

字符串是可以挨个获取他的字节 : 
用.length判断有多**长**
返回长度

```js
let are = "1234"
are[0]//是1
are[1]//是2
//
are.length//3
```

##### charAt 获取下标

兼容IE6,7,8

获取字符串中得下标得值
返回字符串下标得值，下标从0开始

```js
let str = "asdf";
str[0];//"a" 低版本ie不兼容
str.charAt(0);//"a"
```

字符串的定义 :

可以支持小数 向下取整
不存在返回 空字符串 ""

"asdadqw",‘123123’,"你好",... 

是**没有特殊含义**的*字母*或者*汉字*或者是其他的符号
写字符串时注意引号问题 引号是成对出现的如果需要出现多个引号则需要转义字符:\ 引号就近寻找	推荐使用双引号
字符串使用+ 加法 会拼接两个字符串拼在一起
box = box + str可以简写为: box += str

```js
let str = "I say:\"I'm ok!\"";
```

##### 拼接concat或+  

不会改变原先的值

```js
let str1 = "asd",
    str2 = "fgh"
let str3 = srt1.concat(str2,"j")//"asdfghj"
let str  = str1.concat("s","g")//asdsg
let str4 = str1+str2+"j"//"asdfghj"
```

##### 查询字符是否存在indexOf

存在就返回下标 不存在返回-1
多个查询只会显示第一个

```js
let str = "asd"
str.indexOf("a")//0
str.indexOf("E")//-1
```

可以自定义第几位开始查

```js
let str = "asadsd"
str.indexOf("d",2)//3
```



##### 返回最后一个字符的下标lastIndexOf

从结尾开始查找

```js
let str = "哈喽"
str.lastIndexOf("喽")//2
```

也可以自定义倒数第几位查询

##### charCodeAt 转换成unicode编码

减少编码出错

```js
let str = "银时";
str.charCodeAt(0);//38134
str.charCodeAt(1);//26102
```

##### String.fromCharCode 转换unicode编码

```js
String.fromCharCode(38134)//银
```

##### slice 字符串裁剪

从哪里开始减 到 剪到那里
左边包含右边不包含

```js
"asddsa".slice(2, 4)//dd
"asdfgh".slice(2)//dfgh
"asdfgh".slice()//asdfgh
```

第一个参数可以写负数
-1 表示 最后一个字符

```js
let str = "asd"
str.slice(-3, 2)//"as"
str.slice(-3)//"asd"
```

##### substring 起始下标 结束下标 (标识下标截取)

完全等价于 slice
**不可以** 取负数

##### substr (截取长度)

​	起始下标 , 截取长度  **长度不能为负数**

```js
let str = "asdf"
str.substr(1,2)//"sd"
```

##### split  字符串切分 

最终形成数组
以传入的字符串作为分隔 , **切分字符串** 
字符串当中但凡遇到 **传入的字符串**  都会切掉

```js
let str = "width:300px;height:300px;"
let styleArr = str.split(";")//["width:300px","height:300px"]
```

可以传两个参数第二个是个数

##### replace  查找 替换

第一个参数是查找 第二个是要替换的内容
替换满足条件的**第一个**(多个要用正则)
传一个是替换为undefined

```js
let str = "I love you"
str.replace("o" , "h")//"I lhve you"
str.replace("o")//"I lundefined you"
```

###### 可以传正则

```js
let str = '河北真是一个好地方'
let r = /河北/g
str.replace(r,'北京');
```

第二个参数可以传函数

```js
let str = '哈哈哈www'
let r = /11/
str.replace(r,()=>{
    //第一个参数是 每次匹配的整体内容
    //第二个参数是 第一个子项
    //第三个参数是 第二个子项
})
```



##### trim 清除字符串开头和结尾的空格

```js
let str = "  asd   "
str.trim//"asd"
```

##### .toUpperCase 全部转换为大写

##### .toLowerCase  全部转化为小写

##### eval 方法 对传入字符串进行JS解析

是个函数  尽量不要使用 , 可能被用户利用

```js
eval("3+2")//5
```



ES6中的反引号:  ``功能强大

模板字符串 :可以换行，字符串拼接${变量}

```js
let name = "名字"
let str = `我叫${name}`
```

##### .includes() 方法

查找字符串里有没有传的参数

```js
console.log("asd",includes("asd"))//true
console.log("asd",includes("ad"))//false
```

##### startWith/endWith 以什么开始以什么结束

传入字符串

```js
"asd".startWith("asd")//true
```



##### .repeat() 重复多少遍

```js
"asd".repeat(2)//"asdasd"
```



#### 布尔值(Boolean)		

true,false
只有两个数值:真 / 假

#### 未定义(undefined)	

undefined

声明了一个变量但是没有赋值那么这个变量就是 未定义
访问不存在的对象属性

#### 空(null)				

null
将一个变量定义成 空 的对象
是一个单独的类型也是单独的值
不能添加任何属性 , 独立的类型
使用场景: 声明一个null的占位符数值, 保证数据类型的统一

```js
let ob=null;
typeof (ob);//"object"
```



#### 定义变量 let/var : 可以修改

let : 声明的变量只在大括号(代码块的范围内有效)

#### 定义常量 const : 不能修改通常情况下用大写定义

#### 	对象类型 var object

​		**万物皆对象**  **属性名只能是字符串**

​	JS存储方式 : 看内存地址

​		var ob ={"x":"hello world","y":"文字"}一个属性或子变量对应一个值
获取的话是  ob."x"
一个具有各种属性的物体叫对象

​	当我们使用对象的时候 , 对象之间的传值不是复制 , 而是地址的引用

* 查询
  1. 对象.属性名   直接访问的是属性名的字符串
  
2. 对象[]  访问对象中变量对应字符串的值 , 中括号里添加这个属性名的字符

##### 数组里面获取数组的长度用.length   delete删除

```js
 let obj = {
     name:"银时",
 }
 console.log(obj.name)//银时
 console.log(obj["name"])//银时
 //----------------------------------
 let key = "name"
 console.log(obj[key])//银时
 //----------------------------------
 let key1 = "na"
 let key2 = "me"
 console.log(obj[key1 + key2])//银时
```


​     

*  增加 : 后期添加

  1. 可以通过. 方式添加
  2. [字符串 , 或者表示字符串的变量]
	```js
	let person ={
	    "name" :"名字",
	    "age":18
	}
	person.sex ="male"//person = {name:"名字",age:18,sex:"male"}
	person["friend1"] = "万章"
let key = "friend2"
  person[key] = "阿飞"
  ```
  
* 修改属性: 和增加一样

  ```js
  let obj = {age:18,}
  obj.age = 19
  obj["age"] = 20
  ```

  删除: 减少一条属性

  * delete 跟上空格 跟上删除属性

  ```js
  let obj = {
      friend1:"朋友",
      age:18,
  }
  delete obj["friend1"]//obj{age:18,}
  ```

  

##### 注意避免一个变量出现多种状态

##### Object.is()比较两个参数

传两个参数 这两的参数进行比较
不会进行类型转换

```js
Object.is(0,0)//true
Object.is(+0,-0)//false
```

默认不传数值是undefined

可枚举:可以通过for in**进行遍历的属性**

##### Object.keys() 以数组的方式显示属性名

将属性名以数组的形式返回

```js
let a = {a:1,b:2}
Object.keys(a)//["a","b"]
```

##### Object.values 遍历可枚举属性值

将属性值以数组的形式返回

```js
let a = {a:1,b:2}
Object.values(a)//[1,2]
```

##### Object.entris() 每一对输入的对象 以数组方式展示

```js
let a = {a:1,b:3}
Object.entris(a)//[a,1] [b,3]
```

##### Object.create() 生成对象

传入的值作为非常纯粹的值

```js
Object.create(null)//{}这个对象没有属性
```

没有任何属性不可枚举属性也没有
以传入的参数为原型创建一个对象
如果为null 创建一个没有原型的对象
**只能传入对象和null**
创建了的在__ proto __里面

##### Object.assign() 拷贝 合并操作

将你有我没有的方法添加进来
将你有我有的方法,把我的覆盖
我有你没有的不管
传两个值
将后面的值覆盖到前面

```js
let a = {a:2,b:3,c:4}
let b = {a:1,b:2,e:5}
let result = Object.assign(a,b)//{a:1,b:2,c:4,e:5}
console.log(a)//{a:1,b:2,c:4,e:5}
result === a//true
```

##### Object.defineProperty() 属性私有化不能查看

设置的值是不可枚举不可修改的
传三个
一:对象
二:要设置的属性名
三:属性特点

```js
let obj = {}
Object.defineProperty(obj, "propsl", {
    get: function (){
        return num
    },
    set:function (val){
        num = val
    }
})
```
value:这个属性值是多少
enumerable 属性是否可枚举无法重新定义configurable 控制
writable 属性值是否可修改
configurable 这个值设置了是否锁死 默认false 可枚举属性是否可修改

```js
let obj = {}
Object.defineProperty(obj, "propsl",{
    value:3,//值
    enumerable:true,//可枚举
    writable:true,//属性可修改
})
```

**一旦使用了get/set 后面**的value/enumerable/writable/configurable**没办法修改**

##### 深拷贝

将对象完全复制下来, 两者之间没有关系

###### 方法一:面试不要答这个

`Json.stringify()`转化成一个可以转换成数组的字符串
`Json.parse() `再次转换为数组

```js
let a = [1,2,3]
let b = Json.parse(Json.stringify(a))
```



#### 	数组类型 var ar

​		var ar =["hello","文字"]可以直接写值
获取值  ar[0]

##### length 方法  长度

返回的是数组的长度

```js
let arr = [1,2,3]
arr.length//3
```

##### .concat()方法  数组拼接

传入若干个参数 在尾部拼接

```js
let arr2 = [4,3]
let arr = [1,2]
arr.concat(1,2,3)//[1,2,1,2,3]
arr.concate(1,2,arr2,2)//[1,2,1,2,4,3,2]
```

**不会改变原数组**

##### forEach方法 显示每一项 遍历操作

只有数组有

数组遍历操作

接受三个参数
          item => 数组里面的每个元素
          index => 数组下标
          arr => 数组本身整体

```js
let arr = [1,2,3]
arr.forEach(function(item){
    console.log(item)
})
//1
//2
//3
```

```js
let arr = [1,2,3]
arr.forEach(console.log)
//1 0 [1,2,3]
//2 1 [1,2,3]
//3 2 [1,2,3]
```

```js
console.log([1,2,3])
console.log.apple(console, [1,2,3])//1  2  3
```

###### 类数组执行解决

call

```js
let str = "asd"
[]forEach.call(str,function(iten,index){
    console.log(iten)
})//a s d
```

函数接受**三个参数**
1.**指元素本身**
2.**元素的下标**
3.**数组本身**

##### .push()方法  最后一位生成数值

执行过后返回数组**最终的**参数**长度**
在数组最后一位生成数值

```js
let arr=[]
arr.push(0)//返回1 数组是[0]
arr.push(1)//返回2 数组是[0,1]
arr.push("asd",123)//返回4 数组是[0,1,"asd",123]
//在数组的最后一位生成数值 并返回数组添加后的数组长度
```

##### .pop() 方法 删除最后一个元素

执行过后**返回被删除的元素**
1.数组最后一个元素
2.数组被删除的元素返回出来 , 供后续使用

```js
let arr = ["1","2","3"]
arr.pop()//返回"3"  数组是["1" , "2", "3"]
//删除数组最后面的值 最后会返回被删除的值
```

##### .unshift() 方法 在开头添加数值

返回数组的**最终长度**
添加的时候,整体添加 **不会颠倒顺序**

```js
let arr = ["大","家","好"]
arr.unshift(1)//返回4 数组是[1,"大","家","好"]
```

##### .shift() 方法 从头开始删除

执行过后**返回被删除的元素**
1.数组最后一个元素
2.数组被删除的元素返回出来 , 供后续使用

```js
let arr = ["1","2","3"]
arr.shift()//返回"1" 输出["1","2","3"]
```

**数组删除操作 , 请用length判断数组是否没有内容了**

##### .reverse 数组翻转

返回数组翻转的结果

```js
let arr = ["1","2","3"]
arr.reverse//["3","2","1"]
```

##### .slice 裁切

切数组返回数组
**不会改变原数组**
跟字符串里的差不多

##### .splice 数组里最强大的剪裁添加

最少添加一个元素
1.表示数组的操作位置(必写)
2.表示删除几位
3.表示在这个被参数的位置添加若干个参数

能对数组在任意位置(删除任意一个元素)或者(添加任意个元素)

```js
let arr = [0,1,2,3,4,5,6,7,8]
arr.splice(3,3,"一","二","三")
//返回[3,4,5] 输出[0,1,2,"一","二","三",6,7,8]
let aerr = [0,1,2,3]
aerr.splice(0,0,3)
//返回[] 输出[3,0,1,2,3]
```

**我们没有办法跳过中间参数直接传后面参数** 

可以用正则

##### .fill() 方法 全部添加

全部填加一个数字

```js
let arr = new Array(4).fill(0)//[0,0,0,0]
//创建一个长度为4的数组 并全部添加为0
```

##### `.concat` 数组拼接

```js
let a = [1,2,3], b = [2,3,4] ,c = [6,7,8,9]
a.concat(b,c)
```



##### .join() 方法 数组转字符串

执行完成之后返回字符串
不传参数会自动将元素自动拼接到一起以 , 分隔拼接成字符串

```js
let arr = ["1","2","3","4"]
let str = arr.join()
console.log(str)//1,2,3,4
```

括号里传的参数是以**这个参数进行拼接**

```js
let arr = ["1","2","3","4"]
let str = arr.join("&")
console.log(str)//1&2&3&4
```

##### .sort() 方法 数组排序

将数组的内容进行排序
**字符串顺序排序**
**根据ASCLL码进行排序**
空字符串 < 数字 < 大写字母 < 小写字母

```js
let arr = ["12","123","0","1234","23"]
arr.sort()//["0",12","123","1234","23"]
```

sort 方法和forEach类似  **可以传一个参数**
这个参数是一个**比较函数**
接受两个参数 表示前一个和后一个关系
返回 大于0或小于0的内容
当返回 大于0时 是顺序 排列
前 - 后  从小到大排列
后 - 前 从大到小排列

```js
let arr = [1,2,3,4,22,11,44,55,33]
arr.sort(function(a,b){
    return a - b//从小到大[1,2,3,4,11,22,33,44,55]
})
```

##### Array 生成数组

参数不一样会进行**不同的操作**,
只有一个参数且是数字时, 返回那个**数字长度的空数组**
多个参数挨个传入生成数组

##### Array.from()类数组转换为数组/ES6

传类数组帮你**转换为数组**
传入第二个参数, 对数组挨个运算 , 
返回类型是统一的绝对返回数组
如果传入一个类似数组的对象那么对象里面要加length属性

```js
let obj = {
    0:"a",
    1:"b",
    asd:"dsa",
    length:3
}
console.log(Array.from(obj))//["a", "b", undefined]
//
console.log(Array.from(obj, item => item+1))//["a1", "b1", NaN]
//
```



##### Array.of()

传入几个就生成数组的几项

```js
Array.of(1,2,3,4)//[1,2,3,4]
Array.of(1)//[1]
```



##### every()只要有false就返回false

如果回调函数都返回true , 就返回true
只要有一个false 就返回false

```js
let arr = [1,4,2]
let boole = arr.every(item => item > 0)//true
let arrList = [1,-4,2]
let flag = arr.every(item => item > 0)//false
```

##### some()只要有true返回true

```js
let chan17 = [
    {
        name:"asd",
        sex:"女"
    },
    {
        name:"大",
        sex:"男"
    },
    {
        name:"打发",
        sex:"男"
    },
]
let ans = chan17.some(student =>{
    return student.sex === "女"
})
console.log(ans)//true
```

##### filter() 方法 筛选

筛选满足条件的元素 , **创造个数组返回**
返回真就返回当前的返回值
满足条件的元素单独提出来

```js
let chan17 = [
    {
        name:"asd",
        sex:"女"
    },
    {
        name:"大",
        sex:"男"
    },
    {
        name:"打发",
        sex:"男"
    },
]
let boys = chan17.filter(getBoys)
function getBoys(item){
    return item.sex === "男"
}
//boys
[
	{
        name:"大",
        sex:"男"
    },
    {
        name:"打发",
        sex:"男"
    },
]
```

##### map() 方法 数组的每一项进行操作形成一个新的数组

操作每一项 , 最后**打包成数组**

```js
let arr = [1,2,3,4]
let newArr = arr.map( num =>{
    return Math.pow(num, num)
})
```

##### reduce() 方法 对数组进行合并(迭代)操作 , 返回迭代结果

接受**两个参数**
	1.回调函数
		回调函数接受四个参数
			1.每次迭代的迭代体
			2.当前项
			3.下标
			4.原数组
	2.初期迭代体

```js
let exam = [1, 2, 3, 4, 5]
let result = exam.reduce(function (sum, item, index, srr){
    return sum + item
},0)//15
```

sum是后面传入的0 , 下一次sum是返回的东西

##### keys() 方法 返回迭代体接口 下标

方便for...of
```js
for(i of [1,2,3].keys()){
    console.log(i)
}//0 1 2
```
##### value() 返回迭代体接口 值
```js
for(i of [1,2,3].value()){
    console.log(i)
}//1 2 3
```

##### entries() 返回迭代体接口 [下标值]
```js
for(i of [1,2,3].entries()){
    console.log(i)
}//[0,1] [1,2] [2,3]
```

##### find()方法 对数组每一个进行判断只要满足就返回

```js
let arr = [1,2,3]
arr.find(item => item > 1)//2
```

数组每一项进行判断只要满足就返回那个数值

##### findIndex()方法 每一个判断返回下标

```js
let arr = [1,2,3,4]
arr.findIndex(item => item > 2)//2
```

判断数组里的每一项只要满足就返回这个数值的下标

##### get/set 对象拓展

访问这个属性时返回函数执行的结果
get获取
set设置

```js
let obj={
    _value:0,
    get value(){return this._value},
    set value(val){this._value = val}
}
console.log(obj.value)//0
console.log(obj.value(3))//3
```

#### Symbol数据类型

每次创建都会是一个独一无二的东西
用于对象的扩展

简单的使用

```js
let a = Symbol()
```

在对象中创建了多个属性
如果在创建一个属性 很难知道重复了没有
在这里用到了`Symbol` 

```js
let o = {
    x:1,
    y:'1',
    g:'eee',
    e:'134'
}
let x = Symbol()
o[x] = 123;
```

在`Symbol` 里面可以传入一个数据 表示描述

```js
Symbol('一个Symbol')//Symbol(一个Symbol)
```



### json

强大 统一了**数据格式**，用它和**后台进行交互**
JSON不是对象，也不能说是字符串 他**是一种数据格式**
后端返回的数据一般是JSON 字符串，转码
可以作为配置而存在
不能写函数，undefined
只能有唯一的 数组或者是对象

### typeof操作符(不是函数)

判断是属于什么类型

使用方法:

#### typeof(变量)

#### typeof 变量

```js
typeof(变量);//或
typeof 变量;
typeof(123);//"number"
typeof("asd");//"string"
typeof(true);//"boolean"
typeof({});//"Object"
typeof(undefined);//"undefined"
typeof(null);//"object"，指未被赋值的初始化对象
typeof(function a(){});// "function"
typeof(Symbol(123));//"symbol"
```

### 获取元素的方式

#### document.querySelector() ES6

参数是css选择器来的
选中满足条件的第一个元素

#### document.querySelectorAll() ES6

满足条件的所有元素
返回一个集合：多个元素组的物体

#### document.getElementById()  ES5

通过Id名获取元素
传入的参数是一个ID名不需要添加#

#### document.getElementsByClassName()

通过类名选择多个元素
传入参数是class
不管选中了多少个,返回的是一个数组, 没有选中也是数组

#### document.getElementsByTagName()

通过标签名选中元素
也是数组

document.getElementsByName()

通过name属性选择元素

### 函数和自定义属性

#### function.prototype所有函数的母体

#### 	1.函数 先声明再调用

属于object基本类型

**以英文小写字母开头函数执行**

* ​	函数是将一系列代码或者操作行为打包到一起形成的东西 ,一块有特定功能的代码
  写法 : 

  ```js
  function fun(){
      //代码内容.
  }
  ```

  function: 创建一个函数.   fun: 函数名称
  其中函数名 相当于变量  函数名可以起任意名字单见名知意

* 函数分为两种

  1. 具名函数 : 拥有名字 , 能通过函数名调用
     有函数名的函数就是具名函数

  2.  匿名函数 : 没有名字的函数 ,不能单独写出来 ,无法调用
      除非负值给变量或是触发执行或是立即执行.

     ```js
     function foo(){}//具名函数
     document.onclick = function(){};//匿名函数
     ```

  3.  立执行函数 : 立马执行
  保证代码的安全性 , 和减小污染
      
      ```js
      (function () {console.log("这是匿名函数")}())
      ```
  ```
  
  只输入函数名表示的是函数本身
  输入函数+()返回的是函数的返回值
  ```
  
* **函数的执行: 函数名+()**
  **函数执行之后会有返回值**
  **就算不写也返回undefined** 

  ```js
  function foo(){
      console.log(1)
  }
  foo()
  //--------------------------
  box.onclick = foo//点击box执行函数foo
  //立执行函数
  (function () {console.log(1)}())
  ```

  

* 函数写完后需要调用 也就是叫他名字

  * 执行函数:  函数名()
  * 调用一次执行一次

* 函数的传参: 

  ```js
  let sum = 1000
  function add(num){
      sum += num
  }
  console.log(sum)
  ```

  

  * 函数名后面的小括号就是可以穿入参数
    让代码执行的时候会有不同的情况

  * 函数执行的过程中括号里的参数可以使任意类型
    是实参

  * 函数在  **声明**  的过程中**传入**的参数是**形参**
    如果实参不穿默认是undefined

  * 函数  **调用** 的时候传的参数是**实参**
    function say(实参){代码块儿}

    ```js
    function say(实参){console.log(`我今天得心很好`)}
    say("形参");//"我今天心情很好"
    ```
    
  * 如果调用的实参多了怎么办:
    多了直接消失

  * 如果声明的形参多了怎么办 : 
    形参会有默认的nudefined

* 实参也可以写函数

  ```js
  function privateFunction(){
      concole.log("一段字")
  }//声明一个函数打印一段字
  function callFunction(cd){
      cd()
  }//声明一个函数并传入一个实参cd 并执行函数cd
  callFunction(privateFunction)//一段字
  ```

  

* 函数的返回
  
  * 默认有返回 , undefined
    可以手动返回内容: return  返回
    可以返回对象
    
  * 可以返回函数
  
    ```js
    function createAdd(){
        let sum = 0
        return function (num){
            return sum += num
        }
    }
    let add = createAdd()//控制台输入 add(12):返回12,在输入add(10):返回22
    ```

* ES6 语法 箭头函数
  是函数,  比普通函数简单

  ```js
  let sum = (a,b) => (a + b)//等价于下面的函数
  function sum(a,b){
      return a + b
  }
  ```

  1. function删除
  2. 函数名后面写等号
  3. 函数和代码块之间写 =>

  特殊情况：当只有一个参数的时候括号可以删除
  如果没有参数，括号不能删除
  如果代码只有一句并且是返回时后面的大括号可以变成小括号
  并且return可以删除

  ```js
  let a=2
  let foo1 = n => (a*a)//n可以删除括号
  ```

#### 2. arguments   ES6 函数的默认形参

ie8以下不行

​	**相当于对象但不等于**
​	一定要在函数内部使用
​	相当于数组，可以进行数组遍历操作

##### 	callee

​	就是当前函数

```js
function foo(){
    console.log(arguments.callee)
}//function foo(){
//    console.log(arguments.callee)
//}
```

##### 	剩余参数

**...** 只能写在形参里的最后一个  "..." 是剩余参数
​	剩余参数  前面不要 **只要剩下的**
​	手动打包后续内容
​	转换成为一个数组

```js
function foo1(a, b, ...restAll){
    console.log(a, b, restAll)//
}
foo1(1,2,3,4,5)//1 2 [3,4,5]
```

#### 3. 箭头函数  ES6

​	没有 arguments
​	有剩余参数
​	this问题
​		**不会根据调用函数的主体对象来**
​		**根据外部的this来** , 在声明位置**强制绑定上下文**

​	不能被 call/apply/bind 修改

​	有默认值

```js
let foo = (x = 0, y = 0) => {
    return x + y
}
foo(1,2)//3
```

#### 4.函数的this (函数才有)

this 指代某个东西
**this就是调用函数的主体对象**
是一个关键词

谁点它执行  this就指向谁
**谁调用它 this就指向谁** 
对象调用它 this就指向谁
function foo(){}**完全等价于**window.foo

如果没有明确的调用主体，那就是window干的

function(){}: 在内部，**this默认指向调用的函数**
可以被 call/apply/bind  修改

()=>{} 箭头函数 : 直接**绑定到**箭头函数**书写的位置**的 this
在考虑this 的时候, **箭头函数不是函数**
不能由  call/apply/bind  修改

##### 修改this指向的问题 : call apply  bind

**call**

```js
let person = {
    name: "名字",
    sing:function say(){console.log(this.name)}
}
let rabot = {
    name: "rabot"
}
person.sing.call(rabot)
//this 指向到rabot对象
```

###### 打印类型

```js
console.log( ({}).toString.call([]) )//[object Array]
```

第一个参数是**调用的主体对象**
后续参数和原函数一样

```js
function foo(a,b,c){
    console.log(this, a, b,c)
}
let obj4 = {}
foo.call(obj4, 1,2,3)//{} 1 2 3
```

**apply**

方法和call 一模一样
以数组方式传递

(传入的是绑定的数据 , 数组)

```js
function foo(a,b,c){
    console.log(this, a, b,c)
}
let obj4 = {}
foo.call(obj4,[1,2,3])//{} 1 2 3
```



**bind**

大多数用于函数
改变函数的`this`不执行函数

也是修改this指向的方法
传参和call一样

但是bind
1.不执行
2.返回一个this已经绑定好了的函数
3.这个函数在任何时候执行 内部的this都已经绑定好了

```js
function foo(a, b, c){
    console.log(this, a, b, c)
}
let obj1 = {}
let bindObj1foo = foo.bind(obj1, 1, 2, 3)
bindObj1foo//function foo(a, b, c){console.log(this, a, b, c)}
bindObj1foo()//{} 1 2 3
```

#### 函数拓展

##### 尾递归

本质还是递归 在return时不返回表达式 , 会返回一个执行函数
运行逻辑: 浏览器回去优化 先去删除外部的作用域, 然后用return这个函数
以参数的形式存储结果

```js
function foo(n,num=1){
    if(n===1) return num
    return foo(n-1,n+num)
}
//
```

##### 纯函数

输入一定 输出一定 , 不会对外界做出任何改变
不会对外部产成功影响
对数据进行加工 , 返回计算结果

```js
let arr=[1,2,3,4]
arr.filter(item=>item>2)//[3,4]
arr//[1,2,3,4]原数组没有改变
```



##### 偏函数

核心在于参数

```js
function clearStyle(dom){
    return function (border){
        return function (value){
            dom.style[border]=value
        }
    }
}
```

##### 柯里化

把接受多个参数的函数变换成接收单一参数的函数
链式调用: 核心  调用的时候返回封装好的对象 , 函数执行的时候返回this

##### 反柯里化

某个特殊情况下才能生效的代码
对函数进行拆解变形 生成一个新的函数
任意函数都生效

### 自加 a++

a++和++a的区别
a++先返回再去增加

++a先自己增加再返回

### 控制流程

#### if  假如 提出一个假设(条件)

通过表达式进行计算
简单的判断表达式
">":符号左右两边进行判断  true/false

"==": 等于  "!=":不等于

   else  关键词 : 否则

   ​	和if成对出现   写在if 代码块之后

   ```js
   function checkNumber(pointer){
       if(pointer >= 80){
           return "奖励"
       }else if (pointer >= 60) {
           return "试卷一份"
       }else if (pointer >= 30) {
           return "课后补习"
       }else {
           return "下期见"
       }
   }
   ```

   

#### switch  case  break

也是条件判断: 

```js
let jiangjuan = "一等奖"
switch (jiangjuan) {
    case "一等奖":
        console.log("颁发一等奖")
        break
    case "二等奖":
        console.log("颁发二等奖")
        break
    case "三等奖":
        console.log("颁发三等奖")
        break
    default :
        console.log("下次再来")
}
```

#### 三目运算符

* 只能跟单条语句

* 本质上是一个if ...else

* 语法格式
   expression?sentence1:sentence2
   如果expression的值是真，返回冒号前面的

   ```js
   true?1:2//1
   light = (light == "on")? "off":"on"
   ```


#### 循环的三种写法 for/while/do while

​	计算机的特性之一：能准确无误的完成大量重复性的工作。
​	在JS代码中我们可以用循环的方式多次执行同一个代码块,循环的方式有三种：

##### for

*  for循环 : 用于控制循环次数的循环方法
单线程代码 :  在同一时间只能处理单独一条语句
  
  ```js
  for(let i = 0;i < 10;i++){
      console.log(`我是第${i}次执行的`)
  }
  /*其中，for(A;B;C){
  	D;
  }
  A: 循环开始前的初始化操作
  B: 循环的结束条件判断，如果是真，则继续循环，如果是假则退出循环
  C: 单次循环完成之后的状态叠加或者改变
  D: 可以填写若干条被循环的代码
  */
  ```
```
  
  for循环的打断和跳过
  continue : 跳过这次循环直接到达第三个语句	
  break : 一旦执行到break , 循环直接不执行
  
  **注意在for循环中b是最重要的 , 没有结束条件的话页面将进入死循环**

##### while

* while循环: 和for循环基本一致 , 但没有初始化操作和循环状态的改变

  ```js
  let a = 0
  while(a>2){
      console.log(2)
      a = a+1
  }
  /*其中 while(A){
  	B;
  }
  A: 每次(包括第一次)循环开始的判断
  B: 循环的若干代码
  */
```

##### continue : 跳过这次循环

##### break : 一旦执行到break , 循环直接不执行

#####   while可以转换成for循环

当满足条件时, 就执行代码

```js
while (false){
    console.log(666)
}
```



##### for...in 数组遍历 遍历属性名

可以遍历数组甚至对象 : 访问每一个课枚举 属性

```js
let arr = ["a", "s", "d"]
for(let i in arr){
    console.log(i)
}// 0  1  2
let obj = {
    "a":"a1",
    "b":"b1",
    "c":"c1",
}
for(let i in obj){
    console.log(i)
}//a  b  c
for(let i in obj){
    console.log(obj[i])
}//a1  b1  c1
```



##### for...of 遍历每一项的值

只能遍历那些可数(iterable 可迭代) 的东西
**不可迭代就不能用**
能遍历**数组** **类数组** **字符串**

```js
for(let i of "asd"){
    concole.log(i)
}//a  s  d
```

对 对象的使用

```js
let obj = {x:1,y:'1',g:'ee'}
for(let x of Object.entries(obj)){
    console.log(x)
}
//这个x是一个数组 for of 遍历出每一个属性和值
["x", 1]
["y", "123"]
["g", "eee"]
```



##### do while

* do while : 先做一次在进行判断

  ```js
  do{
      console.log
  }while(false)
  ```

### 运算符

#### 逻辑运算符

转换为布尔值: Boolean()
0   ""  undefined  null  NaN  : 都为true

##### 逻辑与&&

* &&
  前面的内容为真 , 返回后面的内容
  a&&b:如果a的结果为真，则返回b，否则返回a
  A?B:A   对A进行判断为真就返回B

##### 逻辑或||

*  ||
  A 真 返回A
  A 假  返回后面内容
  A?A:B

##### 注意 : 优先级

&&(或)优先级高于||
true || true  &&false  // true

##### 非表达式 : !

* !
  取反操作
  强制转换布尔类型再去反
  比如  !obj == true  翻译 : obj真的不存在 , !obj == false  翻译 : obj存在
* !!  两个感叹号
  强制将值 转换为布尔值

##### 算数运算符: "+" "-" "<" ">" "==" "==="

* "+" "-" "*" "/"
  "+" : 适用于字符串运算表示拼接
*  "++" "--"自加和自减
  符号在前 先运算再赋值 
  符号在后  先赋值再运算
* 比较运算 "<" ">" 
  字符串比较 : ASCII码比较
  "0"  48
  "A"  65
  "a"  97
  布尔值类型转换
  true >false
* ==  相等 : 转化后判断
  存才数据类型转换
* ===  全等 : 完全一致
  值一致并且类型一致
* =  赋值操作 : 右边 传递给 左边
* != 不相等 : 参考上面的相等取反
* !==  不全等 

### 数据类型转换

#### 1. 布尔类型Boolean()

转换方法: Boolean函数传入变量  返回对应布尔值

1.  Number 
   除了 0 和 NaN 转换成false 之外 其他都是true
2.  string  字符串
   "" 空字符串为  false  其余都为 true
3. undefined  false
4. null  null => false
5. object 对象
   对象是实际存在的物体 : 几乎所有的对象布尔类型是 true

总结 :  undefined  0  ""  NaN  null 是false 其他都为true

#### 2. 转换成为字符串 string()  toString()

1. 简单转换 : 变量 + "" 强制转换为字符串

2. 专业的转换方式 : string(变量)

3. 复杂类型 : 调用 toString()  方法

   ```js
   let obj = {}
   obj.toString()//[object Object]
   ```

   对象 => [object Object]
   函数 => "function (){}"
   数组 => 去掉中括号 数值之间加上逗号 引号包裹

#### 3. 转换为数值

1. 字符串转换成数值类型 : Number()
   能转换 : 看起来像数值的 都可以转换数值 其余情况 NaN
   Number("") => 0
   "Infinity" => Infinity
2. 布尔类型: 
   	false => 0
      	true => 1
   undefined : 未定义表示值不存在 表示为赋值
   	undefined => NaN
   null : 
   null => 0
   对象 : 
        内部先调用 toString() 的方法转换成为字符串 由字符转 =>数字/数值

### 作用域

#### 代码块和声明方式 :let var const

1. const : **常量** 生成之后不会被改变
   声明的时候必须赋值
   声明之后不能修改他的值
   不能重复声明
2. var : 
   写的变量是**添加到window下**声明的
3. let : 
   先声明后使用
   
   临时性死区 : 因为变量不会提升
   
     代码在预编译阶段其实已经识别了变量 , 但这个变量还未生效 , 生效之**前方位会出错**

#### 作用域是变量的生效范围

全局变量 : 全部的变量

局部变量 : 只在代码块里面生效

特殊情况 : var 声明变量会**提升到函数作用域的顶部**
let/const 声明变量只会提升到代码块级作用域的顶部

函数传参的时候 , 会将变量赋值进去成为**内部变量** , 修改的是**函数内部的变量**()

##### 立执行函数

```js
(function (){})()
+(function (){})()
```

##### 作用域本质

在函数内创建一个作用域存放数值
函数执行完成后  删除

##### 垃圾回收

局部作用域 是函数执行完之后清除 全局作用域是页面关闭后被清除

防止内存溢出(泄漏) : 30M
清除的核心时间: 离开作用域的时候

1.  标记清除 :
   变量进入环境的时候标记为进入 , 代码离开这个环境时 : 标记环境离开 , 垃圾回收机制启动 , 开始收拾 ,释放环境(内存空间释放出来)
   代码底层实现
2. 引用计数 : 
   每一个变量相当于一个灯塔，如果外界有船还需要用到这个灯塔，灯塔会继续存在，直到所有船都回来了这个灯塔就会消失。
   对变量进行统计 , 如果引用为零 , **作用域消失**直接伴随着变量文档消失
3. 特殊情况
   全局作用域在页面关闭的情况下才会消失

##### 闭包的好 , 坏  闭包: 保存了该消失的作用域

通过函数拥有作用域链的方式保留了一段本该销毁的作用域

好处 : 
		将全局变量变成一个私有的变量
		但是单独保留了访问 , 限制了修改

坏处 : 
		内存溢出

```js
function main(){
    let data = "数据";
    function fn(){
        console.log(data)//这个数据没有办法在外面得到
    }//也就是使用过后就消失了 ,需要return
    return fn//返回这个函数
}
let fnMain = main()//返回的是一个函数
fnMain()//打印数据
```

闭包的例子

```js
function createO(){
    let count = 0;
    let o = {
        add:function(){
            count++
        },
        getNum:function(){
            return count
        }
    }
}
let o = createO()
```

用`var`写的`for`循环问题

```js
let oNav = document.querySelectorAll(".nav");
for(var i=0;i<5;i++){
    (function (i){
        oNav.onclick = function(){
            console.log(i)
        }
    })(i)
}
```



### 算法

计算方法
不同算法有优劣
算法优劣区分方式:

1. 时间 : 谁用的时间少(相对概念)
   相对于相同的参照物
2. 空间: 谁消耗的空间资源小

做算法优先考虑时间问题

时间复杂度: 
	量级的比较
		考虑的是随着代码(n)增加 时间变大  的变化速率O(n)
		跟n成线性关系
		O(n^2)和n^2成线性关系
		O(n^2)远远大于O(n)
二分查找
从中间查找两边 如果小 往右

#### console.time() console.timeEnd()代码运行时间

```js
console.time("名称")
for(let i = 0;i < 1000000000;i++){
    
}
concole.timeEnd("名称")//532.32132ms ( 这是代码所需要运行的时间 )
```

#### 递归

**在函数内部自己调用自己**就是递归
栈溢出
要约束好结束条件

可以方便的解决问题:将**复杂问题简单化**
简化成可以解决的问题 , 直接写出答案

##### 递归潜在的问题:

有可能做很多重复的劳动
已经算过的不需要算过了
	将计算过的结果存储到一个对象当中 
	在计算过程中如果对象里有就抄过来
	没有就计算在存储进去

### 解构赋值 语法糖

赋值 将右边的值传递给左边
左右解构一定要相等

#### 数组的解构

```js
function foo1(arr){
    let [a, b] = arr
    console.log(a,b)
}
foo1([1, 2])//1 2
```

#### 对象的解构

**属性值**能作为变量值而存在

```js
function foo2(obj){
    let {name: a, age: b} = obj
    console.log(a, b)
}
let oMsg = {
    name: "名字",
    age: 18,
}
foo2(oMsg)//"名字" 18
```

```js
function foo3(obj){
    let {pocket:{bb:str}} = obj
    console.log(str)
}
let oMsg = {
    name: "名字",
    age: 18,
    pocket:{
        aa:[1,2,3],
        bb:"文字",
    }
}
foo3(oMsg)//"文字"
function foo4(obj){
    let {pocket:{aa:[arr]}} = obj
    console.log(arr)//这里是打印了数组的第一项
}
foo4(oMsg)//1
```

##### 对象的展示/解构赋值

和对象一样 分等号左边和等号右边

```js
let obj = {
    a: 1,
    ...{
        c:2,
        d:3
    }
}
console.log(obj)//打开了之后的对象 {a:1,c:2,b:3}
let {...aa} = obj//{a:1,c:2,b:3}
```



#### 特殊情况

##### 当属性名与属性值一致时

```js
let obj5 = {
    props1:"文本",
    props2:"文本",
    props3:"文本",
    props4:"文本",
    props5:"文本",
}
let {props1,props2,props3} = obj5
console.log(props1,props2,props3)//文本 文本 文本
```

##### 剩余参数

等号左边是**吸收数组**
等号右边是**释放数组**

```js
function foo(){
    let [a, ...b] = arguments
    console.log(a, b)
}
foo(1,2,3,4,5)//1 [2,3,4,5]

let arr = [1, ...[2,3,4,5]]
console.log(arr)//1,2,3,4,5
```

```js
let arr = []
let {forEach:fu} = arr
//这是把forEach单独拿出来了
```



### 定时器

可以在一定的时间之后进行操作
定时器属于异步代码
**同步代码永远大于异步代码**

#### setTimeout

在某个时间**之后**进行操作
接受两个参数
	1.需要执行的代码函数
	2.在某个时间之后  数值  单位 ms 1s=1000ms
	3.传入的参数

```js
setTimeout(function(){
    console.log(1)
},1000)//一秒后打印 1
```

每一个定时器都是独立的，互相不干扰

##### clearTimeout()清除定时器

每一个定时器都有返回值
再用返回值的编号进行操作

```js
let time = setTimeout(() =>{
    console.log("定时器安装成功")
})
cleraTimeout(time)
```

#### setInterval 每隔多少时间执行1次

两个参数
时间到了之后执行的代码
每隔多少时间的间隔:数值

```js
let setInterval(function(){
    console.log(1)
},1000)//每隔一秒打印一个1
```

##### clearInterval 清除Interval定时(同clearTimeout)

括号里跟的是函数表达式**不是函数执行**

#### requestAnimationFrame 请求 动画 关键帧(浏览器的渲染)

**离开浏览器当前页面不会渲染**

进行操作等待页面渲染完成,提交下一次数据提交下一次的数据

**只等待下一次**,不会永远等待, 要在运动函数中**手动写上递归**

```js
function foo(){
    console.log(1)
    requestAnimationFrame(foo)
}//不停的打印1
```

#### cancelAnimationFrame() 关闭 动画关键帧

将动画关键帧存储起来

```js
let o=null
function foo(){
    o=requestAnimationFrame(foo)
    console.log(1)
}
cancelAnimationFrame(o)
```



### Math 数学对象

帮助解决数学问题

#### Math.PI π

#### Math.E 自然常数

#### Math.abs 绝对值

```js
Math.abs(-1)//1
```

#### Math.floor 向下取整

不超过x的最大整数, 

```js
Math.floor(-3)// -4
Math.floor(4.9)//4
```

#### Math.ceil() 向上取整

不小于X的最小整数

```js
Math.ceil(3.4)//4
```

#### Math.round 四舍五入

看小数点第一位
对于正数是四舍五入
对于负数情况相反

```js
Math.round(3.5)//4
特殊情况
Math.round(-3.5)//-3
```

#### Math.random() 返回 0~1之间的数 随机数

0~1之间是左闭右开

```js
console.log(Math.random())//0 ~ 1之间的数字
console.log(Math.random()*100)//0~100之间的数字
console.log(Math.random()*(51-22)+22)//22~51之间的数字
`#`+Math.random().toString(16).slice(2,8)//随机十六进制
```

#### 三角函数

​	sin 对边/斜边
​	cos 邻边/斜边
​	tan 对边/邻边

30deg 的直角三角形 <=>60deg 的直角三角形
	长度: 短 中 长
	短:中:长 1:根2:2

##### Math.sin(弧度)/Math.cos/Math.tan

Math.cos(Math.PI/3) = 1/2
Math.sin(Math.PI/6) = 1/2

##### Math.asin(对边/斜边)/Math.acos/Math.atan 反三角函数

#### Math.pow() 算平方

Math.pow(底数 , 指数)
Math.pow(2 , 2/3) 表示2 的平方结果开三次方

```js
Math.pow(2 , 2)//4
```

#### Math.sqrt() 根号

### 日期对象

#### Date 函数

帮助我们对时间进行操作
	首字母大写的构造函数
Date() 直接执行返回时间有关的字符串
	星期几 , 月份 , 几号 , 年份 , 时(24进制)分(60进制)秒(60进制) , 格林尼治平太阳时间

日期对象的API

#### new Date()

返回一个对象 object
输入0 表示系统最开始的时间
传入数值:表示1970年经过的毫秒数

#### new Date().valueOf()从初始到今经过的毫秒

返回时间对象到初试时间之间过了多少毫秒

#### (new Date).gateDate()返回当前月的第几个星期

周天是0

#### (new Date).getDay()返回一周当中的第几天

#### (new Date).getMonth)()返回当前月份的下标

从0开始  0是一月

#### (new Date).getHours()返回从1开始的24进制的时

#### (new Date).getMinutes()返回从1开始的60进制的分

#### (new Date).getSeconds()返回从1开始的60进制的秒

#### (new Date).getFullYear()返回年

#### (new Date).getMilliseconds()返回毫秒

**将上面所有get 改为set是设置**

### 节流

防止流量过大造成麻烦
防止大量高密度事件触发冲击后台 或冲击业务逻辑, 用户体验糟糕

```js
let state = true;
if(state)return
state = false;
//一些代码...
setTimeout(()=>{state = true},900)
```

### 防抖

防止抖动
防止大量信息处理

```js
let timer = null;
clearTimeout(timer);
timer = setTimeout(()=>{console.log(1)},500);
```

### 正则表达式

描述了一些规则 ,让字符串进行匹配
对字符串进行操作

#### 生成正则表达式new RegExp()

new RegExp()返回一个正则表达式
RegExp 传两个参数
匹配公式

##### 匹配模式

######  i:是忽略大小写

###### g:全局匹配

###### m:允许换行重新开始

###### s:允许匹配换行符

```js
let reg=new RegExp("a","i")//匹配满足a的字符串忽略大小写
```

#### 用正则表达式进行匹配

##### test 测试是否有字符串满足匹配条件

匹配的是整个字符串

````js
let reg=new RegExp("a","i")
console.log(reg.test("aqwer"))//true
````

**另一种写法**
直接写出来

#### 斜杠写法 `/`以斜杠开始斜杠结束末尾选择性的添加匹配模式

```js
let reg=/a/i//匹配满足a的字符串忽略大小写
```

#### 正则表达式的量词: 描述出现过多少次

##### `{}`匹配多少次中间添加量词

`{n}` n个
`{n,m}` 最小n个, 最大m个 m一定要比n大
`{n,}` 最小n个 无限大

````js
/a{2}/.test("aa");//true
/ba{2}/.test(baba);//false
/(ba){2}/.test(baba);//true 括号打包分组
````

**如果有特殊 有意义的符号用反斜杠转义**
反斜杠表示转义反斜杠后面的内容
但是如果转义的内容没有特殊意义就不管

```js
/\\/.test("\\");//true
```

##### `[]` 

1. 代表或者 

   ```js
   let a = 'a哈哈'
   let r = /[abc]哈哈
   ```

2. 范围

   ```js
   let a = '123'
   let r = /[1-6]/ // 匹配1到6
   ```

#### .exec 迭代匹配

匹配的结果以数组方式返回

```js
/a{2,3}/.exec("aaa")//["aa",index:0,input:"aaa"]
```

第一个表示匹配模式
index表示开始匹配的下标
input表示匹配的字符串
花括号里是大于等于第一个值
小于等于第二个值
第一个是**0次时是空字符串**
第二个值不写表示正无穷
**会将上次匹配成功的位置记录下来**

#### 正则表达式特殊符号

##### *匹配任意次数 {0,} 匹配0次以上

有也可以 有多个也可以

##### +匹配第二个开始的多个次数 {1,}  1次以上

##### ?匹配开头 {0,1} 

代表 有或者没有

```js
/a?/.exec("asd");//["a"]
/ba?/.exec("abasd");//["ba"]
```

##### ^表示匹配开始

```js
"abc".match(/^[a-z]/g);//["a"]
"abc".match(/[a-z]$/g);//["c"]
```

在中括号里是取反

```js
/[^0-9]/;//匹配除了0-9之外的字符
```

##### $表示匹配结束

```js
"aaaa".match(/^a{3-5}$/)//["aaaa"]
"aa".match(/^a{3-5}$/)//null
```

##### 正则表达式的中括号 或者的意思

```js
/[fi]/.exec("asdfe");//["f"]
/[fi]/.exec("asdia");//["i"]
```

##### |复杂或

```js
let reg=/^\w{5,13}@.{2,5}\.(com|cn)$/
```

中括号里面加一个 - 是多少到多少
正则表达式**已经匹配过了**的东西**不会再匹配**

##### .号 (点号)换行符之外的任意单个字符

```js
let str=`a:"你好", b:"你好大家好"`
let reg=/.:/g
reg[Symbol.match](str)//["a", "b"]
```

##### \d 匹配 0-9单个数字

```js
/\d/;//匹配0-9的单个数字
```

##### \D 匹配 0-9之外的字符

##### \w 非特殊字符 

字母, 数字, 下划线

0-9 a-z A-Z 下划线(_)

##### \W 匹配特殊字符

[^0-9a-zA-Z_]

##### \s 所有的空格

空格: 空格 制符表 换行键  缩进符

##### \S 所有的非空格

##### \b 匹配单词边界

就是单词的末尾

```js
let str="hellow nice to"
let reg=/\b./g;//每个单词后面挨着的字符
```

一个单词的开始位置和结束位置

```js
let str = "Boy is giry"
let r = /\bBoy\b/;//Boy这个单词开头 和 结尾
```

#### 修饰词

##### `i` 不区分大小写

```js
let str = 'Abc',r = /ABC/i
```

##### `m` 换行匹配

##### `g` 全局匹配

#### .match

返回一个数组

```js
"aaa".match(/a/g);//["a","a","a"]
```

#### Symbol.match

但凡用到了Symbol.match 都可以 用字符串来匹配

#### `.test` 

匹配正则返回一个**布尔类型** 

#### `RegExp` 

最近一次的正则匹配结果会存储到`RegExp` 

```js
RegExp.$1
RegExp.$2
```



#### 正则断言

断言就是一个约束条件 , 需要查询约束条件 , 最终匹配不要这个约束条件
先写上括号 : 需要断言的内容
括号里添加 ?
后面 **加上断言位置** 在后面是 ?= 。在前面 <=
查找不是这个后缀的内容  ?!

```js
let str="张三.mp4\n李四.rmvb\n王五.avi\n王五.mp4"
let reg=/.+(?=\.mp4)/gm;//匹配了.mp4前面的内容 不包含mp4 但mp4作为了查询条件
//匹配王五的影片但是影片的后缀不是.mp4
let reg2=/王五(?!\.mp4)/g
```

**前置** 断言 : **判断x前面是否有形容词y**
	有 (?<=y)x
	没有 (?<!y)x
**后置** 断言 : **判断x后面是否有形容词y**
	有 x(?=y)
	没有 x(?!y)

```js
let str="张三.mp4\n李四.rmvb\n王五.avi\n张三.avi\n王五.mp4"
let reg=/(?<=王五\.).+/gm;//王五的影片有几种格式
```


#### 捕获组

将前面的子项 **结果** 重复一般
正则里面的小括号是子项
后面数字代表第几个子项

```js
let str = '123aaa123'
let r = /\d{3}aaa\1/ //反斜杠后面写一个数字就是捕获组
str.match(r)
```



#### 贪婪模式和非贪婪模式

贪婪模式: (默认使用)匹配过程中**尽可能多**的**满足条件**的元素
非贪婪模式 :**尽可能少**的匹配到满足要求的元素 量词后面添加一个?
**加问号是非贪婪** 

```js
let reg=/a[bcd]*?/;//[a]
let str="adcbc"
let str2=`<div>asdasd</div>`
let reg2=/<div>.*?<\/div>/;//匹配div标签和里面的内容
```



### window

#### window.onloab等待浏览器加载完

```js
window.onloab = function(){
    let body = document.querySelector
}
```

#### window.onscroll  浏览器滚动事件

#### window.location 切换页面

```js
window.location = "页面地址"
```



### 面向对象

对象是什么?
一个具有自己**独立属性** 具有方法的对象集合体 无序性
任何对象生成方式都是通过new
new: 从内存地址拿到可用的地址
object 是什么?**是一个函数**
在面型对象讨论中**严格区分对象和函数**
任何对象都是通过**构造函数**(使用new)生成的
new 
在构造函数中不是依赖return
在构造函数中作用域内容多都不显示
**this是构造函数的灵魂**
在构造函数中this 直接指向了实例
new 操作符实际上将构造函数this返回了
new 操作符 每次执行都会**创建一个新的对象**
对象访问属性 先从对象身上找 找不到就去原型里找(_ _proto _ _)
每一个构造函数都将自己的基因**传递给了自己的实例**

```js
function Person(){
    this.props="propson"
}//这个是构造函数
new Person
```

构造函数里面的`this` 指向这个函数里面的空对象

#### 构造函数里面的两个属性: 

##### prototype:原型(只有函数有)

###### constructor:

任何对象访问constructor属性都能访问的到自己的构造函数

##### __ proto __ :

隐式原型 构造函数访问属性的访问方法
构造函数的prototype属性**传递给了实例**的__ proto __

```js
let obj= new Foo()
obj.__proto__===Foo.prototype//true
```

#### 原型链

访问属性 对象上找属性 对象__ proto __ 找属性
这样的寻找方式就是原型链
如果直接修改原型 foo.prototypr= 这种写法 请将constructor指回原来的过早函数
或者foo.prototype.a=设置的参数
或object.assign(foo.prototype, 设置的参数)
在**一般情况**(除new)下一个对象就是object创建出来的
在一般情况下 , 一个**函数就是Function 创建**出来的
function.__ proto __ .constructor ===function
function 是上层规定好的
Function.prototype 是由 Object创建的
Function.prototype.__ proto __ === Object.prototype

####  继承

一个构造函数继承两一个构造函数的`proto` 

```js
function Goudan(name,age){
    this.name = name
    this.age = age
}
Goudan.prototype.say = function(){}
function Dachui(name,age){
    //私有属性的继承
    Goudan.call(this,name,age)
}
//原型继承
Dachui.prototype = new Goudan();
//另一种原型继承的方法
function F(){}
F.prototype = Goudan.prototype
Dachui.prototype = new F()
```

##### ES6继承

```js
class Goudan extends Dachui{}//谁继承与谁
```



### 代码执行顺序

异步代码 : 不按顺序
定时器 ,后续触发的事件.
根据时间处理的代码

##### Promise

构造函数 : 
new 实例化的 返回一个Promise的对象 ,整理代码让代码扁平化

承诺在传入的函数执行完成 , 继续执行后面的内容 接受一个参数 执行的函数

```js
new Promise(function (resolve, reject){})
```

Promise状态 三种
pending 等待
resolve 成功
reject 失败

##### resolve:解决 =>函数执行成功

当resolve执行的之后Promise就知道此时函数执行完成并且成功了

```js
let promise=new Promise(function min(resolve,reject){
    setTimeout(function (){
        console.log("第一段代码")
        resolve()
    })
})
promise.then(function (){
    console.log("第二段代码")
})//先执行 第一段代码 后执行 第二段代码
```

```js
function waitForSec(time){
    return new Promise(resolve=>{
        steTimeout(()=>{
            console.log(`${time}等待完成`)
            resolve()//监听等待完成的操作
        },time)
    })
}
waitForSec(1000)
	.then(()=>{
    	return waitForSec(1100)
	})
	.then(()=>{
    	return waitForSec(1200)
	})
```

resolve 是异步代码
支持传入参数 传入Promise里面的参数 

```js
new Promise(resolve=>{
    let result=null
    setTimeout(()=>{//result 接受的数据
        result={
            name:"mingcheng",
            point:59
        }
        resolve(result)
    },1000)
}).then((response)=>{//response返回的数据
    console.log(response.point)
    response.point++
    response.message="这个真棒~"
    return new Promise(next=>{
        next(response)
    })
}).then(res=>{
    console.log(res)
})
```



##### reject: 拒绝 => 函数执行失败



###### .then() 方法  执行成功后干什么

###### .catch()方法  执行失败/出错 后干什么

如果程序出错或执行了 reject 就会执行catch 并将错误捕获输出出来
catch完成之后 后续的promise也会执行

###### .finally() 方法 不管怎么样Promise执行结束了

**不管处理结果**成功还是失败*最后再来一句*

##### Promise.resolve() 返回成功的Promise对象

等价于

```js
new Promise(res => res())
```

##### promise.all 构造函数的方法

往里面传入一个数组
数组的每一项都是Promise对象
只要数组里面的Promise对象**都完成了**才执行then

##### promise.race方法 赛跑 只要成功就触发then

有多种方法可以获取数据 只要有一个跑通了就可以拿到数据了
和all相反

##### throw 抛出

###### throw new Error("报错") 以报错的形式抛出

#### async 定义一个异步函数

```js
async function a(){
    console.log(1)
}//
let b = async function(){
    console.log(2)
}
```

await

##### await 等待一个Promise结果

不能单独用  需要放在async函数中
Promise正常执行 就正常运行
promise执行失败(reject) 报错

```js
async function (){
	let data=await new Promise()
}
```

###### try, catch 处理Promise执行失败的错误

```js
async function(){
    tyr{
        let data = await new Promise
    }
    catch{
        //不拉不拉代码
    }
}
```



#### Generator 函数特性 *

function 后面添加一个 *

```js
let fn=function* fn(){}//生成一个迭代器
```

迭代器函数执行生成迭代器对象

##### yield 迭代器返回

和return很像

```js
let loop=function* (){
    let index=0
    while(true){
        console.log(index++)
    }
    yield index//代码在这里暂停了
}
let LoopGenerator = loop()
LoopGenerator.next()//{value:0}
```

##### .next()方法 

可以分开执行每次都访问迭代器通过yield返回的内容

### ajax

不整体刷新页面时像后台发送请求拿到数据

#### XMLHttpRequest

构造函数创建一个可以发送给后台的ajax对象

```js
let xhr = new XMLHttpRequest()//生成很多ajax对象
```

客户端c和服务器s进行连接发送文件进行的操作
**3次握手 , 4次挥手**
	三次握手:
		c对s说: 我接下来发送一些内容给你
		s对c说: 我知道你要发送内容了 , 我已经准备好了
		c对s说: 我已经收到你的同意了 , 我要开始发送
		传输消息
	结束连接 四次挥手:
		c对s说: 我不打算和你通信了
		s对c说: 我已近收到了 , 那我也结束掉这段通信
		c对s说: 我已近知道你收到这段消息了, 关闭发送模块, 我后面也不会发消息
		s对c说: 我也收到了 , 我也关闭我的发送模块和接受的模块

#### 实例化完成之后open

做基础的设置

```js
xhr.open("get","http://loaclhost/get")//第一个请求方式, 第二个请求地址
```

#### 发送请求send

可以写在地址当中

```js
xhr.open("get","/get?user=goudan&pass=123")
```

向后端发送的数据
但是get请求不需要发送额外的信息

```js
xhr.send("数据")
```

#### 接收数据onreadystatechange

```js
xhr.onreadystatechange = function(){
    this.readyState
}
```

xhr接收数据是有状态的

##### xhr状态 readyState

0:请求未初始化
1:服务器连接已建立
2:请求已接收
3:请求处理中
4:请求已完成, 且响应已就绪

##### 状态码 status

100-600
1xx:消息还没有发送
2xx:表示成功没问题
3xx:表示重定向
4xx:表示失败拒绝
5xx:表示服务器崩了

```js
xhr.onreadystatechang = function(){
    if(xhr.readyState===4&&xhr.status>=200&&xhr.status<300||xhr.status===304){
        //拿到数据
    }
}
```

##### 后端返回的数据responseText

返回的数据是一个字符串需要转换

###### JSON.parse 特殊字符串转对象

#### ajax post请求

数据携带不会写在url之中
规定请求格式 , 设置请求头部的信息

##### setRequestHeader

###### post规定的请求头

```js
xhr.setRequestHeader("Content-type","application/x-www-form-urlencoded")
```

##### send发送信息

将数据整理发送
属性名=属性值&属性名=属性值

```js
xhr.send("user=goudan&pass=123&age=18")
```

获取数据和get一样

#### fetch 

浏览器自带的方法 xhr封装(兼容性有点低)

```js
fetch("/get?user=goudan&pass=123")
	.then(response=>response.json())//先用json方法整理成json对象在点then
	.then(res=>{
    console.log(res)//这个才是fetch返回后端的数据
})
//或者
fetch("地址",{method:"GET"})
	.then(response=>response.json())//先用json方法整理成json对象在点then
	.then(res=>{
    console.log(res)//这个才是fetch返回后端的数据
})
```

### 跨域

前端访问后端如果**域名**不同就会引起**跨域问题**
浏览器设置了策略: 同源策略

1. 协议相同
   前面的额协议必须一致(http://  https://  file://)
2. 域名相同
   协议后面到端口前面中间的这一部分
3. 端口相同
   域名后面的端口号

#### 解决跨域

找后端
或者自己搭建一个后端做代理
因为后端访问后端是没有跨域问题的

##### JSONP

绕过了浏览器跨域检测进行跨域操作
JSON width padding
意思是 将数据外面包一层壳
script标签可以跨域
借用script标签生成一个script标签代码就可以跨域了

```html
<script>
	function myFunction(data){
        console.log(data)
    }//前后端约定一个函数
    //访问地址加上函数 后端就会返回一个执行函数的代码
    //而函数的参数就是数据
    //前端创建一个函数里面接受参数并处理
</script>
<script src="地址?cb=myFunction"></script>
```

但是你要通过代码创建一个script标签
并且要不留痕迹的删掉

```js
function JSONP(){
    //创建script标签
    let script = document.createElement("script")
    //添加地址
    script.src = "访问的地址"
    //在body里面添加script标签
	document.body.appendChild(script)
    //script加载完成之后删除标签
    script.onload = function(){
        this.parentNode.removeChild(this)
        //删除要通过父元素删除
        //parentNode是他的父元素
        //叫自己的父亲元素把自己删掉
        //或者是document.body.removeChild(script)
    }
}
```

### url转码/解码操作

#### encodeURI

将字符串解析

```js
encodeURI("字符串")
```

#### decodeURI

```js
decodeURI("解析码")
```

### BOM

浏览器对象模型

#### `window.close()` 关闭当前页面

#### `window.open()` 打开一个标签

#### `window.onresize` 浏览器的宽高

```js
window.onresize = function(){}
```

#### `window.onscoll` 浏览器的滚动条滚动时

```js
window.onscoll = function(){}
```

#### `window.onblur` 离开了当前标签

#### `window.location` 当前标签的一些数据

##### `location.href` 当前页面的链接

###### `location.reload()` 刷新页面

#### `window.history` 前进回退操作

##### `history.back()` 后退

##### `history.forward()` 前进

##### `history.go()` 退回或前进第几个

#### `window.navigator` 浏览器的一些信息

##### `navigator.userAgent` 各种浏览器的信息

#### `window.screen` 当前电脑的分辨率

### DOM相关操作

DOM: document object model

节点: 一个标签就是一个节点
父节点: 相对概念 , 谁相对于谁是父节点 =>是谁的父亲
谁在外面紧紧的包裹里面的元素外面的元素就是里面的父节点
一个标签可以使子节点也可以是父节点

#### DOM树

页面元素从html节点开始分叉一直可以递归分叉到任意元素
每个标签都是对象
最大的对象是document
里面有两个东西
doctype

#### html标签节点 document,documentElement

#### hend document.head

#### body document.body

#### 获取方式

##### query 方式标签节点

```js
let queryList = document.querySelectorAll("div")
```

NodeList 包含了其他节点(**获取的结果**)
	标签节点(元素 文本 属性)

##### get 系列

```js
getElementByClassName//多个元素 数组
getElementById//单个元素
```

会**动态的更新**节点
HTMLCollection动态的元素的数组(**获取的过程**)
元素节点

动态和静态
修改页面元素

```js
document.body.appendChild(document.createElement("div"))//生成一个div的节点
```

#### 添加,删除`class`名字

```js
let box = document.qquerySelector(".div")
box.classList.add("nav","aa")//添加
box.classList.remove("aa")
```

#### 判断`class`名字

```js
let box = document.querySelector(".div");
box.classList.contains("div")//返回布尔值
```

#### 有名字删除名字没有就增加

```js
let box = document.querySelector("div");
box.classList.toggle(".show");
```

#### 获取一个元素的所有节点 `childNodes` 

```js
let wrap = document.getElement('.div');
wrap.childNodes//.div 下面的所有节点包含换行和注释
```

#### 只获取子节点 `children` 

获取内部的子节点

```js
let div = document.querySelector(".div");
div.children
```

#### 获取当前元素的父元素 `parentNode` 

#### 当前元素的定位父级 `offsetPatent` 

#### 第一个子元素节点 ` firstElementChild` 

### DOM的增删改

##### 添加

###### innerHTML

```js
let box=document.querySelector(".box")
box.innerHTML=`<div class=".small"></div>`
```

方法**不优化**
innerHTml添加方式: **重新渲染**html
消耗性能, **从新渲染**
重新生成元素 , 之前的内容**消失了**
innerHTML对页面以前的**内容覆盖**

######  document.createElement()  创建元素

```js
let div=document.createElement("div")//括号里传标签名
```

创建一个div标签 存在div变量里面

###### document.body.appendChild() 添加创建了的元素

```js
let box=document.querySelector(".box")//获取父元素
let div=document.createElement("div")
box.appendChild(div)
```

如果还要添加请**再生成一次**

###### document.createDocumentFragment() 生成一个文档片段

就是一个袋子
也有appendChild方法
只不过是生成在一个Fragment数组里面

###### 插入到某一个节点之前 `insertBefore` 

```js
let oA = document.createElement('a'),
    div = document.querySelector('.div');
div.insertBefore(od, div.children[2])//添加到div里面的第三个元素上面
```



**DOM操作非常消耗性能**(涉及到渲染, 更新)

##### 删除

###### removeChild() 父元素删除子元素的操作

```js
box.removeChild(boxList[0])
```

###### parentnode 父亲节点 父元素

```js
document.documentElement.parentnode===document//true
```

###### 定位父级 offsetPrent

父相子绝

```js
let box=document.querySelector(".box")//获取父元素
box.offsetPrent
```

###### `getComputedStyle` 获取 一个元素的css

```js
getComputedStyle(div)//传入一个节点
```



#### 属性

##### getAttribute() 获取标签属性

##### setAttribute() 设置属性

以字符串的形式进行添加
出入两个参数
一个是属性名
二是属性值

```js
let img=document.createElement("img")
img.steAttribute("loaded","true")
```

##### 属性的生成 createAttribute()

属性节点的设置方法

##### getBoundingClientRect() 获取元素的位置

```js
let box=document.querySelector(".box")
box.getBoundingClientRect()
```

相对于浏览器窗口可视区域的位置

##### clientHeight/clientWidth 盒子的高和宽

##### clientTop / clientLeft 盒子的边框 高 宽

获取的值单位是像素
滚动条是占位置的一般是17像素
client 元素的本质区域 就是可以看到的区域

##### clientTop/clientLeft 盒子距离 上/右 的距离

没有**下和左**

##### 浏览器窗口可视大小 

###### innerHeight/innerwidth

前面加上**window**

**包含滚动条**

##### 浏览器软件大小

###### window.outerWidth

###### window.outerHeight

###### window.resize 监听窗口发生改变

前面加上**window**

##### 盒子的位置信息 offset

如果设置了定位属性就会**参照定位父级**
没有定位属性**参照body**

###### offsetTop

###### offsetLeft

###### offsetParent 定位父级

定位参考的是父级padding之外**边框之内**

##### 滚动 scroll

###### scrollWidth 宽

###### scrollHeight 高

盒子里面内容的可以滚动的大小

###### scrollTop 竖直方向滚动高

生成滚动条的那个元素的滚动宽高位置

###### scrollLeft  水平方向滚动宽

##### 滚动事件 onscroll

直接写在window 下面
或写到动作/被滚动的物体的元素上面

```js
window.onscroll=function(){
	const height=document.documentElement.scroll+window.innerHeight
    imgs.forEach(img=>{
        //已经加载了的图片就不去加载了
        if(img.getAttribut("loadata")===true) return
        if(img.offsetTop<height){
            img.src=img.dataset.src//改成真实的地址
        }
        console.log(window.scrollY)
    })
}
```

##### 设置滚动 scrollTo()

传入两个值一个是x 一个是y

```js
window.scrollTo(0,100)//往下走100px
```

### 事件

事件发生的状态
需要在什么情况下做什么事情

事件主体对象(谁 发生了什么样的事情)
事件类型
事件处理函数

#### 点击的时候 : click

事件绑定是以等号赋值

```js
let box=document.querySelector(".box")
function handleClick(){
    console.log(1)
}
box.onclick=handleClick
```

以标签形式写出来

```html
<div onclick="foo()"></div>
<script>
    function foo(){
        console.log(1)
    }
</script>
```

事件对象 : 任何事件触发 浏览器帮我们整理一个事件对象
存储事件触发的**一些细节**是 事件函数的**第一个形参** event
里面有一个isTrust 是否是原生事件 浏览器自带的事件

###### screenX/Y 整个浏览器的位置

##### onmousedown 鼠标按下

##### onmouseup 鼠标抬起

##### onmouseove 鼠标移动

##### touchstart 触碰 (手机端)

##### touchmove 手机端 移动

#### 事件源

触发那个**事件的元素是谁**  .target
事件取消赋值为 null

##### mate是window 健

#### 键盘事件 

##### onkeydown 按键按下

##### onkeyup 按键抬起

#### 事件模型

##### 事件监听 addEventListener() 

DOM2级事件

三个参数
第一个事件类型
	不需要写on 直接写事件名 字符串
第二个事件处理函数
	注册了一个函数处理操作 , 可以有多个处理函数 , 谁先写谁先操作
	事件监听是以函数作为基准, 相同的函数不能重复注册
	事件监听的事件对象和之前的绑定的事件对象是一致的

```js
box.addEventListener("click",function (){})
```

##### 事件监听取消 removeEventListener

```js
box.removeEventListener("click",function(){})
```

##### 事件委托

在一起的元素都可以交给他们**统一**管理者**处理**
用一个观察者观察点击操作

```js
let box=document.querySelector(".list")
box.addEventListener("click",function (e){
    console.log(e)
})
```

###### e.target 事件的目标 触发的主题对象

```js
let ul=document.querySelector(".list")
ul.addEventListener("click",function (){
    if(e.target.tagName.toLowerCase()==="li"){
        //
    }
})
```



##### 事件模型

点击操作
系统点击操作事件会遵循一定顺序
由外到内的操作顺序
事件触发流程: 事件捕获阶段 直到目标元素

任何一个事件触发
事件捕获阶段: **从外到内** 找到元素
事件冒泡阶段: **从里到外** 传递信息出去

任何元素都会出现let box=document.querySelector(".list")的时机
事件是在**冒泡阶段触发**的
修改事件触发的时机 : 在addEventListener 的**第三个值**
是为布尔值 默认为false

```js
box.addEventListener("click",function(){
    console.log(1)
},false)//是否在捕获阶段触发
//或者第三个参数是 {passive:false}
```

###### 阻止事件进一步传递 e.stopPropagation()

e是 event对象
阻止冒泡发生

###### 阻止事件的默认行为`e.preventDefault()` 

页面中有一些默认行为

#### 阻止选中文本

```js
document.onselectstart = function(){return false}
```

#### 自定义事件

自己定义的事件
自己规定事件的名称事件触发

##### CustomEvent() 实例化一个自定义事件

传入参数: 事件名
**先监听后触发**
一开始就触发

```js
let event=new CustomEvent("my-event",{
    datali:{
        value:"自定义事件数据"
    }
})
let box=document.querySelector(".box")
box.addEventListener("my-event",function(e){
    console.log(e)
})//先监听
box.dispatchEvent(evnet)//触发一个自定义事件
```

实例化之后返回一个对象

###### bubbles 是否会冒泡打开

默认值是false
如果要改为true就写在**别的事件里**

##### dispatchEvent() 触发事件

### cookie

请求之中存在用户信息的确认
有时效性

前端设置`cookie` 

```js
document.cookie = 'name=goudan'
```

设置过期时间

```js
//在设置cookie的内容最后面写上代码
let date = new Date(new Date().getTime() + 24*60*1000)//一天
document.cookid = 'name=dachui;expires='+date.toUTCString()
```

#### localStorage

本地存储 将前端的数据保存到本地
关闭页面再打开都会保存下来
是一个对象
刷新页面之后里面的数据会保留

```js
sessionStorage.setItem('name','goudan');//设置值
sessionStorage.getItem();//取值
sessionStorage.removeItem('name');//删
sessionStorage.clear();//全删
```

```js
localStorage.setItem("对象",JSON.stringify(对象))
```

##### setItem 设置localStorage()里面的值

##### 删除单个数值 removeItem()

##### 清空里面所有的值 clear()

localStorage不能接受字符串
要转换

##### JSON.stringify()转换为字符串

在转换为数组

```js
JSON.parse(localStorage.getItem("left"))
```

##### JSON.parse();转换为json对象

### canvas

#### 图片跨域问题

在创建的img里添加crossOrigin属性

```js
let img = new Image()
img.crossOrigin=""
```

canvas h5一个**标签**
各种特效 => canvas 制作 , 动画
理解成一张图片: 图片里的内容是自己绘制出来的
canvas 标签 只能在dom层级进行操作
有自己的默认宽高  如果用样式更改的话会被拉伸
用行内方法

```js
<canvas width="500" height="500">
```

#### getContext 绘制上下文

上下文的格式 "2d" "webGl"获取显卡

```js
let canvas=document.querySelector("#canvas")
let ctx=canvas.getContext("2d")//获取2d绘制环境
```

ctx控制绘制的主体对象的各种东西

绘制直线需要开始位置和结束位置
中间还有划线的方法
绘制的时候**一定要结束**

##### 开始位置 moveTo()

```js
ctx.moveTo(50,100)
```

##### lineTo()直线

```js
ctx.lineTo(100,150)
```

###### 划线 stroke()

告诉浏览器开始绘制
把线连起来

```js
ctx.stroke()
```

###### 填充颜色 fill()

浏览器会把初始点连起来里面填充颜色

```js
ctx.fill()
```

###### 线条样式 粗细lineWidth

```js
ctx.lineWidth = 3
```

###### 线条颜色 strokeStyle

是全局的笔的颜色

```js
ctx.strokeStyle="#ff670"
```

##### 结束绘制 closePath()

##### 开始绘制beginPath()切断画笔

##### 画一个矩形 rect()

矩形只要知道两个点就行
告诉浏览器绘制的路径
前两个是**起始点**
后两个是矩形的**宽高**

```js
ctx.rect(300,300,100,200)
```

###### ctx.fillStyle 填充颜色

```js
ctx.fillStyle="#ff6700"
```

##### fillRect添加填充矩形

```js
ctx.fillRect(300,300,100,200)
```

##### 绘制圆弧 arc()

先规定圆弧的圆心 半径 开始的坐标角度 结束的圆弧角度 顺时针/逆时针

```js
ctx.arc(400,100,50,0,1,false)//圆心的X坐标 ,Y坐标 ,半径 ,开始角度 ,结束角度 ,顺逆方向(默认顺) false是顺时针
```

开始画圆的位置是 Math.PI/2

#### 绘制图片到canvas

生成一个img标签

```js
let img=new Image()
```

##### 绘制图片 drawImage()

传三个参数img标签, 图片的X Y坐标

```js
let img=new Image()
ctx.drawImage(img, 700, 100)
```

如果要控制大小写五个参数

```js
let img=new Image()
ctx.drawImage(img, 700, 100, 100, 100)//后两个是 X方向的长度 Y方向的长度
```

完全体是九个参数  裁切

```js
ctx.drawImage(img, 130,50,230,250,700,100,235,250)//原始裁切的起始位置(两个值),原始图裁切大小(两个值),canvas的绘制位置(两个值), canvas的绘制大小(两个值)
```



#### 获取canvas中的图片信息数据getImageData()

传入四个参数 位置信息

```js
ctx.getImageData()
```

#### 图片重新绘制putImageData()

```js
ctx.putImageData(imageData,0,0)//图片,X位置 Y位置
```

##### 清空之前的画布 clearRect()

传入清空的矩形区域

```js
ctx.clearRect(0,0,canvas.width,canvas.height)
```

#### 二次贝塞尔曲线 quadraticCurveTo()

```js
ctx.quadraticCurveTo()
```

#### rotate() 旋转

默认以左上角旋转
传入弧度

```js
ctx.rotate()
```

#### translate() 调整旋转中心

### import

script 里的导入JS文件

```html
<script type="import">
	import Game form "./src/game.js"
</script>
```

```js
class Game{
    
}
export default Game//导出代码
```

import代码全部写在**首行**

## Proxy监听对象

```js
new Proxy()
```

第一个参数是监听的对象
第二个是一个**函数**或是**get和set**

```js
let ob = {
    name:"n",
    age:11
}
let fn = new Proxy(bo,{
    get(target,key){
        //target目标, key值
        //访问值走get
    },
    set(target,key,value){
        //设置值走set
    }
})
fn.name
```

## Set数据结构

传入一个数组参数

```js
let a = new Set([1,2,3])
//{1,2,3}
```

### 数组去重

```js
let a = [... new Set([1,1,2,3,4,4,5,5,6,6])]
console.log(a)
//[1,2,3,4,5,6]
```

有add , remove , clear 方法

## Map数据结构

普通对象只能用字符串当做 键/属性 
如果是对象或者数组 将强制转换成字符串
`Map` 允许任意数据类型当做 键/属性 

```js
let a = [1,2];
let b = {x:1,y:'22'};
let m = new Map();
m.set( a , 'goudan' )//存值
m.get(a)//取值
```

## 位运算

位运算是把数字转换为二进制进行运算

或 (|) 有1出1 全0出0:  用于取整
`22.2 | 0 === 22` 

与 (&) 有0出0 全1出1

异或 (^) 相等出0 不等出1

## 拖拽

就是鼠标按下,并且鼠标移动

```js
let app = document.gitElementById('app');
app.onmousedown = function(e){
    //获取鼠标当前的位置
    let x = e.clientX - e.offsetLeft;
    let y = e.clientY - e.offsetTop;
    app.onmouseenter = (e)=>{
        //更改他的translate的css样式
    }
}
```

在`H5` 里面需要在标签里设置属性
`draggable` 是`HTML` 5的新特性

```html
<div id='app' draggable='true'></div>
<!-- true false auto auto是更具浏览器定义是否可以拖拽 true是可以拖拽-->
```

```js
app.ondragend = (e)=>{
    //拖拽的事件函数
    this.style.cssText = `left:${e.clientX}px;top:${e.clientY}px;`
}
```

### 拖拽开始事件`ondragstart` 

### 拖拽过程中触发`ondrag` 

### 拖拽结束事件`ondragend` 

### 元素被拖拽到当前元素上`ondragenter` 

一个物体被拖拽到了当前元素上面所触发的事件

### 元素拖到当前元素上并停留了`ondragover` 

一个元素拖拽到当前元素上并停留了
需要阻止默认时间`e.preventDefault()` 

### 拖拽的元素离开了当前元素`ondragleave` 

### 被拖拽的元素在当前元素上松开了鼠标`ondrop` 
