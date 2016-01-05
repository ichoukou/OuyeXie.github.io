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

 -!important
!important的出现就是为了让用户自己设置被执行语句的优先级

 - -webkit-appearance : none ;
    - [来移除原生控件样式](http://www.daqianduan.com/4606.html)

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