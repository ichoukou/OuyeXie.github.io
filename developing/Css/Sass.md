# Notes

```
@extend
@mixin
@include
@import
@if
@else
@for
@while
@each
@function
```

id 选择器以 "#" 来定义

类选择器以一个点号显示

CSS2 引入了一种新的简单选择器 - 通配选择器（universal selector），显示为一个星号（*）。该选择器可以与任何元素匹配，就像是一个通配符。

属性选择器可以根据元素的属性及属性值来选择元素。
如果需要根据属性值中的词列表的某个词进行选择，则需要使用波浪号（~）。

可以使用下面这个公式将像素转换为 em：pixels/16=em

text-decoration 属性大多用于去掉链接中的下划线: 
a:link {text-decoration:none;}

在新的 @font-face 规则中，您必须首先定义字体的名称（比如 myFirstFont），然后指向该字体文件。

@keyframes 规则用于创建动画。在 @keyframes 中规定某项 CSS 样式，就能创建由当前样式逐渐改为新样式的动画效果

# Details

<pre>
<code>
CSS 背景属性
属性	描述
background	简写属性，作用是将背景属性设置在一个声明中。
background-attachment	背景图像是否固定或者随着页面的其余部分滚动。
background-color	设置元素的背景颜色。
background-image	把图像设置为背景。
background-position	设置背景图像的起始位置。
background-repeat	设置背景图像是否及如何重复。

CSS 文本属性
属性	描述
color	设置文本颜色
direction	设置文本方向。
line-height	设置行高。
letter-spacing	设置字符间距。
text-align	对齐元素中的文本。
text-decoration	向文本添加修饰。
text-indent	缩进元素中文本的首行。
text-shadow	设置文本阴影。CSS2 包含该属性，但是 CSS2.1 没有保留该属性。
text-transform	控制元素中的字母。
unicode-bidi	设置文本方向。
white-space	设置元素中空白的处理方式。
word-spacing	设置字间距。

CSS 字体属性
属性	描述
font	简写属性。作用是把所有针对字体的属性设置在一个声明中。
font-family	设置字体系列。
font-size	设置字体的尺寸。
font-size-adjust	当首选字体不可用时，对替换字体进行智能缩放。（CSS2.1 已删除该属性。）
font-stretch	对字体进行水平拉伸。（CSS2.1 已删除该属性。）
font-style	设置字体风格。
font-variant	以小型大写字体或者正常字体显示文本。
font-weight	设置字体的粗细。

设置链接的样式
能够设置链接样式的 CSS 属性有很多种（例如 color, font-family, background 等等）。
链接的特殊性在于能够根据它们所处的状态来设置它们的样式。
链接的四种状态：
a:link - 普通的、未被访问的链接
a:visited - 用户已访问的链接
a:hover - 鼠标指针位于链接的上方
a:active - 链接被点击的时刻

CSS 列表属性(list)
属性	描述
list-style	简写属性。用于把所有用于列表的属性设置于一个声明中。
list-style-image	将图象设置为列表项标志。
list-style-position	设置列表中列表项标志的位置。
list-style-type	设置列表项标志的类型。
marker-offset	 

CSS Table 属性
属性	描述
border-collapse	设置是否把表格边框合并为单一的边框。
border-spacing	设置分隔单元格边框的距离。
caption-side	设置表格标题的位置。
empty-cells	设置是否显示表格中的空单元格。
table-layout	设置显示单元、行和列的算法。

CSS 边框属性
"CSS" 列中的数字指示哪个 CSS 版本定义了该属性。
属性	描述	CSS
outline	在一个声明中设置所有的轮廓属性。	2
outline-color	设置轮廓的颜色。	2
outline-style	设置轮廓的样式。	2
outline-width	设置轮廓的宽度。	2

术语翻译
element : 元素。
padding : 内边距，也有资料将其翻译为填充。
border : 边框。
margin : 外边距，也有资料将其翻译为空白或空白边。

CSS 边框属性
属性	描述
border	简写属性，用于把针对四个边的属性设置在一个声明。
border-style	用于设置元素所有边框的样式，或者单独地为各边设置边框样式。
border-width	简写属性，用于为元素的所有边框设置宽度，或者单独地为各边边框设置宽度。
border-color	简写属性，设置元素的所有边框中可见部分的颜色，或为 4 个边分别设置颜色。
border-bottom	简写属性，用于把下边框的所有属性设置到一个声明中。
border-bottom-color	设置元素的下边框的颜色。
border-bottom-style	设置元素的下边框的样式。
border-bottom-width	设置元素的下边框的宽度。
border-left	简写属性，用于把左边框的所有属性设置到一个声明中。
border-left-color	设置元素的左边框的颜色。
border-left-style	设置元素的左边框的样式。
border-left-width	设置元素的左边框的宽度。
border-right	简写属性，用于把右边框的所有属性设置到一个声明中。
border-right-color	设置元素的右边框的颜色。
border-right-style	设置元素的右边框的样式。
border-right-width	设置元素的右边框的宽度。
border-top	简写属性，用于把上边框的所有属性设置到一个声明中。
border-top-color	设置元素的上边框的颜色。
border-top-style	设置元素的上边框的样式。
border-top-width	设置元素的上边框的宽度。

