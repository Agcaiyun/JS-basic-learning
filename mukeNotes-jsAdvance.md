**对象简介**
* ```JavaScript``` 中的所有事物都是对象,如:字符串/数值/数组/函数等,每个对象带有*属性* 和 *方法*
* 对象的属性:反应该对象某些特定的性质.如:字符串的长度,图像的长宽 等
* 对象的方法:能够在对象上执行的动作.如:表单的提交(```submit```),时间的获取(```getYear)``` 等
* ```JavaScript``` 提供多个內建对象,如:```String```  ```Date```  ```Array ```  等等
* 访问对象属性的语法:``` objectName.propertyName```
    ```
    var myarray=new Array(6);//定义数组对象
    var myl=myarray.length;//访问数组长度length属性
    ```

* 访问对象的方法:```objectName.methodName()```
    ```
    var mystr="Hello world!";//创建一个字符串
    var request=mystr.toUpperCase(); //使用字符串对象方法
    ```
**Date 日起对象**
* 日期对象可以存储任意一个日期,并且可以精确到毫秒
* 定义一个时间对象:``` var Udate = new Date();```
    ***注意**:使用关键字 ```new ```,```Date()``` 的首字母必须大写
    * 使``` Udate ```成为日期对象,并且已经有初始值:当前时间(当前电脑系统时间)

**返回/设置 年份方法**
* ```get/setFullYear() ```返回/设置 年份,用四位数表示
    * 如果不是四位数,比如:``` mydate.setFullYear(81)```
        * 不同的浏览器,有不同的结果
        * 年份会被设定为``` 0081 ```或者``` 81 ```这两种情况
    * 并且不同的浏览器获得的时间格式有差异
        * 比如:FF的格式为:星期  月 日 年 时  分 秒 时区

**getDay()**
* ```getDay() ```返回星期,返回的是 ```0``` ~``` 6 ```的数字,``` 0 ```表示星期天
* 如果要返回相对应的"星期",通过数组完成,代码如下:
```
<script type="text/javascript">
  var mydate=new Date();//定义日期对象
  var weekday=["星期日","星期一","星期二","星期三","星期四","星期五","星期六"];
//定义数组对象,给每个数组项赋值
  var mynum=mydate.getDay();//返回值存储在变量mynum中
  document.write(mydate.getDay());//输出getDay()获取值
  document.write("今天是："+ weekday[mynum]);//输出星期几
</script>
```

**返回/设置 时间方法**
* ```get/setTime() ```返回/设置 时间,单位**毫秒数** 
* ```getTime() ```返回的是: ```dateObject``` 指定的日期和时间距离 ```1970```年 ```1``` 月 ```1 ```日午夜(```GMT```时间)之间的毫秒数
* 如果将目前日期对象的时间推迟一小时,代码如下:
```
var mydate = new Date();
document.write("当前时间:" + mydate + "<br>");
mydate.setTime(mydate.getTime() + 60 * 60 * 1000);
document.write("推迟一个小时时间:" + mydate);
```
* **注意** 单位为 毫秒
* 时间推迟一个小时就是: "x.setTime(x.getTime() + 60 * 60 * 1000);"

## String
**indexOf()**
* ```indexOf(0)  ``` 方法可以返回某个特定的字符串值在字符串中首次出现的位置
* 语法 :``` stringObject.indexOf( substring,startpos)  ```
* 参数说明
    * ``` substrin``` : 必需.规定需要检索的字符串值
    * ``` startpos``` 可选的**整数**参数.规定在字符串中开始检索的位置.这个参数的合法值为  ```0```~  ```stringObject.length - 1  ```.如果省略该参数,则将从字符串的首字符开始检索.
* 如果找到一个  ```substring```,则返``` substring ```第一次出现的位置.(  ```stringObject  ```中的字符位置从  ```0```开始)
* 如果要检索的字符串没有出现,则该方法返回```-1 ```

**split()  字符串分割**
* ``` split()``` 方法将**字符串** 分割为 **数组**,并 **返回此数组**,原来的 字符串并**不会**受到任何影响
* 语法:``` stringObject.split(separator,limit)```
* 参数说明:
    * ```separator :``` 必需.从该参数指定的地方开始分割 ```stringObject```
    * ``` limit``` : 可选参数.分割的次数,如果设置该参数,返回的子串不会多于这个参数指定的数组,如果无此参数,则不限制次数
* **注意**: 如果把空字符串("") 用做 ```separator``` ,那么 ```stringObject``` 中的每个字符之间都会被切割
* ```eg ```
```
var mystr = "www.imooc.coom";
document.write(mystr.split(".") + "<br>");
document.write(mystr.split(".") , 2 ) + "<br>" );
```
```
www,imooc,com
www,imooc
```

**substring() 提取字符串**
* ```substring() ```方法用于提取字符串中 介于 两个指定下标之间的字符.(将提取到的字符作为返回值返回,原来的字符串并**不会**被改变  )
* 语法:``` stringObject.substring(startPos,stopPos)```
* 参数说明:
    * ``` startPos```: 必需.一个非负的整数,表示开始位置
    * ```stopPos```: 可选.一个非负的整数,表示结束位置.如果省略该参数,那么返回的子串会一直到字符串对象的结尾
* 注意
    * ```substring(startPos,stopPos)```  其中,截取范围为:```[startPos,stopPos) ```  (表示包含开始下标的字符,不包含结束下标的字符)
    * 如果参数 ```startPos``` 与 ```stopPos ```相等,那么该方法返回的值就是一个空串(即长度为``` 0 ```的字符串)
    * 如果 ```startPos``` 比 ```stopPos``` 大,那么该方法在提取子串之前会先交换这两个参数

**substr() 提取指定数目的字符**
* ```substr() ```方法从字符串中提取从 ```startPos ```位置开始的指定数目的字符串
* ``` substr()``` 方法只是提取符合要求的字符串 作为返回值返回,并**不会改变**原来的字符串
* 语法:``` stringObject.substr(startPos,length)```
* 参数说明:
    * ```startPos ```: 必需.要提取的子串的起始位置.必需是数值
    * ```length ```: 可选.提取字符串的长度.如果省略,则返回从 ```stringObject ```的开始位置```startPos``` 到 ```startObject ```的结尾的字符
* **注意**
    * 如果参数``` startPos``` 为负数,则从字符串的尾部开始计算位置.```-1 ```指字符串的最后一个字符,```-2 ```表示倒数第二个字符
    * 如果``` startPos ```为负数,且绝对值大于字符串长度,```startPos``` 为``` 0 ```


**Math 对象**
* ``` Math ```对象是一个固有的对象,无需创建它,直接把``` Math ```作为对象使用就可以调用其所有属性和方法.这是它与 ```Date String ```对象的区别 
* 使用``` Math ```的属性和方法的语法:
    * ```var pi_value = Math.PI;```
    * ```var sqrt_value = Math.sqrt(15);```
* [参考资料](http://www.w3school.com.cn/jsref/jsref_obj_math.asp)

**round**
* ```round() ``` 方法可以把一个数字四舍五入为最接近的整数
* 语法: ```Math.round(x) ``` 把一二数字四舍五入为最接近的整数

**random()**
* ``` random() ```方法可返回介于 ```0 ```~ ```1``` (大于等于```0``` ,但小于```1```) 之间的一个随机数
* 语法: ```Math.random()```
    * 返回一个大于或等于``` 0 ```但小于 ```1 ```的符号为**正** 的数字值
* 扩大返回的随机数的范围
    * ```Math.random()``` * 需要扩大的倍数

## Array
**Array 数组对象**
* 数组对象是一个对象的集合,里面的对象可以是不同类型的.数组的每一个成员都有一个"下标",用来表示它在数组中的位置,是从零开始的.
* 数组定义的方法
    * 定义一个空数组 : ```var myArrayName = new Array();```
    * 定义时指定有几个空元素的数组 : ```var myArray = new Array(n);```
    * 定义数组的时候,直接初始化数据 : v```ar myArray = [<元素1>,<元素2>,<元素3> ...];```
        * 比如:定义数组并赋值 :``` var myArray = [2,3,4];```

**concat() 数组链接**
* ```concat() ```方法用于链接两个或者多个数组.此方法返回一个新的数组,**不改变**原来的数组.
* 语法 : ```arrayObject.concat(array1,array2,...,arrayN)```
**注意** : 该方法只是将链接之后的结果作为返回值进行返回,但是**并不改变**原来的数组

**join()**
* ```join() ```方法用于将数组中的所有元素放入一个字符串中.元素是通过指定的分隔符进行分隔(分隔符就是需要被传入的这个方法的参数)
* 语法 : ```arrayObject.join(```分隔符);
* 这个方法只是返回分隔之后的字符串,**不影响**数组原来的内容.

**reverse()**
* ```reverse() ```方法用于颠倒数组中元素的位置
* 语法: ```arrayObject.reverse()```
* **注意** : 这个方法**会改变**原来的数组,而不是创建新的数组(比改变原数组)作为返回值.

**slice()**
* ```slice() ```方法从已有的数组中返回选定的元素( ```[start,end)``` ).返回一个子数组,并**不会改变**元素组
* 语法 : ```arrayObject.slice(start,end)``` ;
* 参数说明:
    * ```start```: 必需.规定从何处开始选取.如果是负数,那么它规定从数组尾部开始计算位置. ```-1 ```表示最后一个元素,```-2 ```表示倒数第二个元素.
    * ``` end ```: 可选.规定从何处开始结束.该参数是数组结束处的数组下标.如果没有指定该参数,那么切分的数组包含从 ```start ```到 数组结束 的所有元素.如果这个参数是负数,那么它规定的是从数组的尾部开始算起的元素.

##浏览器对象

**setInterval()  计时器**
* 在执行时,从载入页面后每间隔指定的时间执行一次代码
* 语法 : ```setInterval```(代码,交互时间) 
* 参数说明 :
    * 代码 : 要调用的函数 或 要执行的代码串
    * 交互时间 : 周期性执行 或 调用 表达式之间的时间间隔,以 毫秒 为单位(```1s = 1000ms```)
* 返回值 : 一个可以传递给``` clearInterval() ```从而取消对"代码"的周期性执行的值
* 调用函数格式(假设有一个 ```clock() ```函数)
    * ```setInterval("clock()",1000)```
    * ``` setInterval(clock,1000)```

**clearInterval()**
* ```clearInterval()``` 方法可以取消由 ```setInterval() ```设置的交互时间
* 语法 : ```clearInterval(id_of_setInterval);```
* 参数说明 : ```id_of_setInterval``` 由 ```setInterval() ```返回的 ```ID``` 值
*``` eg ```
```
<!DOCTYPE HTML>
<html>
<head>
<meta http-equiv="Content-Type" content="text/html; charset=utf-8">
<title>计时器</title>
<script type="text/javascript">
   function clock(){
      var time=new Date();                     
      document.getElementById("clock").value = time;
   }
// 每隔100毫秒调用clock函数，并将返回值赋值给i
     var i=setInterval("clock()",100);
</script>
</head>
<body>
  <form>
    <input type="text" id="clock" size="50"  />
    <input type="button" value="Stop" onclick="clearInterval(i)"  />
  </form>
</body>
</html>
```
* **注意** : ```onclick= **"** clearInterval(i) **"**```

**setTimeout()**
* ```setTimeout() ```计时器,在载入后延迟指定时间后,去执行一次表达式**仅仅执行一次**
* 语法 :``` setTimeout(代码,延迟时间)```
* 参数说明 : 
    * 要调用的函数 或 要执行的代码串
    * 延迟时间 : 在执行代码前需要等待的时间,以 毫秒 为单位

**clearTimeout() 取消计时器**
* ```setTimeout() ```和``` clearTimeout() ```一起使用,停止计时器
* 语法 : ```clearTimeout(id_of_setTimeout)```
* 参数说明 :
    * ```id_of_setTimeout``` : 由 ```setTimeout() ```返回的``` ID ```值,该值标识要取消的延迟执行代码块

**History 对象**
* ```history``` 对象记录了用户曾经浏览过的页面(```URL```),并可以实现浏览器前进与后退相似导航的功能
* **注意** : 从窗口被打开的那一刻开始记录,每个浏览器窗口 每个标签页 乃至 每个框架,都有自己的 ```history``` 对象与特定的 ```window``` 对象 关联
* 语法 :``` window.history```.[属性 | 方法]   ( ```window ```可以省略)
* ``` History ```对象属性 
    * ```length``` : 返回浏览器历史列表中的``` URL ```数量
* ```History ```对象方法
    * ``` back()``` : 加载``` history ```列表中的前一个 URL 
        * ```window.history.back();```
        * 等同于点击浏览器的倒退按钮
        * ```back() ```相当于``` go(-1)```
        * ```window.history.go(-1)```;
    * ```forward() ```: 加载``` history``` 列表中的下一个 ```URL``` 
        * 如果倒退之后,再想回到倒退之前浏览的页面,则可以使用``` forward() ```方法
        * ```window.history.forward();```
        * 等价于点击浏览器的前进按钮
        * ```forward()``` 相当于 go(1)```
        * ```window.history.go(1);```
    * ```go()``` : 加载``` history ```列表中的某个具体的页面
        * ```go() ```方法,根据当前所处的页面,加载``` history ```列表中的某个具体的页面
        * ``` window.history.go(number);```
        * 参数```number ```:  ```0 1 -1```
            * ```1``` : 前一个,```go(1)``` 等价于``` forward()```
            * ```0``` : 当前页面
            * -1 : 后一个,```go(-1) ```等价于``` back()```
            * 其他数值 : 要访问的 ```URL``` 在 ```History``` 的 ```URL``` 列表中的相对位置

**Location 对象**
* ```location ```用于获取 或 设置 窗体的 ```URL``` ,并且可以用于解析``` URL```
* 语法 : ```location.[属性 | 方法]```
* [参考资料](http://www.w3school.com.cn/jsref/dom_obj_location.asp)

**Navigator 对象**
* ```Navigator``` 对象包含有关浏览器的信息,通常用于检测浏览器与操作系统的版本
* ```Navigator``` 对象描述
    * ```Navigator``` 对象包含的属性描述了正在使用的浏览器,可以使用这些属性进行平台专用的配置
    * 虽然这个对象的名称显而易见是``` Netscape``` 的 ```Navigator``` 浏览器,但其他实现了``` JavaScript ```的浏览器也支持这个对象
    *没有应用于 ```navigator``` 对象的公开标准,不过所有的浏览器都支持该对象
    * ```Navigator ```对象的实例是唯一的,可以用 ``` window``` 对象的```navigator ```属性来引用它
    * 在调用这个对象的时候,应该是全小写的,也就是 ```navigator.[属性 | 方法]```

**userAgent**
* 返回用户代理头的字符串表示(就是包括浏览器版本信息等的字符串)
* 语法 : ```navigator.userAgent ```
* 使用``` userAgent``` 判断使用的是什么浏览器
* ``` eg ```
```
function validB(){ 
  var u_agent = navigator.userAgent; 
  var B_name="Failed to identify the browser"; 
  if(u_agent.indexOf("Firefox")>-1){ 
      B_name="Firefox"; 
  }else if(u_agent.indexOf("Chrome")>-1){ 
      B_name="Chrome"; 
  }else if(u_agent.indexOf("MSIE")>-1&&u_agent.indexOf("Trident")>-1){ 
      B_name="IE(8-10)";  
  }
    document.write("B_name:"+B_name+"<br>");
    document.write("u_agent:"+u_agent+"<br>"); 
} 
```

**screen 对象**
* ```screen``` 对象用于获取用户的屏幕信息
* 语法 : ```window.screen.属性```
* 属性
    * ```availHeight```   :   窗口可以使用的屏幕高度(访问者屏幕的宽度,减去界面特性,比如:任务栏),单位像素
        * 注意 : 不同系统的任务栏默认高度不一样,及任务栏的位置可在屏幕上下左右 任何位置,所以有可能可用宽度和高度不一样
    * ```availWidth  ```  :   窗口可以使用的屏幕宽度,单位像素
    * ```colorDepth ```   :   用户浏览器表示的颜色位数,通常为``` 32 ```位(每像素的位数)
    * ```pixelDepth```    :   用户浏览器表示的颜色位数,通常为``` 32 ```位(每像素的位数)(```IE```不支持此属性)
    * ```height  ```      :   屏幕的高度,单位像素
    * ```width ```        :   屏幕的宽度,单位像素

## DOM 对象

**setAttribute()**
* setAttribute() 方法增加一个特定名称和值的新属性,或者把一个现有的属性设定为指定的值
* 语法 : elementNode.setAttribute(name,value)
* 参数说明
    * name : 要设置的属性名
    * value : 要设置的属性值
* 注意
    * 把指定的属性设置为指定的属性
    * 如果指定名称的属性不存在,则该方法创建一个新属性

**节点属性**
* nodeName 属性 : 节点的名称,是**只读**的
    *  元素节点的 nodeName 与标签名相同
    *  属性节点的 nodeName 是属性的名称
    *  文本节点的 nodeName 永远是 #text
    *  文档节点的 nodeName 永远是 #document
* nodeValue 属性 : 节点的值
    *  元素节点的 nodeValue 是 undefined 或 null
    *  文本节点的 nodeValue 是文本自身
    *  属性节点的 nodeValue 是属性的值
* nodeType 属性 : 节点的类型,是**只读**的.一下常用的几种节点类型
    元素类型    节点类型
    元素          1
    属性          2
    文本          3
    注释          8
    文档          9


**childNodes 访问子节点**
* 访问选定元素节点下的所有子节点的列表,返回的值可以看作是一个数组,他具有 length 属性
* 语法 : elementNode.childNodes
* 注意 : 如果选定的节点没有子节点,则该属性返回不包含节点的 NodeLise
* 有很强的兼容性问题(虽然所有主流浏览器都支持 childNodes 属性)
* [参考资料](http://www.imooc.com/code/1590)

**firstChild / lastChild**
* firstChild 属性返回 "childNodes" 数组的第一个子节点.如果选定的节点没有子节点,则该属性返回 null
* 语法 : node.firstChild
    * 与 elementNode.childNodes[0]  是同样的效果
* lastChild 属性返回"childNodes"数组的最后一个子节点.如果选定的节点没有子节点，则该属性返回 null
* 语法 : node.lastChild
    * 与elementNode.childNodes[elementNode.childNodes.length-1]是同样的效果