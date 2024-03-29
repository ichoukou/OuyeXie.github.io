# Notes

 - @import
import a file (only have to import in main.scss and all other imported files can use it)

 - a[href][title]
属性选择器: 同时有 href 和 title 属性的 HTML 超链接

 - h1 em
后代选择器: 作为 h1 元素后代的 em 元素

 - div>p
子元素选择器: 选取父元素是 <div> 元素的每个 <p> 元素

 - h1 + p
相邻兄弟选择器: 选择紧接在 h1 元素后出现的段落，h1 和 p 元素拥有共同的父元素

 - A ~ B
General sibling selectors: The ~ combinator separates two selectors and matches the second element only if it is preceded by the first, and both share a common parent.

 - a:link
伪类: 

<pre>
属性	描述	CSS
:active	向被激活的元素添加样式。	1
:focus	向拥有键盘输入焦点的元素添加样式。	2
:hover	当鼠标悬浮在元素上方时，向元素添加样式。	1
:link	向未被访问的链接添加样式。	1
:visited	向已被访问的链接添加样式。	1
:first-child	向元素的第一个子元素添加样式。	2
:lang	向带有指定 lang 属性的元素添加样式。	2
</pre>

 - :after
伪元素:

<pre>
属性	描述	CSS
:first-letter	向文本的第一个字母添加特殊样式。	1
:first-line	向文本的首行添加特殊样式。	1
:before	在元素之前添加内容。	2
:after	在元素之后添加内容。	2
</pre>

 - &
using the & as the parent selector name and to join it with the rest of the string

<pre>
.news-tag-bg {
      background-color: $primary-color;
      color: $default-color;
      border-radius: 5px;
      padding-right: 10px;
      padding-left: 10px;
      margin-right: 10px;
       &:active,
       &.active {
          color: #fff;
          background-color: darken($primary-color, 10%);
        }
    }
</pre>
一个元素不一定有active状态,这时可以加一个active的class,是一种通行做法.

 - duplicated definition
the later definition will complement the ones before and change the certain rules if it is already defined.

 - margin:auto
把左和右外边距设置为 auto，规定的是均等地分配可用的外边距。结果就是居中的元素：

 - style="font-size:10px;font-color:#ff0000"
內联写法

 - .push-right:after{
     right: 15px;
     content: '\e826';
   }
    - http://blog.jobbole.com/49173/
    - https://www.zhihu.com/question/22022905
    - https://github.com/twbs/ratchet
    - [right: absolute position](http://www.w3school.com.cn/css/css_positioning_absolute.asp)
    
 - line-height: 18px;
在css中是没有行距(leading)这种属性(attribute)的，但是有行高(line-height)属性

 - background: #db6d16
   url(../images/headers/about.jpg);
给#header层添加背景图案

 - text-decoration: none;
让下划线消失

 - background-position: 0 -50px;
显示背景图片的中部，因此需要将背景图片向上移动50px

 - @include arrow($size: 5px, $color: darken($chrome-color, 5%), $start: 15px);
    -http://cssarrowplease.com/

 - !important
!important的出现就是为了让用户自己设置被执行语句的优先级

 - !default
sass的默认变量一般是用来设置默认值，然后根据需求来覆盖的，覆盖的方式也很简单，只需要在默认变量之前重新声明下变量即可

 - !global
从名称上看是一个全局变量，但和全面似乎没有太大区别，不过我们来换过一种测试效果，将!gobal放在内部，其也将会影响全局

 - -webkit-appearance : none ;
    - [来移除原生控件样式](http://www.daqianduan.com/4606.html)
    
 - cursor 一些不同的光标
    - http://www.w3school.com.cn/cssref/pr_class_cursor.asp
    
 - z-index 属性设置元素的堆叠顺序。拥有更高堆叠顺序的元素总是会处于堆叠顺序较低的元素的前面。
    - http://www.w3school.com.cn/cssref/pr_pos_z-index.asp
    
 - overflow 属性规定当内容溢出元素框时发生的事情
    - http://www.w3school.com.cn/cssref/pr_pos_overflow.asp
   
 - class 顺序
    - [结论：若同时应用多个class，后定义的优先（即近者优先），加上!important最优先！](http://blog.csdn.net/szwangdf/article/details/4219878)
    - http://www.w3school.com.cn/css/css_selector_class.asp
    
 - transform 属性向元素应用 2D 或 3D 转换。该属性允许我们对元素进行旋转、缩放、移动或倾斜。
    - http://www.w3school.com.cn/cssref/pr_transform.asp
    
 - pointer-events
    - https://developer.mozilla.org/en-US/docs/Web/CSS/pointer-events
    
 - -webkit-overflow-scrolling : touch; 快速滚动和回弹的效果
    - http://blog.csdn.net/hursing/article/details/9186199
    
 - aria-hidden="true" 为了避免 屏幕识读设备抓取非故意的和可能产生混淆的输出内容（尤其是当图标纯粹作为装饰用途时），我们为这些图标设置了 aria-hidden="true" 属性。
    - http://www.imooc.com/qadetail/62014
 
 - -webkit-tap-highlight-color 当用户点击iOS的Safari浏览器中的链接或JavaScript的可点击的元素时，覆盖显示的高亮颜色。
    - http://www.css88.com/webkit/-webkit-tap-highlight-color/
    
 - perspective, -webkit-perspective 属性定义 3D 元素距视图的距离，以像素计。该属性允许您改变 3D 元素查看 3D 元素的视图。
    - http://www.w3school.com.cn/cssref/pr_perspective.asp
 - cubic-bezier 
    - http://www.candoudou.com/archives/590
    - http://www.w3.org/TR/css3-transitions/#transition-timing-function_tag
    - http://cubic-bezier.com/
    
# Reference

 - http://www.ruanyifeng.com/blog/2012/06/sass.html
 - http://www.w3school.com.cn/cssref/css_selectors.asp
 - https://developer.mozilla.org/en-US/docs/Web/CSS/Reference
 - http://stackoverflow.com/questions/20515625/use-ampersand-in-selector-name-with-sass
 - http://blog.jobbole.com/49173/
 - https://www.zhihu.com/question/22022905
 - https://github.com/twbs/ratchet
 - http://www.wzsky.net/html/Website/CSS/112650.html
 - http://cssarrowplease.com/
 - http://www.cnblogs.com/lykbk/archive/2012/08/09/huhu345545.html
 - http://www.css88.com/archives/5402
 - http://www.daqianduan.com/4606.html
 - http://www.w3cplus.com/sassguide/syntax.html
 - http://www.w3cplus.com/preprocessor/sass-bring-change.html
 - http://www.w3school.com.cn/cssref/pr_class_cursor.asp
 - http://www.w3school.com.cn/cssref/pr_pos_z-index.asp
 - http://www.w3school.com.cn/cssref/pr_pos_overflow.asp
 - http://blog.csdn.net/szwangdf/article/details/4219878
 - http://www.w3school.com.cn/css/css_selector_class.asp
 - http://www.w3school.com.cn/cssref/pr_transform.asp
 - http://www.css88.com/webkit/-webkit-tap-highlight-color/
 - http://www.w3school.com.cn/cssref/pr_perspective.asp
 - http://www.candoudou.com/archives/590
 - http://www.w3.org/TR/css3-transitions/#transition-timing-function_tag
 - http://cubic-bezier.com/