CSS 外边距属性
属性	描述
margin	简写属性。在一个声明中设置所有外边距属性。
margin-bottom	设置元素的下外边距。
margin-left	设置元素的左外边距。
margin-right	设置元素的右外边距。
margin-top	设置元素的上外边距。

注释：只有普通文档流中块框的垂直外边距才会发生外边距合并。行内框、浮动框或绝对定位之间的外边距不会合并。

您可以使用 display 属性改变生成的框的类型。这意味着，通过将 display 属性设置为 block，可以让行内元素（比如 <a> 元素）表现得像块级元素一样。还可以通过把 display 设置为 none，让生成的元素根本没有框。这样的话，该框及其所有内容就不再显示，不占用文档中的空间

display 属性规定元素应该生成的框的类型。
可能的值
值	描述
none	此元素不会被显示。
block	此元素将显示为块级元素，此元素前后会带有换行符。
inline	默认。此元素会被显示为内联元素，元素前后没有换行符。
inline-block	行内块元素。（CSS2.1 新增的值）
list-item	此元素会作为列表显示。
run-in	此元素会根据上下文作为块级元素或内联元素显示。
compact	CSS 中有值 compact，不过由于缺乏广泛支持，已经从 CSS2.1 中删除。
marker	CSS 中有值 marker，不过由于缺乏广泛支持，已经从 CSS2.1 中删除。
table	此元素会作为块级表格来显示（类似 table），表格前后带有换行符。
inline-table	此元素会作为内联表格来显示（类似 table），表格前后没有换行符。
table-row-group	此元素会作为一个或多个行的分组来显示（类似 tbody）。
table-header-group	此元素会作为一个或多个行的分组来显示（类似 thead）。
table-footer-group	此元素会作为一个或多个行的分组来显示（类似 tfoot）。
table-row	此元素会作为一个表格行显示（类似 tr）。
table-column-group	此元素会作为一个或多个列的分组来显示（类似 colgroup）。
table-column	此元素会作为一个单元格列显示（类似 col）
table-cell	此元素会作为一个表格单元格显示（类似 td 和 th）
table-caption	此元素会作为一个表格标题显示（类似 caption）
inherit	规定应该从父元素继承 display 属性的值。

CSS 定位机制
CSS 有三种基本的定位机制：普通流、浮动和绝对定位。
除非专门指定，否则所有框都在普通流中定位。也就是说，普通流中的元素的位置由元素在 (X)HTML 中的位置决定。
块级框从上到下一个接一个地排列，框之间的垂直距离是由框的垂直外边距计算出来。
行内框在一行中水平布置。可以使用水平内边距、边框和外边距调整它们的间距。但是，垂直内边距、边框和外边距不影响行内框的高度。由一行形成的水平框称为行框（Line Box），行框的高度总是足以容纳它包含的所有行内框。不过，设置行高可以增加这个框的高度。

CSS position 属性
通过使用 position 属性，我们可以选择 4 种不同类型的定位，这会影响元素框生成的方式。
position 属性值的含义：
static
元素框正常生成。块级元素生成一个矩形框，作为文档流的一部分，行内元素则会创建一个或多个行框，置于其父元素中。
relative
元素框偏移某个距离。元素仍保持其未定位前的形状，它原本所占的空间仍保留。
absolute
元素框从文档流完全删除，并相对于其包含块定位。包含块可能是文档中的另一个元素或者是初始包含块。元素原先在正常文档流中所占的空间会关闭，就好像元素原来不存在一样。元素定位后生成一个块级框，而不论原来它在正常流中生成何种类型的框。
fixed
元素框的表现类似于将 position 设置为 absolute，不过其包含块是视窗本身。

CSS 定位属性
CSS 定位属性允许你对元素进行定位。
属性	描述
position	把元素放置到一个静态的、相对的、绝对的、或固定的位置中。
top	定义了一个定位元素的上外边距边界与其包含块上边界之间的偏移。
right	定义了定位元素右外边距边界与其包含块右边界之间的偏移。
bottom	定义了定位元素下外边距边界与其包含块下边界之间的偏移。
left	定义了定位元素左外边距边界与其包含块左边界之间的偏移。
overflow	设置当元素的内容溢出其区域时发生的事情。
clip	设置元素的形状。元素被剪入这个形状之中，然后显示出来。
vertical-align	设置元素的垂直对齐方式。
z-index	设置元素的堆叠顺序。

