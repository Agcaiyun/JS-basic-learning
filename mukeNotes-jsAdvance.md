**对象简介**
* JavaScript 中的所有事物都是对象,如:字符串/数值/数组/函数等,每个对象带有*属性* 和 *方法*
* 对象的属性:反应该对象某些特定的性质.如:字符串的长度,图像的长宽 等
* 对象的方法:能够在对象上执行的动作.如:表单的提交(submit),时间的获取(getYear) 等
* JavaScript 提供多个內建对象,如:String  Date  Array   等等
* 访问对象属性的语法: objectName.propertyName
    ```
    var myarray=new Array(6);//定义数组对象
    var myl=myarray.length;//访问数组长度length属性
    ```

* 访问对象的方法:objectName.methodName()
    ```
    var mystr="Hello world!";//创建一个字符串
    var request=mystr.toUpperCase(); //使用字符串对象方法
    ```
**Date 日起对象**
* 日期对象可以存储任意一个日期,并且可以精确到毫秒
* 定义一个时间对象: var Udate = new Date();
    ***注意**:使用关键字 new ,Date() 的首字母必须大写
    * 使 Udate 成为日期对象,并且已经有初始值:当前时间(当前电脑系统时间)

**返回/设置 年份方法**
* get/setFullYear() 返回/设置 年份,用四位数表示
    * 如果不是四位数,比如: mydate.setFullYear(81)
        * 不同的浏览器,有不同的结果
        * 年份会被设定为 0081 或者 81 这两种情况
    * 并且不同的浏览器获得的时间格式有差异
        * 比如:FF的格式为:星期  月 日 年 时  分 秒 时区

**getDay()**
* getDay() 返回星期,返回的是 0 ~ 6 的数字, 0 表示星期天
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
* get/setTime() 返回/设置 时间,单位**毫秒数** 
* getTime() 返回的是: dateObject 指定的日期和时间距离 1970年 1 月 1 日午夜(GMT时间)之间的毫秒数
* 如果将目前日期对象的时间推迟一小时,代码如下:
```
var mydate = new Date();
document.write("当前时间:" + mydate + "<br>");
mydate.setTime(mydate.getTime() + 60 * 60 * 1000);
document.write("推迟一个小时时间:" + mydate);
```
* **注意** 单位为 毫秒
* 时间推迟一个小时就是: "x.setTime(x.getTime() + 60 * 60 * 1000);"

**indexOf()**
* indexOf(0) 方法可以返回某个特定的字符串值在字符串中首次出现的位置
* 语法 : stringObject.indexOf( substring,startpos)
* 参数说明
    * substring : 必需.规定需要检索的字符串值
    * startpos: 可选的**整数**参数.规定在字符串中开始检索的位置.这个参数的合法值为 0 ~ stringObject.length - 1 .如果省略该参数,则将从字符串的首字符开始检索.
* 如果找到一个 substring ,则返回 substring 第一次出现的位置.(stringObject 中的字符位置从 0 开始)
* 如果要检索的字符串没有出现,则该方法返回 -1

**split()  字符串分割**
* split() 方法将**字符串** 分割为 **数组**,并 **返回此数组**,原来的 字符串并不会受到任何影响
* 语法: stringObject.split(separator,limit)
* 参数说明:
    * separator : 必需.从该参数指定的地方开始分割 stringObject
    * limit : 可选参数.分割的次数,如果设置该参数,返回的子串不会多于这个参数指定的数组,如果无此参数,则不限制次数
* **注意**: 如果把空字符串("") 用做 separator ,那么 stringObject 中的每个字符之间都会被切割
* eg 
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
* substring() 方法用于提取字符串中 介于 两个指定下标之间的字符.(将提取到的字符作为返回值返回,原来的字符串并未被改变  )
* 语法: stringObject.substring(startPos,stopPos)
* 参数说明:
    * startPos: 必需.一个非负的整数,表示开始位置
    * stopPos: 可选.一个非负的整数,表示结束位置.如果省略该参数,那么返回的子串会一直到字符串对象的结尾
* 注意
    * substring(startPos,stopPos)  其中,截取范围为:[startPos,stopPos)   (表示包含开始下标的字符,不包含结束下标的字符)
    * 如果参数 startPos 与 stopPos 相等,那么该方法返回的值就是一个空串(即长度为 0 的字符串)
    * 如果 startPos 比 stopPos 大,那么该方法在提取子串之前会先交换这两个参数

**substr() 提取指定数目的字符**
* substr() 方法从字符串中提取从 startPos 位置开始的指定数目的字符串
* substr() 方法只是提取符合要求的字符串 作为返回值返回,并不会改变原来的字符串
* 语法: stringObject.substr(startPos,length)
* 参数说明:
    * startPos : 必需.要提取的子串的起始位置.必需是数值
    * length : 可选.提取字符串的长度.如果省略,则返回从 stringObject 的开始位置startPos 到 startObject 的结尾的字符
* **注意**
    * 如果参数 startPos 为负数,则从字符串的尾部开始计算位置.-1 指字符串的最后一个字符,-2 表示倒数第二个字符
    * 如果 startPos 为负数,且绝对值大于字符串长度,startPos 为 0 

**Math 对象**
* Math 对象是一个固有的对象,无需创建它,直接把 Math 作为对象使用就可以调用其所有属性和方法.这是它与 Date String 对象的区别 
* 使用 Math 的属性和方法的语法:
    * var pi_value = Math.PI;
    * var sqrt_value = Math.sqrt(15);
* [参考资料](http://www.w3school.com.cn/jsref/jsref_obj_math.asp)

**round**
* round()  方法可以把一个数字四舍五入为最接近的整数
* 语法: Math.round(x)  把一二数字四舍五入为最接近的整数

**random()**
* random() 方法可返回介于 0 ~ 1 (大于等于0 ,但小于1) 之间的一个随机数
* 语法: Math.random()
    * 返回一个大于或等于 0 但小于 1 的符号为**正** 的数字值
* 扩大返回的随机数的范围
    * Math.random() * 需要扩大的倍数

**Array 数组对象**
* 数组对象是一个对象的集合,里面的对象可以是不同类型的.数组的每一个成员都有一个"下标",用来表示它在数组中的位置,是从零开始的.
* 数组定义的方法
    * 定义一个空数组 : var myArrayName = new Array();
    * 定义时指定有几个空元素的数组 : var myArray = new Array(n);
    * 定义数组的时候,直接初始化数据 : var myArray = [<元素1>,<元素2>,<元素3> ...];
        * 比如:定义数组并赋值 : var myArray = [2,3,4];

**concat() 数组链接**
* concat() 方法用于链接两个或者多个数组.此方法返回一个新的数组,**不改变**原来的数组.
* 语法 : arrayObject.concat(array1,array2,...,arrayN)
**注意** : 该方法只是将链接之后的结果作为返回值进行返回,但是**并不改变**原来的数组

**join()**
* join() 方法用于将数组中的所有元素放入一个字符串中.元素是通过指定的分隔符进行分隔(分隔符就是需要被传入的这个方法的参数)
* 语法 : arrayObject.join(分隔符);
* 这个方法只是返回分隔之后的字符串,不影响数组原来的内容.

**reverse()**
* reverse() 方法用于颠倒数组中元素的位置
* 语法: arrayObject.reverse()
* **注意** : 这个方法**会改变**原来的数组,而不是创建新的数组(比改变原数组)作为返回值.