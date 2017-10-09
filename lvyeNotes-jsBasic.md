* onchange事件
    * 在JavaScript中，当用户在单行文本框text和多行文本框textarea输入文本时，由于文本框内字符串的改变将会触发onchange事件。此外，在下拉列表select中一个选项的状态改变后也会触发onchange事件。

    * 具有获得onchange事件的元素有3个：
        * （1）单行文本框text；
        * （2）多行文本框textarea；
        * （3）下拉列表select；


* onselect事件
    * 在JavaScript中，当用户选中单行文本框text或多行文本框textarea的文本时，会触发onselect事件。onselect事件的具体过程是从鼠标按键被按下，到鼠标开始移动并选中内容的过程。这个过程并不包括鼠标键的放开。

    * 新手很容易把onselect和onchange这2个事件搞混，误以为下拉列表列表项的选中触发的事件是onselect。这一点大家要搞清楚：下拉列表列表项的选中触发的事件是onchange而不是onselect。