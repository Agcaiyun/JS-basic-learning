>  因为更喜欢编辑器中的快捷键，而且在这里与 Git 接触更多。所以将这个笔记暂时托管到 GitHub 上面

# 在这里记录的是在 慕课网 JS初级教程 中学习到的之前没注意到的知识

### 数据类型的隐式转换

* ```+``` ：

    * 两侧都是**数字**，则计算数字的**和**
    * 两侧都是**字符**，则作为 **连字符**
    * 如果一侧为**字符**，一侧为**数字**，则作为**连字符**
    * 32 + 32  // 64
    * "32" + 32 // "3232"
    * "32" - 32 // 0
* ```-```：
    * 只会作为 **减号** 来使用

* 小技巧
    * 如果想将 **字符**转换为 **数字** 则：``` str - 0```；
    * 如果想将 **数字**转换为 **字符**，则： ```num + ''```

### <script type="text/javascript">

* 表示```<script></script> ```之间的是 文本类型```（text）``` ，```javascrit``` 是为了告诉浏览器前面的文本是属于 ```javascript ```语言

### <script> </script> 的放置位置
* 如果 <script> </script> 中的内容是初始化的 ```JS``` ，则必须放在 ```head``` 里面，因为初始化都要求提前进行（如给页面``` body ```设置 ```css``` 等）
* 而如果是通过时间调用执行的``` function``` 那么对位置没有什么要求

### 变量区分大小写
* 在 ```JS``` 中，变量是区分大小写的
* 变量不声明也不会报错，但是如果不声明是定义为 **全局** 变量的，很容易会造成 **全局污染** ，所以一般要求变量都是要声明后才能使用的

### white-space：pre；
* 这个属性表示：空白会被浏览器保留
* 比如：```document.write("<span style="white-space:pre">" + "1    2                    3" + "</span>");```   

### confirm
* ```confirm``` 消息对话框通常用于允许用户做选择的动作。
* 语法：
    * ```confirm(str) ```;
* 参数说明
    * ```str ```: 在消息对话框中要显示的文本
    * 返回只 ： ```Boolean``` 值
* 返回值
    * 当用户点击"确定" 按钮时，返回``` true```
    * 当用户点击"取消" 按钮时，返回 ```false```
* 例如：

```
<script type="text/javascript">
    var mymessage=confirm("你喜欢JavaScript吗?");
    if(mymessage==true)
    {   document.write("很好,加油!");   }
    else
    {  document.write("JS功能强大，要学习噢!");   }
</script>
```

###  prompt
* 语法：
    *``` prompt(str1,str2);```
* 参数说明：
    * ```str1 ```: 要显示在消息对话框中的文本，不可修改
    * ```str2 ```： 文本框中的内容，可以修改
* 返回值：
    * 点击确定按钮，文本框中的内容将作为函数返回值
    * 点击取消按钮，将返回 ```null```
* eg

    ```
    var myname=prompt("请输入你的姓名:");
    if(myname!=null)
    {   alert("你好"+myname); }
    else
    {  alert("你好 my friend.");  }

    ```

### 打开新窗口 (window.open)
* ```open()``` 方法可以查找一个已经存在 或者 新建 的浏览器窗口
* 语法：``` window.open([URL]``` , [窗口名称] , [参数字符串])
* 参数说明
    * ```URL``` ： 可选参数，在窗口中要显示网页的网址或路径。如果省略这个参数，或者它的值是空字符串，那么窗口就不显示任何文档
    * 窗口名称 ： 可选参数，被打开窗口的名称
        * 该名称由字母、数字和下划线字符组成
        * ```"._top"``` ```"._blank"``` ```"_self"``` 具有特殊意义的名称
            * ```_blank```: 在新窗口显示目标网页
            *``` _self```: 在当前窗口显示目标网页
            * ```_top```: 框架网页中在上部窗口中显示目标网页
        * 相同``` name ```的窗口只能创建一个，要想创建多个窗口则 ```name ```不能相同
        * ```name``` 不能包含空格
    * 参数字符串： 可选参数，设置窗口参数，各参数用逗号隔开（有大概``` 8 ```个常用的窗口参数，需要的可以 ```Google or baidu``` ，这里就不记录了（记了估计也还是在忘记的时候直接``` Google ```的情况过
* eg 
```
<script type="text/javascript"> window.open('http://www.imooc.com','_blank','width=300,height=200,menubar=no,toolbar=no, status=no,scrollbars=yes')
</script>
```
> 打开 ```http://www.imooc.com``` 网站，大小为```300px * 200px```，无菜单，无工具栏，无状态栏，有滚动条窗口：

**注意** 
* 运行结果考虑浏览器兼容问题

### 关闭窗口 （window.close)
* 用法 ：``` window.close()```; //关闭本窗口  或者``` <窗口对象>.close()```;  //关闭指定的窗口
* eg
```
<script>
    var mywin = window.open('http://www.imooc.com');   //将新打开的窗口对象，存在变量  mywin 中
    mywin.close();
</script>
```
> 上面代码在打开新窗口的同时，关闭该窗口，看不到被打开的窗口

### innerHTML 
* ```innerHTML ```属性用于获取或者替换``` HTM``` 元素的内容
* 语法：```Object.innerHTML```
**注意：**
* ```Object``` 是获取的**元素对象**，如同 通过``` document.getElementById("ID") ```获取的元素（也是元素这个对象，是个对象）
* ```innerHTML ``` 严格区分大小写

### className
* ```className``` 属性设置 或 返回 元素的``` class``` 属性
* 语法：``` object.className = classname```;
* 作用： 
    * 获取元素的 ```class``` 属性
    * 为网页内的某个元素指定一个``` css ```样式来更改该元素的外观

### DOM自定义属性 getAttribute/setAttribute/removeAttribute

* 函数语法 
    * ```object.attributes```                 : 属性返回包含被选中的节点属性的 NamedNodeMap
    * ```object.getAttribute(name)```         : 方法通过名称获取属性的值
    * ```object.setAttribute(name,value)```   : 方法创建或改变某个新属性
    * ```object.removeAttribute(name) ```     : 方法通过名称删除属性的值
        * ``` removeAttribute()``` 与 ```removeAttributeNode()```  方法的差异是：
            * ```removeAttributeNode() ``` 方法删除指定的 ```Attr``` 对象，而``` removeAttribute() ```方法删除具有指定名称的属性，结果是相同的
            * ``` removeAttribute()``` 这个方法不返回值，而 ```removeAttributeNode()``` 方法返回被删除的属性，以``` Attr ```对象的形式
