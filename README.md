# FE-topic
前端面试题及要点
## css相关的问题
1. css选择器有哪些？ 答：id选择器\#id 类选择器\.class 标签选择器p div 等。重点：属性选择器\[href\]  ,然后问css选择器的优选级概念（也叫权重）。一般回答就是id选择器是100，类选择器是10 标签选择器是1（大致是这个意思）然后问属性选择器的优选级是多少(等于类选择器)，面试者需要清楚明了的说出这些选择器权重只能相加不能进位，!important 权重最高，相同权重的css，后面的会覆盖前面的。各类选择器的优先级
important声明 1,0,0,0
ID选择器 0,1,0,0
类选择器 0,0,1,0
伪类选择器 0,0,1,0
属性选择器 0,0,1,0
标签选择器 0,0,0,1
伪元素选择器 0,0,0,1
通配符选择器 0,0,0,0            详见链接[CSS选择器优先级与效率优化](https://segmentfault.com/a/1190000003064142) 这个文章后面还记录选择器的效率，可以深入了解。
2. css盒子模型详 常规content(width,height)+paddding+border+margin 这个没什么好问的主要问一下box-sizing属性可以改变盒子模型的计算方式。
3. css行内元素和块状元素区别1. 块状元素独占一行，行内元素可以共享一行（水平方向会一个个接着）。 2. 块状元素可设置width、height、margin、padding；行内元素则只能设置margin-left,margin-right,padding-left,padding-right.其他属性设置无效 3. 哪些属性可以让行内元素变为块状元素:display:block; float，position
4. position定位问题:根据父级元素postion值不是static的元素来定位，postion：relative的元素这是left，top则会偏移自身的位置。详见链接[position](http://www.w3school.com.cn/css/css_positioning.asp)
###以上问题皆为css基础概念。
5. css实现一个两栏布局(不用考虑兼容性，能说出多少说多少)：类似于QQ邮箱(左侧定宽200px，右侧铺满剩余窗口),能回答出2种方法的则水平一般,回答出3-4种则水平可以，回答出5+则水平不错。具体方法有：1. 左侧浮动，右侧设置margin-left:200px; 2. 左侧浮动右侧overflow:hidden，（问为什么可以，能答出触发BFC则加分)。 3. flexBox布局, 4. 栅格布局 5.绝对定位,6.用calc 计算，额我只能想到这6种.
6. 移动端布局：如何实现一个正方形来适配所有的手机，正方形边长为手机屏幕的宽。 1. 能答出padding:50%则是瞎闷，答出padding-top或者padding-bottom为50%则是正确，再问为什么，答案见这里[padding,margin百分比的计算](https://www.zhihu.com/question/20983035) [百分比妙用](https://segmentfault.com/a/1190000004231995) ,大致就是说：padding-top,padding-bottom这些属性的百分比是按照父级元素的宽来计算的。 2. 也可以用一个1px*1px的透明图片来撑起一个div。
###以上算是css的两个实例考验。都能答出来则水平不错。
(也可以再问问对浮动的理解，以及为什么要清除浮动,怎么清除浮动)
##html标签相关
1. html语义话的理解。这是个开放性的题目，能答出个123则说明比较喜欢钻研基础的知识,见链接[语义话理解](http://www.cnblogs.com/yizuierguo/archive/2009/07/26/1531112.html)
2. s 和 del 的语义话区别   strong 和em区别  这个题目比较难，额说没啥区别的一般就是不怎么深入去理解的。。。。一般只知道 strong 和em的区别  。。。反正我面试的能回答正确的很少。主要考察面试者对前端基础的一个钻研态度
##js相关：
1.js事件模型（也叫js事件机制） 一个事件会从document一直捕获传递到目标节点。。中间如果触发监听捕获的事件并且调用event.stopPropagation()；则此事件不会再继续向目标节点传递。这个事件到达目标节点之后，默认是不冒泡的。。只有event.bubbles为true的时候才会触发冒泡。
详见我的博客[js事件捕获和冒泡](http://myway.sinaapp.com/85.html)  重点问：是否所有的事件都能捕获（对）,是否所有的事件都冒泡(否)。哪些事件不能冒泡（这个能说出123就可以）.这个问题能都说完整则js水平尚可。否则，js不过关.
2. 事件委托机制及好处。答：主要是利用事件冒泡，根据event.target来获取目标元素,好处：减少事件的绑定，不用关心子元素的变化更新等。
3. ajax的完整过程w3c标准的就行。。。。这个考察基本功。。能答对则基础过关。
4. jsonp 原理及优缺点，答：优点：跨域，缺点：只能get，不能post，
> JSONP的优点是：它不像XMLHttpRequest对象实现的Ajax请求那样受到同源策略的限制；它的兼容性更好，在更加古老的浏览器中都可以运行，并且在请求完毕后可以通过调用callback的方式回传结果。JSONP的缺点则是：它只支持GET请求而不支持POST等其它类型的HTTP请求；它只支持跨域HTTP请求这种情况，不能解决不同域的两个页面之间如何进行JavaScript调用的问题。