CSS 选择器参考手册
选择器	描述
[attribute]	用于选取带有指定属性的元素。
[attribute=value]	用于选取带有指定属性和值的元素。
[attribute~=value]	用于选取属性值中包含指定词汇的元素。
[attribute|=value]	用于选取带有以指定值开头的属性值的元素，该值必须是整个单词。
[attribute^=value]	匹配属性值以指定值开头的每个元素。
[attribute$=value]	匹配属性值以指定值结尾的每个元素。
[attribute*=value]	匹配属性值中包含指定值的每个元素。

伪类
W3C："W3C" 列指示出该属性在哪个 CSS 版本中定义（CSS1 还是 CSS2）。
属性	描述	CSS
:active	向被激活的元素添加样式。	1
:focus	向拥有键盘输入焦点的元素添加样式。	2
:hover	当鼠标悬浮在元素上方时，向元素添加样式。	1
:link	向未被访问的链接添加样式。	1
:visited	向已被访问的链接添加样式。	1
:first-child	向元素的第一个子元素添加样式。	2
:lang	向带有指定 lang 属性的元素添加样式。	2

伪元素
W3C："W3C" 列指示出该属性在哪个 CSS 版本中定义（CSS1 还是 CSS2）。
属性	描述	CSS
:first-letter	向文本的第一个字母添加特殊样式。	1
:first-line	向文本的首行添加特殊样式。	1
:before	在元素之前添加内容。	2
:after	在元素之后添加内容。	2

CSS 尺寸属性
CSS 尺寸属性允许你控制元素的高度和宽度。同样，还允许你增加行间距。
属性	描述
height	设置元素的高度。
line-height	设置行高。
max-height	设置元素的最大高度。
max-width	设置元素的最大宽度。
min-height	设置元素的最小高度。
min-width	设置元素的最小宽度。
width	设置元素的宽度。

CSS 分类属性 (Classification)
CSS 分类属性允许你控制如何显示元素，设置图像显示于另一元素中的何处，相对于其正常位置来定位元素，使用绝对值来定位元素，以及元素的可见度。
属性	描述
clear	设置一个元素的侧面是否允许其他的浮动元素。
cursor	规定当指向某元素之上时显示的指针类型。
display	设置是否及如何显示元素。
float	定义元素在哪个方向浮动。
position	把元素放置到一个静态的、相对的、绝对的、或固定的位置中。
visibility	设置元素是否可见或不可见。

新的边框属性
属性	描述	CSS
border-image	设置所有 border-image-* 属性的简写属性。	3
border-radius	设置所有四个 border-*-radius 属性的简写属性。	3
box-shadow	向方框添加一个或多个阴影。	3

新的背景属性
属性	描述	CSS
background-clip	规定背景的绘制区域。	3
background-origin	规定背景图片的定位区域。	3
background-size	规定背景图片的尺寸。	3

新的文本属性
属性	描述	CSS
hanging-punctuation	规定标点字符是否位于线框之外。	3
punctuation-trim	规定是否对标点字符进行修剪。	3
text-align-last	设置如何对齐最后一行或紧挨着强制换行符之前的行。	3
text-emphasis	向元素的文本应用重点标记以及重点标记的前景色。	3
text-justify	规定当 text-align 设置为 "justify" 时所使用的对齐方法。	3
text-outline	规定文本的轮廓。	3
text-overflow	规定当文本溢出包含元素时发生的事情。	3
text-shadow	向文本添加阴影。	3
text-wrap	规定文本的换行规则。	3
word-break	规定非中日韩文本的换行规则。	3
word-wrap	允许对长的不可分割的单词进行分割并换行到下一行。	3

新的转换属性
下面的表格列出了所有的转换属性：
属性	描述	CSS
transform	向元素应用 2D 或 3D 转换。	3
transform-origin	允许你改变被转换元素的位置。	3
2D Transform 方法
函数	描述
matrix(n,n,n,n,n,n)	定义 2D 转换，使用六个值的矩阵。
translate(x,y)	定义 2D 转换，沿着 X 和 Y 轴移动元素。
translateX(n)	定义 2D 转换，沿着 X 轴移动元素。
translateY(n)	定义 2D 转换，沿着 Y 轴移动元素。
scale(x,y)	定义 2D 缩放转换，改变元素的宽度和高度。
scaleX(n)	定义 2D 缩放转换，改变元素的宽度。
scaleY(n)	定义 2D 缩放转换，改变元素的高度。
rotate(angle)	定义 2D 旋转，在参数中规定角度。
skew(x-angle,y-angle)	定义 2D 倾斜转换，沿着 X 和 Y 轴。
skewX(angle)	定义 2D 倾斜转换，沿着 X 轴。
skewY(angle)	定义 2D 倾斜转换，沿着 Y 轴。

