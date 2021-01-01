##### JQ获取的东西自带遍历

##### 获取值自动获取第一个

#### 获取标签

```js
$("p")
```

#### 获取id / class

```js
$("#id")
$(".class")
```

#### 获取的JQ数组取其中的某一项eq

```js
$("#id p").eq(1)
$("#id p").eq(-1)//负一是最后一个
```

这样取出来之后还是JQ对象

#### JQ和DOM之间转换

```js
$("#id div")[0]//取出的是DOM节点
let odiv = document.querySelectorAll(".box")
$(odiv)//转换成了JQ对象
```

#### 获取和设置标签名

```js
$("#id").prop("id")//传入一个是获取传入两个是设置
$('a').prop("href","https://www.baidu.com/")
```

传入多个是传入对象

#### 获取和设置自定义参数

```js
$(".div").attr("name","goudan")
```

他和prop的区别在attr只会获取你设置的值  设置什么就是什么

#### 删除属性

```js
$(".div").removeAttr("title")
```

#### 添加clss名字

```js
$(".div").addClass("goudan")
```

#### 有名字的删除没名字的添加

```js
$("#div").toggleClass("a")
```

#### 获取innerHTML 和innerText

```js
$("#wrap").html()//获取就是传值
$("#wrap").text()
```

#### value值

```js
$("#inp").val()
```

#### 获取元素位置offset

```js
$("#box").offset()
```

offset可以设置值

````js
$("#box").offset({top:200,left:200})//距离浏览器的窗口顶部和左边200px
````



#### 获取定位父级的距离

注意定位父级距离将不计算margin

```js
$("#box").position()
```

#### scrollTop浏览器的滚轮scrollLeft

```js
$("html").scrollTop(200);
```

#### 获取元素本身宽高height / width

```js
$("#box").height()
```

##### 加上padding是innerHeight

等价于createHeight

##### 加上padding和border是outerHeight

等价于offsetHeight

#### append添加节点或者内容

```js
$("#wrap").append("<div></div>")
$("#app").append("内容")
let p = document.createElement("p")
$("#app").append(p)
```

如果在标签里面传入一个标签节点这个标签节点就会在标签里面

返回一个JQ对象

#### 创建一个不存在与页面中的JQ对象

```js
let $box = $("<div style='color:red;'></div>")
let node  = document.createElement("p");
$(node);
```

#### appendTo子元素添加到谁里面去

```js
let $box = $("<div></div>");//创建一个jq对象
$box.appendTo($("body"))
```

#### prepend在标签前面添加

```js
$("#div").prepend($("<p></p>"))
```

#### 在特定的标签之后`insertAfter` 

```js
$('<b>ww</b>').insertAfter($('p').eq(1));//将b标签添加到第1个的后面
```

#### 在特定的标签之前 `insertBefort` 

#### after/before创建一个兄弟元素

```js
$("#box").after($("<a></a>"))
$("#box").before($("<a></a>"))
```

#### 添加一个父元素wrap

#### 删除父元素unwrap

#### 用一个标签替换自己replaceWith

```js
$("p").replaceWith("<b>内容</b>")//内容也会替换
```

#### empty将里面任何东西清空

里面不需要传入任何参数

```js
$("#wrap").emptay()
```

#### remove自杀

从开始标签到结束标签删除掉

#### clone复制标签

```js
let $p = $(".div").clone()
```

里面有两个**布尔值**
第一个是否复制事件函数
第二个所有子元素的数据

#### filter 过滤

```js
$(p).filter(".goudan")
//找到属性名是goudan 的元素
```

#### play播放音频

#### pause暂停音频

#### 选中除了自己之外的所有兄弟元素 `siblings` 

#### `end` 上一个链式调用的jq对象

```js
$('html').find('body').end()//是html
```

### 事件

#### `on` 事件

```js
$('#wrap').on({
    'click.goudan':()=>{console.log(1)}
})
```

#### 取消事件`off` 

```js
$('#wrap').off('click.goudan')
```

#### 事件委托

```js
$('#wrap').on('click','p',()=>{
    //给子元素p标签添加事件
})
```



### ajax的get请求

$.get("地址")

```js
$.get("/get?user=goudan&pass=123",function(res){
    //res是后端返回给前端的信息
})
```

### ajac的post请求

$.post("地址",数据,函数)

```js
$.post("/post",{user:"goudan",pass:123},res=>{
    console.log(res)
})
```

### $.ajax 请求

```js
$.ajax({
    type:"get"//请求方式
    ,url:""//请求地址
    ,data:{
        //前端返回给后端的数据
    }
    ,dataType:''//接受的数据类型
    ,success(msg){
        console.log(msg)//后端返给前端的数据
    }
    ,error(err){
        console.log(err)//出错
    }
})
```