转换属性
下面的表格列出了所有的转换属性：
属性	描述	CSS
transform	向元素应用 2D 或 3D 转换。	3
transform-origin	允许你改变被转换元素的位置。	3
transform-style	规定被嵌套元素如何在 3D 空间中显示。	3
perspective	规定 3D 元素的透视效果。	3
perspective-origin	规定 3D 元素的底部位置。	3
backface-visibility	定义元素在不面对屏幕时是否可见。	3
2D Transform 方法
函数	描述
matrix3d(n,n,n,n,n,n,
n,n,n,n,n,n,n,n,n,n)	定义 3D 转换，使用 16 个值的 4x4 矩阵。
translate3d(x,y,z)	定义 3D 转化。
translateX(x)	定义 3D 转化，仅使用用于 X 轴的值。
translateY(y)	定义 3D 转化，仅使用用于 Y 轴的值。
translateZ(z)	定义 3D 转化，仅使用用于 Z 轴的值。
scale3d(x,y,z)	定义 3D 缩放转换。
scaleX(x)	定义 3D 缩放转换，通过给定一个 X 轴的值。
scaleY(y)	定义 3D 缩放转换，通过给定一个 Y 轴的值。
scaleZ(z)	定义 3D 缩放转换，通过给定一个 Z 轴的值。
rotate3d(x,y,z,angle)	定义 3D 旋转。
rotateX(angle)	定义沿 X 轴的 3D 旋转。
rotateY(angle)	定义沿 Y 轴的 3D 旋转。
rotateZ(angle)	定义沿 Z 轴的 3D 旋转。
perspective(n)	定义 3D 转换元素的透视视图。

过渡属性
下面的表格列出了所有的转换属性：
属性	描述	CSS
transition	简写属性，用于在一个属性中设置四个过渡属性。	3
transition-property	规定应用过渡的 CSS 属性的名称。	3
transition-duration	定义过渡效果花费的时间。默认是 0。	3
transition-timing-function	规定过渡效果的时间曲线。默认是 "ease"。	3
transition-delay	规定过渡效果何时开始。默认是 0。	3

CSS3 动画属性
下面的表格列出了 @keyframes 规则和所有动画属性：
属性	描述	CSS
@keyframes	规定动画。	3
animation	所有动画属性的简写属性，除了 animation-play-state 属性。	3
animation-name	规定 @keyframes 动画的名称。	3
animation-duration	规定动画完成一个周期所花费的秒或毫秒。默认是 0。	3
animation-timing-function	规定动画的速度曲线。默认是 "ease"。	3
animation-delay	规定动画何时开始。默认是 0。	3
animation-iteration-count	规定动画被播放的次数。默认是 1。	3
animation-direction	规定动画是否在下一周期逆向地播放。默认是 "normal"。	3
animation-play-state	规定动画是否正在运行或暂停。默认是 "running"。	3
animation-fill-mode	规定对象动画时间之外的状态。	3

新的多列属性
下面的表格列出了所有的转换属性：
属性	描述	CSS
column-count	规定元素应该被分隔的列数。	3
column-fill	规定如何填充列。	3
column-gap	规定列之间的间隔。	3
column-rule	设置所有 column-rule-* 属性的简写属性。	3
column-rule-color	规定列之间规则的颜色。	3
column-rule-style	规定列之间规则的样式。	3
column-rule-width	规定列之间规则的宽度。	3
column-span	规定元素应该横跨的列数。	3
column-width	规定列的宽度。	3
columns	规定设置 column-width 和 column-count 的简写属性。	3

新的用户界面属性
下面的表格列出了所有的转换属性：
属性	描述	CSS
appearance	允许您将元素设置为标准用户界面元素的外观	3
box-sizing	允许您以确切的方式定义适应某个区域的具体内容。	3
icon	为创作者提供使用图标化等价物来设置元素样式的能力。	3
nav-down	规定在使用 arrow-down 导航键时向何处导航。	3
nav-index	设置元素的 tab 键控制次序。	3
nav-left	规定在使用 arrow-left 导航键时向何处导航。	3
nav-right	规定在使用 arrow-right 导航键时向何处导航。	3
nav-up	规定在使用 arrow-up 导航键时向何处导航。	3
outline-offset	对轮廓进行偏移，并在超出边框边缘的位置绘制轮廓。	3
resize	规定是否可由用户对元素的尺寸进行调整。	3

</code>
</pre>

# Reference
 - http://www.ruanyifeng.com/blog/2012/06/sass.html
 - http://www.w3school.com.cn/css/css_intro.asp