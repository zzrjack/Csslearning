# 一、一级题目

## 1. CSS选择器及其优先级



选择器名称	选择器符号	选择器优先级
行内样式	style={}			1000
id选择器	#id				100
类选择器	.className		 10
属性选择器	a[ref=‘atrName’]	10
伪类选择器	:hover			10
标签选择器	p				1
伪元素选择器	::after			1
兄弟选择器	+				0
子选择器	>					0
后代选择器	div p			0
通配符	*					0
**css优先级规则：**
*1、css选择规则的权重值不同时，权重值高的优先；*
*2、css选择规则的权重值相同时，后定义的规则优先；*
*3、css属性后面加 !important 时，无条件绝对优先；*

------------------------------------------------
## 2.display的属性值及其作用

1）none 用于隐藏元素，包括子元素会一并隐藏，在页面中好像不存在一样，其元素节点依然存在于DOM中。

2）block，将display属性设置为block，元素就变成了块级元素，块级元素是正常显示的。块级元素独占一行，默认宽度为父元素的宽度，常用的有 div ul li ol p h1~h6 headr、dd 。需要注意的是 *p 标签和h1~h6标签，里面是不能嵌套块级元素的。*

3）inline 行内元素。不会独占一行，像 sapn 不会独占一行。行内元素会根据前一个元素的位置流动，并且不可设置大小，元素大小有内容撑开。

4）inline-block，行内块级元素，即可一以像块元素一样设置大小，也不会独占一行 。 例如 input 和 img

5）**flex**

1.display：flex，设置为弹性属性，弹性属性可以灵活的设计响应式布局，无需定位和浮动。
2.flex-direction 规定弹性容器内的弹性项目的方向。
3.justify-content 当弹性项目没有用到主轴上的所有可用空间时，水平对齐这些项目。
4.align-items 当弹性项目没有用到主轴上的所有可用空间时，垂直对齐这些项。
5.flex-wrap 规定弹性项目是否应该换行，若一条 flex 线上没有足够的空间容纳它们。
6.align-content 修改 flex-wrap 属性的行为。与 align-items 相似，但它不对齐弹性项目，而是对齐 flex 线。
7.flex-flow flex-direction 和 flex-wrap 的简写属性。
8.order 规定弹性项目相对于同一容器内其余弹性项目的顺序。
9.align-self 用于弹性项目。覆盖容器的 align-items 属性。
10.lex flex-grow、flex-shrink 以及 flex-basis 属性的简写属性。

6）display其它不常用属性、
1.list-item： 此元素会作为列表显示。
2.run-in： 此元素会根据上下文作为块级元素或内联元素显示。
3.table： 此元素会作为块级表格来显示，表格前后带有换行符。
4.inline-table： 此元素会作为内联表格来显示，表格前后没有换行符。
5.table-row-group： 此元素会作为一个或多个行的分组来显示
6.table-header-group： 此元素会作为一个或多个行的分组来显示
7.table-footer-group： 此元素会作为一个或多个行的分组来显示
8.table-row： 此元素会作为一个表格行显示
9.table-column-group： 此元素会作为一个或多个列的分组来显示
10.table-column： 此元素会作为一个单元格列显示
11.table-cell： 此元素会作为一个表格单元格显示
12.table-caption： 此元素会作为一个表格标题显示
13.inherit： 规定应该从父元素继承 display 属性的值。

------------------------------------------------
## 3.块级，行内，行内块的区别

**块级元素**

每个块级元素通常都会独占一行或者是多行，可以对其单独设置高度,宽度以及对齐等属性。
常见的块级元素有：<h1>~<h6>,<p>,<div>,<ul>,<ol>,<li>等 

**行内元素**

行内元素（内联元素）：不占有独立的区域**，仅仅依靠自己的字体大小或者是图像大小来支撑结构**。 
一般不可以设置宽度，高度以及对齐等属性。 
常见的行内元素有：<a >,<strong>,<b>,<em>,<del>,<span >等
默认的宽度就是它本身的宽度 

**行内块级元素**

行内块级元素，它既具有块级元素的特点，也有行内元素的特点，它可以自由设置元宽度和高度，
也可以在一行中放置多个行内块级元素。比如input、img就是行内块级元素，它可以设置高宽以及一行多个。 

**行内元素、块级元素、行内块级元素有什么区别**
块级元素的特点：

块级元素会**独占一行**
**高度，行高，外边距和内边距都可以单独设置**
宽度默认是容器的100%
可以容纳内联元素和其他的块级元素 

**行内元素的特点：**

和相邻的行内元素在一行上
**高度和宽度无效，但是水平方向上的padding和margin可以设置，垂直方向上的无效 默认的宽度就是它本身的宽度**
**行内元素只能容纳纯文本或者是其他的行内元素（a标签除外）**

**行内块级元素的特点：**

和其他行内或行内块级元素元素放置在同一行上；
元素的高度、宽度、行高以及顶和底边距都可设置。 

如何将行内元素转为块级元素

display：block ，定义元素为块级元素 
display : inline ，定义元素为行内元素 
display：inline-block，定义元素为行内块
------------------------------------------------
## 4.隐藏元素的方法有哪些

（1）使用 display:none;隐藏元素，渲染树不会包含该渲染对象，因此该元素不会在页面中占据位置，也不会响应绑定的监听事件。

-（2）使用 visibility:hidden;隐藏元素。元素在页面中仍占据空间，但是不会响应绑定的监听事件。

-（3）使用 opacity:0;将元素的透明度设置为 0，以此来实现元素的隐藏。元素在页面中仍然占据空间，并且能够响应元素绑定的监听事件。

-（4）通过使用绝对定位将元素移除可视区域内，以此来实现元素的隐藏。

-（5）通过 z-index 负值，来使其他元素遮盖住该元素，以此来实现隐藏。

-（6）通过 clip/clip-path 元素裁剪的方法来实现元素的隐藏，这种方法下，元素仍在页面中占据位置，但是不会响应绑定的监听事件。

-（7）通过 transform:scale(0,0)来将元素缩放为 0，以此来实现元素的隐藏。这种方法下，元素仍在页面中占据位置，但是不会响应绑定的监听事件。

<hr>

##5.display:none, visibility:hidden的区别

1.display:none是让这个元素失去块元素的效果，其本身这个元素也是直接消失，会影响到布局问题。

2.visibility:hidden:可以让元素消失，属于css样式，它只是简单的让元素看不见，但本身的位置还在，如果对div进行hidden，那么div除了看不见，其他所有的样式都在。

------------------------------------------------
## 6.盒子模型的理解

W3C定义的盒子模型包括margin、border、padding、content ，元素的width=content的宽度

IE盒子模型与W3C的盒子模型唯一区别就是元素的宽度，元素的width=content+padding+border

![img](CSS.assets/20160922110926392.dib)

W3C定义盒子模型与IE定义的盒子模型，IE定义的比较合理，元素的宽度应该包含border（边框）和padding（填充），这个和我们现实生活的盒子是一样的，W3C也认识到自己的问题了，所以在CSS3中新增了一个样式box-sizing，包含两个属性content-box 和 border-box。

1） **content-box**  元素的width=content+padding+border

2）**border-box**   元素的width=width（用样式指定的宽度）

------------------------------------------------
## 7.CSS3中有哪些新特性

CSS3的主要新特性：

### 1）选择器

丰富选择的目的：在标签中减少class和id属性的使用。
1）属性选择器
[属性名]
[属性名=属性值]
[属性名^=属性值]
[属性名$=属性值]
[属性名*=属性值]
2）结构性伪类
:first-child
:last-child
:nth-child(n)
:nth-last-child(n)
:nth-of-type(n)
:nth-last-of-type(n)
:only-child
:only-of-type
:empty
3）目标伪类
:target
4）UI元素状态伪类
:checked (只在Opera浏览器中有效)
:disabled
:enabled
:selection
5）否定伪类
:not()
6）通用兄弟元素选择器

### 2）阴影

1） 文本阴影（主流浏览器都支持，（IE9以上支持））
text-shadow: 水平偏移距离 垂直偏移距离 [模糊距离] [阴影的尺寸] [颜色] [inset];
2）文本自动换行（主流浏览器都支持）
word-wrap: normal|break-word;
3）单词拆分（主流浏览器都支持）
word-break: normal|break-all|keep-all;
4）文本拆分（所有主流浏览器都不支持）
text-wrap: normal|none|unrestricted|suppress;
5）文本溢出
a)单行文本溢出（重要）
text-overflow: clip|ellipsis|string;

### 3）形状转换（2D <-> 3D）

### 4）变形

### 5）动画（过渡动画、帧动画）

### 6）边框

1）圆角边框（掌握）
border-radius: 1-4 length|% / 1-4 length|%;
四个方位的词：top-left/top-right/bottom-left/bottom-right
2）边框阴影（IE9以上支持）
box-shadow: 水平偏移距离 垂直偏移距离 [模糊距离] [阴影的尺寸] [颜色] [inset];
3）边框图片(IE11.0及以后版本支持）
border-image：图片 向内偏移距离 宽度 图像区域超出边框的距离 重复效果;
重复效果：round/strech/repeat



### 7）多重背景

1）多重背景
background: 背景色 背景图片 平铺方式 位置,背景色 背景图片 平铺方式 位置,…
2）background-size：设定背景图像的尺寸。
background-size: 固定长度|百分比值|cover|contain;
3）background-origin：指定背景图像的位置区域。
background-origin: padding-box|border-box|content-box;
4）background-clip：设定背景的绘制区域。
background-clip: border-box|padding-box|content-box;
5）渐变背景
background-image: 线性渐变｜径向渐变



### 8）反射

### 9）文字

### 10）颜色函数（rgba/hsl/hsla）

1）RGBA
rgba(r,g,b,a)
r:红色 取值范围：0-255/0-100%
g:绿色 取值范围：0-255/0-100%
b:蓝色 取值范围：0-255/0-100%
a:不透明度 取值范围：0-1的一个小数
2）HSL
hsl(h,s,l)
h:色调 取值范围：0-360
s:饱和度 取值范围：0-100%
l:亮度 取值范围：0-100%
3）HSLA
hsla(h,s,l,a)
h:色调 取值范围：0-360
s:饱和度 取值范围：0-100%
l:亮度 取值范围：0-100%
a:不透明度 取值范围：0-1的一个小数

4）opacity
调整元素的不透明度，大多数情况下用于做元素的遮罩效果。取值范围：0-1的一个小数 IE8及8以下版本不支持opacity，处理兼容的方式，再添加一行代码来处理不透明度：filter:alpha(opacity=数值） 数值的范围：0-100

------------------------------------------------


### 11）滤镜（filter）

### 12）弹性布局

### 13）多列布局

### 14）栅格布局

### 15）盒模型

### 16）Web字体

### 17）媒体查询

<hr>

## 8.单行与多行文本溢出

### 单行：

1.使用宽度with，来限制宽度

2.使用white-space:nowrap/pre来强制限制换行；

3.使用overflow:hidden隐藏溢出文本；

使用text-flow:ellipsis来用...来表示隐藏的文本

------------------------------------------------
### 多行：

1. 使用[css3](https://so.csdn.net/so/search?q=css3&spm=1001.2101.3001.7020)自带的属性-webkit-box来改变

/*css代码：*/
 overflow: hidden;
        text-overflow: ellipsis;
        display:-webkit-box;
       -webkit-line-clamp: 2;/*行数*/
       -webkit-box-orient: vertical;

<hr>



## 9.对BFC的理解，如何创建BFC

BFC 全称：Block Formatting Context， 名为 “块级格式化上下文”。

W3C官方解释为：BFC它决定了元素如何对其内容进行定位，以及与其它元素的关系和相互作用，当涉及到可视化布局时，Block Formatting Context提供了一个环境，HTML在这个环境中按照一定的规则进行布局。

简单来说就是，BFC是一个完全独立的空间（布局环境），让空间里的子元素不会影响到外面的布局。那么怎么使用BFC呢，BFC可以看做是一个CSS元素属性

**如何触发**
这里简单列举几个触发BFC使用的CSS属性

overflow: hidden
display: inline-block
position: absolute
position: fixed
display: table-cell
display: flex
BFC的规则
BFC就是一个块级元素，块级元素会在垂直方向一个接一个的排列
BFC就是页面中的一个隔离的独立容器，容器里的标签不会影响到外部标签
垂直方向的距离由margin决定， 属于同一个BFC的两个相邻的标签外边距会发生重叠
计算BFC的高度时，浮动元素也参与计算

## 10.布局

### 1.两栏

- ####  ①侧边栏左浮动+正文部分overflow：auto

  ```html
  <head>
      <meta charset="UTF-8">
      <meta name="viewport" content="width=device-width, initial-scale=1.0">
      <title>Document</title>
      <style>
          .wrap{
              width:900px;
              margin:0 auto;
          }
          .left{
              width: 200px;
              height: 500px;
              background: #ccffff;
              float: left;
          }
          .right{
              height: 500px;
              overflow: auto;
              background: #ffcccc;
          }
      </style>
  </head>
  <body>
      <div class="wrap">
          <aside class="left"></aside>
          <div class="right">
              这里是正文！这里是正文！这里是正文！这里是正文！这里是正文！这里是正文！
          </div>
      </div>
  </body>
  </html>
  
  ```

  

- #### ②定位实现两栏布局

  ```html
  <!DOCTYPE html>
  <html lang="en">
  <head>
      <meta charset="UTF-8">
      <meta name="viewport" content="width=device-width, initial-scale=1.0">
      <title>Document</title>
      <style>
          .wrap{
              width:900px;
              margin:0 auto;
              position: relative;
          }
          .left{
              width:200px;
              height:500px;
              background: #ccffff;
              position: absolute;
              top:0;
              left:0;
          }
          .right{
              width:700px;
              height:500px;
              background: #ffcccc;
              position: absolute;
              top:0;
              right:0;
          }
      </style>
  </head>
  <body>
      <div class="wrap">
          <aside class="left"></aside>
          <div class="right">
              这里是正文！这里是正文！这里是正文！这里是正文！这里是正文！这里是正文！
          </div>
      </div>
  </body>
  </html>
  
  ```

  

- #### ③纯浮动形式

  ```html
  <!DOCTYPE html>
  <html lang="en">
  <head>
      <meta charset="UTF-8">
      <meta name="viewport" content="width=device-width, initial-scale=1.0">
      <title>Document</title>
      <style>
          .wrap{
              width:900px;
              margin:0 auto;
              overflow: hidden;
          }
          .left{
              width:200px;
              height:500px;
              background: #ccffff;
              float: left;
          }
          .right{
              width:700px;
              height:500px;
              background: #ffcccc;
              float: left;
          }
      </style>
  </head>
  <body>
      <div class="wrap">
          <aside class="left"></aside>
          <div class="right">
              这里是正文！这里是正文！这里是正文！这里是正文！这里是正文！这里是正文！
          </div>
      </div>
  </body>
  </html>
  
  ```

  

- #### ④浮动+常规流

  ```html
  <!DOCTYPE html>
  <html lang="en">
  <head>
      <meta charset="UTF-8">
      <meta name="viewport" content="width=device-width, initial-scale=1.0">
      <title>Document</title>
      <style>
          .wrap{
              margin:0 auto;
              width:80%;
          }
          .left{
              width:200px;
              height:500px;
              background: #ccffff;
              float: left;
          }
          .right{
              height: 500px;
              background: #ffcccc;
              margin-left:200px;
  
      </style>
  </head>
  <body>
      <div class="wrap">
          <aside class="left"></aside>
          <div class="right">
              这里是正文！这里是正文！这里是正文！这里是正文！这里是正文！这里是正文！
          </div>
      </div>
  </body>
  </html>
  
  ```

  

### 2.三栏

- #### ①流体float

  1.首先绘制左右两栏，左右分别对应浮动

  2.绘制中间栏，流出左右两栏距离与间距

  缺点：主要内容无法最先加载，当主要内容过多时影响用户体验

  ```html
  <style>
     .container {
      border: 1px solid red;
    }
    
  /*  流体布局,先绘制左右栏 */
  
    .left {
      float: left;
      width: 200px;
      height: 200px;
      background-color: aqua;
    }
    .right { 
      float: right;
      width: 200px;
      height: 200px;
      background-color: aquamarine;
    }
    .mid {
      background-color: cadetblue;
      height: 200px;
      margin-left: 220px;
      margin-right: 220px;
    } 
   
  
  </style>
  <body>
    <div class="container">
      <div class="left">left</div>
      <div class="right">right</div>
      <div class="mid">mid</div>
    </div>
  </body>
  
  ```

  

- #### ②bfc

  1.我们先把左右两栏元素浮动，中间栏不做其他属性，发现中间栏默认撑满全屏，这时候我们就可以利用BFC不会和浮动元素重叠的规则，把中间元素改成一个BFC，使用overflow:hidden或者display: flex达到中间栏自适应

  缺点：主要内容无法最先加载 ，当主要内容过多时影响用户体验

  ```html
  <style>
   .left {
      float: left;
      width: 200px;
      height: 200px;
      background-color: aqua;
      margin-right: 20px;
       
    }
    .right { 
      float: right;
      width: 200px;
      height: 200px;
      background-color: aquamarine;
      margin-left: 20px; 
      
    }
    .mid {
      background-color: cadetblue;
      height: 200px;
      overflow: hidden 
      /* display: flex */
    } 
  
  
  </style>
  <body>
    <div class="container">
      <div class="left">left</div>
      <div class="right">right</div>
      <div class="mid">mid</div>
    </div>
  </body>
  
  
  ```

  

- #### ③flex

  1.flex属性的完整写法是:flex-grow项目放大比例、flex-shrink项目缩小比例 、flex-basis项目占据属性

  1.项目绘制按照左中右排列

  2.父元素使用flex属性

  3.(1)左右两栏固定宽度
  赋值给元素width属性
  赋值给元素flex属性：flex: 0 1 200px(放大比例0，缩小比例1，项目宽度200px）
  (2)中间使用flex:1占据剩余空间

  缺点：无法兼容所有浏览器

  ```html
  <style>
   .container {
      border: 1px solid red;
      display: flex;
    }
    .left {
      width: 200px;
      height: 200px;
      background-color: aqua;
    }
    .right { 
      width: 200px;
      height: 200px;
      background-color: aquamarine;
    }
    .mid {
      background-color: cadetblue;
      height: 200px;
      flex-grow: 1;
      margin-left: 20px; 
      margin-right: 20px;
    } 
  </style>
  
  <body>
    <div class="container">
      <div class="left">left</div>
      <div class="mid">mid</div>
      <div class="right">right</div>
    </div>
  </body>
  
  ```

  

- #### ④position

  1.父元素使用相对定位
  2.两侧子元素使用绝对定位
  3.中间元素不做定位处理，只留出空间就好

  优点：主要内容可以优先加载

  ```html
   .container {
      position: relative;
    }
  
    .left {
      position: absolute;
      width: 200px;
      height: 200px;
      left: 0;
      top: 0; 
      background-color: aqua;
    }
  
    .right {
      position: absolute;
      top: 0;
      right: 0;
      width: 200px;
      height: 200px;
      background-color: aquamarine;
    }
  
    .mid {
      background-color: cadetblue;
      height: 200px;
  	margin: 0 220px;
    }
  </style>
  <body>
    <div class="container">
      <div class="mid">mid</div>
      <div class="left">left</div>
      <div class="right">right</div>
    </div>
  </div>
  </body>
  
  ```

  

- #### ⑤Table

  1.先设置外边盒子采用表格布局
  2.设置子元素为表格单元格格式
  3.左右两栏设置宽度，中间无需设置

  缺点：无法设置栏间距

  ```html
    .container {
      display: table;
      width: 100%;
    }
    .left, .mid, .right {
      display: table-cell;
    }
  
    .left {
      width: 200px;
      height: 200px;
      background-color: aqua;
    }
    .right { 
      width: 200px;
      height: 200px;
      background-color: aquamarine;
    }
    .mid {
      background-color: cadetblue;
      height: 200px;
    } 
  
  </style>
  <body>
    <div class="container">
      <div class="left">left</div>
      <div class="mid">mid</div>
      <div class="right">right</div>
    </div>
  </div>
  </body>
  
  ```

  

<hr>

### 3.水平垂直居中

- 一、使用 margin:auto

  当元素有给定的高度以及宽度的时候，使用 margin: auto; 元素仅会水平居中，并不会进行垂直居中。
  此时就需要设置元素的 position 为 absolute，父级元素的 position 为 relative，同时元素的上下左右都需要设置为 0。

  ```html
  <div class="box">
    <div class="center1"></div>
  </div>
  
  .box{  
     width: 200px; 
     height: 200px;
     background-color: #eee;  
     position: relative;  
     margin-top: 20px;
  }
  .center1{  
     width: 50px;  
     height: 50px;  
     background-color: #00ACED;  
     margin: auto;  
     position: absolute;  
     top: 0;  
     left: 0;  
     right: 0;  
     bottom: 0;
  }
  
  ```

  

- 二、使用 position:absolute

  当已经知道了要进行水平垂直居中的元素的宽高时，就可以通过设置 position: absolute 来实现。
  但是，使用的同时还需要结合其他属性才完整实现。
  因为，单是设置 absolute，上左距离均为一半，就会出现下面这种情况。
  很显然可以看到，元素并不是完全居中，仅只有左上角的位置在中心点。\

  因此想要实现元素完全水平垂直居中，在设置了 absolute 定位后，可以设置 margin 值为负，或者使用 calc 来计算，上左距离在 50% 的基础上还要减去元素本身一半的宽高。

  margin 值为负或者 calc 计算均是在已知元素宽高的情况下，假设不知道元素的宽高，那么怎么实现水平垂直居中呢？这里就可以使用 transform 属性，通过坐标位移来实现居中。

  ------------------------------------------------

  ```html
  /* 结合 margin */
  .center2{  
  	width: 50px;  
  	height: 50px;  
  	background-color: #7FFFD4;  
  	position: absolute;  
  	left: 50%;  
  	top: 50%;  
  	margin-left: -25px;  
  	margin-top: -25px;
  }
  /* 结合 calc 计算*/
  .center2{  
  	width: 50px;  
  	height: 50px;  
  	background-color: #7FFFD4;  
  	position: absolute;  
  	left: calc(50% - 25px)  
  	top: calc(50% - 25px);
  }
  /* 结合 transform */
  .center2{
  	width: 50px;
  	height: 50px;
  	background-color: #7FFFD4;
  	position: absolute;
  	left: 50%;
  	top: 50%;
  	transform: translate(-50%, -50%);
  }
  
  ```

  

- 三、使用弹性布局

  可以通过弹性布局来设置水平垂直居中，这里需要设置父级元素 display:flex; 还需要设置两个属性，
  水平布局 justify-content 以及垂直布局 align-items。

  ```html
  <div class="box2">  
  	<div class="center4"></div>
  </div>
  
  .box2{  
  	background-color: #eee;  
  	width: 200px;  
  	height: 200px;  
  	position: relative;  
  	margin-top: 20px ;  
  	display: flex;  
  	justify-content: center;  
  	align-items: center;
  }
  .center4{  
  	width: 50px;  
  	height: 50px;  
  	background-color: #B39873;
  }
  
  ```

  

- 四、文本水平对齐和行高（文字水平垂直居中）

  前面介绍的是元素如何实现水平垂直居中，下面介绍的是如何将文字进行水平垂直居中。
  这第一个方法也是最经常用的，使用文本水平对齐 text-align 和行高 line-height 来实现的。

  ```html
  <div class="box3">  
  	<div class="center5">文字居中</div>
  </div>
  
  .box3{  
  	background-color: #eee;  
  	width: 200px;  
  	height: 200px;  
  	margin-top: 20px;
  }
  .center5{  
  	text-align: center;  
  	line-height: 200px;
  }
  
  ```

- 五、使用网格布局（文字水平垂直居中）

  第二个方法可以通过网格布局 grid 来实现。而这里通过 grid 有两种方式实现，一种对元素本身属性进行设置，另一种在元素的父级元素中设置。两者看上去内容似乎差不多，不同的是在元素中设置的是 align-self 还要多了一个 margin，父级元素中是 align-items。

  ```html
  /* grid 元素中设置 */
  .box4{  
  	background-color: #eee;  
  	width: 200px;  
  	height: 200px;  
  	margin-top: 20px;  
  	display: grid;
  }
  .center6{  
  	align-self: center;  
  	justify-content: center;  
  	margin: auto;
  }
  /* grid 父级元素中设置 */
  .box5{  
  	background-color: #eee;  
  	width: 200px;  
  	height: 200px;  
  	margin-top: 20px;  
  	display: grid;  
  	align-items: center;  
  	justify-content: center;
  }
  
  ```

<hr>

### 4.对flex布局的理解以及应用场景

flex布局的盒子模型设置垂直居中就非常简单了，只需要设置 align-items:center; 属性。

采用 Flex 布局的元素，称为 Flex 容器（flex container），简称"容器"。容器默认存在两根轴：水平的主轴（main axis）和垂直的交叉轴（cross axis）。

**弹性元素永远沿主轴排列，那么如果主轴排不下，通过flex-wrap决定容器内项目是否可换行**

**默认是flex-wrap:no-wrap(不换行),当盒子放不下时也不会溢出,而是盒子伸缩**

flex-direction 属性决定主轴的方向（也就是排列方向），有4个属性值可以设置：

row（默认值）：主轴为水平方向，起点在左端。

row-reverse：主轴为水平方向，起点在右端。

column：主轴为垂直方向，起点在上沿。

column-reverse：主轴为垂直方向，起点在下沿。

**align-items 属性定义项目在交叉轴上如何对齐。**

(1)flex-start（默认值）：上对齐

(2)flex-end：下对齐

(3)center：居中

(4)stretch：子盒子无高度时，侧轴伸缩拉伸显示

**justify-content 属性定义了项目在主轴上的对齐方式。**

(1)flex-start（默认值）：左对齐

(2)flex-end：右对齐

(3)center：居中

(4)space-between：两端对齐，项目之间的间隔都相等

(5)space-around：两个项目两侧间隔相等



*问：flex:1;代表什么意思？*

**flex 属性是 flex-grow, flex-shrink 和 flex-basis 的简写，默认值为 0 1 auto。后两个属性可选。**

flex-grow 属性定义项目的放大比例，默认为0，即如果存在剩余空间，也不放大。如果所有项目的flex-grow属性都为1，则它们将等分剩余空间（如果有的话）。如果一个项目的flex-grow属性为2，其他项目都为1，则前者占据的剩余空间将比其他项多一倍。

flex-shrink 属性定义了项目的缩小比例，默认为1，即如果空间不足，该项目将缩小。如果所有项目的flex-shrink属性都为1，当空间不足时，都将等比例缩小。如果一个项目的flex-shrink属性为0，其他项目都为1，则空间不足时，前者不缩小。

flex-basis 属性定义了在分配多余空间之前，项目占据的主轴空间。浏览器根据这个属性，计算主轴是否有多余空间。它的默认值为auto，即项目的本来大小。

flex 属性属性有两个快捷值：auto (1 1 auto) 和 none (0 0 auto)。

建议优先使用这个属性，而不是单独写三个分离的属性，因为浏览器会推算相关值。

所以**flex: 1表示的含义是等分剩余空间。**

## 11.定位与浮动

### 1.为什么需要清除浮动？清除浮动的方式

**清除浮动主要是为了解决，父元素因为子级元素浮动引起的内部高度为0的问题**

总结一下：

当父元素不给高度的时候，

内部元素不浮动时会撑开

而浮动的时候，父元素变成一条线即红色那条线，如下图所示

![img](CSS.assets/20180729115542434.png)

法一、使用after伪元素

```html
    .clearfix:after{/*伪元素是行内元素 正常浏览器清除浮动方法*/
        content: "";
        display: block;
        height: 0;
        clear:both;
        visibility: hidden;
    }
    .clearfix{
        *zoom: 1;/*ie6清除浮动的方式 *号只有IE6-IE7执行，其他浏览器不执行*/
    }
 
<body>
    <div class="fahter clearfix">
        <div class="big">big</div>
        <div class="small">small</div>
        <!--<div class="clear">额外标签法</div>-->
    </div>
    <div class="footer"></div>
</body>
```

法二、4.使用before和after双伪元素清除浮动

```html
     .clearfix:after,.clearfix:before{
        content: "";
        display: table;
    }
    .clearfix:after{
        clear: both;
    }
    .clearfix{
        *zoom: 1;
    }
 
 <div class="fahter clearfix">
        <div class="big">big</div>
        <div class="small">small</div>
    </div>
    <div class="footer"></div>
```

法三、overflow:hidden 触发BFC 。

内容增多的时候容易造成不会自动换行导致内容被隐藏掉，无法显示要溢出的元素

不推荐使用

```html
    .fahter{
        width: 400px;
        border: 1px solid deeppink;
        overflow: hidden;
    }
```

### 2.position属性有哪些，区别是什么？

**1.position: absolute;**

绝对定位 ，绝对定位的元素的位置相对于最近的已定位父元素，如果元素没有已定位的父元素，那么它的位置相对于 `<html>` 

**2. position: fixed;**

固定定位 ，与绝对定位相似，但元素的包含块为 viewport 视口。该定位方式常用于创建在滚动屏幕时仍固定在相同位置的元素。在下面的示例中，"one" 元素定位在离页面顶部 80px，离页面左侧 20px 的位置。

```html
<div class="an">
    <div class="one">one</div>
    <div class="two">two</div>
</div>
<style>
.an {
    width: 500px;
    height: 300px;
    overflow: scroll;
    background: indianred;
}
 
.one {
    position: fixed;
    top: 50px;
    left: 50px;
    background: red;
    width: 100px;
    height: 100px;
    color: white;
}
 
.two {
    background: yellow;
    height: 500px;
}</style>
```

![img](CSS.assets/b876175ada9a1f760def3fe45b7310d4.png)

**3.position: relative;**

相对定位 ，相对于其正常位置进行定位，不影响其他元素的偏移。

**4.position: sticky;**
粘性定位 ，可以被认为是相对定位和固定定位的混合。元素在跨越特定阈值前为相对定位，之后为固定定位

这是一个结合了 position:relative 和 position:fixed 两种定位功能于一体的特殊定位。常见的吸顶、吸底（头部返回栏，底部切换栏等）的效果都是使用这个属性：

**注意：**

- 须指定 `top` 、 `right` 、 `bottom` 、 `left` 四个阈值其中之一，才可使粘性定位生效。否则其行为与相对定位相同。 并且 `top` 和 `bottom` 同时设置时，`top` 生效的优先级高，`left` 和 `right` 同时设置时，`left` 的优先级高。
- 设定为 `position:sticky` 元素的任意父节点的 `overflow` 属性必须是 `visible`，否则 `position:sticky` 不会生效。如果 `position:sticky` 元素的任意父节点定位设置为 `overflow:hidden`，则父容器无法进行滚动，所以 `position:sticky` 元素也不会有滚动然后固定的情况。如果 `position:sticky` 元素的任意父节点定位设置为 `position:relative | absolute | fixed`，则元素相对父元素进行定位，而不会相对 `viewport` 定位。
- 达到设定的阀值，也就是设定了 `position:sticky` 的元素表现为 `relative` 还是 `fixed`是根据元素是否达到设定了的阈值决定的。

**5.position: static;**
静态定位 ，HTML 元素默认情况下的定位方式为 static（静态），静态定位的元素不受 top、bottom、left 和 right 属性的影响，它始终根据页面的正常流进行定位

**6.position: inherit;**
inherit 值如同其他 css 属性的 inherit 值，即继承父元素的 position 值。

## 12.实际应用题

### 1.实现一个三角形

把盒子宽高去掉，边框细节变成下图所示，然后设置边框透明度。

![img](CSS.assets/60a7bbb68e9a4411a57fce4ac538c692.png)

```html
<!DOCTYPE html>
<html lang="ch">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>CSDN测试专用</title>
    <style>
    .div{width:0px;
        height:0px;
        border:10px solid transparent;/*以下四个样式对应四种三角形，任选其一即可实现*/
        /* border-top-color:lightseagreen; */
        /* border-left-color:lightseagreen; */
        /* border-right-color:lightseagreen; */
        border-bottom-color:lightseagreen;
    }
    </style>
</head>
<body>
   <div class="div"></div>
</body>
</html>
```



### 2.实现一个扇形

任意角度：一个圆，加两个绝对定位的半圆做角度拼接。

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Document</title>
  </head>
  <body>
    <style>
      .contain {
        position: relative;
        width: 200px;
        height: 200px;
      }
      .main {
        height: 100%;
        background: lightgreen;
        border-radius: 100px;
      }
      .common {
        position: absolute;
        top: 0;
        width: 50%;
        height: 100%;
      }
      .mask1 {
        transform: rotate(83deg);
        border-radius: 100px 0 0 100px;
        left: 0;
        transform-origin: right center;
        background: red;
      }
      .mask2 {
        transform: rotate(-76deg);
        transform-origin: left center;
        left: 100px;
        border-radius: 0 100px 100px 0;
        background: blue;
      }
    </style>

    <div class="contain">
      <div class="main"></div>
      <div class="mask1 common"></div>
      <div class="mask2 common"></div>
    </div>
  </body>
</html>

```



### 3.宽高自适应的正方形

**（1）设置垂直方向的padding**

在 CSS 中，[margin](https://so.csdn.net/so/search?q=margin&spm=1001.2101.3001.7020) 和 padding 的百分比是相对于父元素的宽度来计算的，利用这个特性，将 padding-top 或者 padding-bottom 设置为与 width 相同的百分比，再将 height 设为 0，最后通过定位可以实现自适应的正方形。

设置垂直方向的padding撑开容器(padding可以用百分比，百分比是根据它包含块的width来确定的，也就是父级元素的width）

```html
<body>
    <div class="card-box">
        <div class="card"></div>
    </div>
</body>
 
<style>
.card-box {
    width: 25%;
    height: 0;
    padding-bottom: 25%;
    position: relative;
}

.card {
    position: absolute;
    top: 0;
    right: 0;
    bottom: 0;
    left: 0;
    background-color: skyblue;
}</style>

```



**（2）使用vw**   推荐使用

​    //CSS3中新增了一组相对于可视区域百分比的长度单位vw、vh、vmin、vmax。vw 是相对于浏览器内部的可视区域（viewport）宽度的单位，1vw = 1% viewport width; 1vh = 1% viewport height。假设浏览器内部宽度为 1000px，那么 1vw = 10px。

```css
 .card-box {
    width: 25%;
    height: 25vw;
}
 
.card {
    width: 100%;
    height: 100%;
    background-color: skyblue;
}
```
------------------------------------------------

### 4.画一条0.5px的线

方法1：采用 meta viewport 的方式

仅适用于移动端

```html
<meta name="viewport" content="initial-scale=1.0, maximum-scale=1.0, user-scalable=no" />

```

方法2：采用 transform: scale() 的方式

使用[scale](https://so.csdn.net/so/search?q=scale&spm=1001.2101.3001.7020)缩放transform：scaleY（0.5）加上transform-origin：50% 100%；

```html
<body>
    <div class="hr scale-half"></div>
    <style>
      .hr.scale-half {
        height: 1px;
        transform: scaleY(0.5);
        transform-origin: 50% 100%;
        background-color: black;
      }
    </style>
  </body>
```



### 5.设置小于12px的字体

```html
<div>
    文本
</div>
```



1.文本嵌套块标签，这是因为缩放只对有宽高的标签有效，缩放的时候也是将标签一起缩放，而不仅仅是缩放文本，所以如果使用span等行内标签时，还需要将行内标签进行元素转换为块元素（display:block;）
font-size：12px；
2.给文本设置字体12px，并设置缩放值为10/12=0.83333，也就是transform:scale(0.83)；如果要设置8px，那就是8/12=0.66666
3.transform-origin：0 0；
默认缩放中心点是在盒子的正中心，所以如果我们需要文本左对齐，就需要改变中心点，也就是transform-origin：0 0；该值有两个参数值，第一个是水平方位值，第二个是垂直方位值，对应的如果需要右对齐、或者是有缩进，那就改变对应的参数值即可。
4.white-space: nowrap;
文本进行缩放后，并不会改变其原来盒子的大小，只是视觉上改变了大小，也就是说如果文本有换行的时候，它进行缩放后仍然是折行显示，这显然不符合我们要求，所以我们还需要强制文本在一行显示，也就是 white-space: nowrap;



```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style>
        div {
            width: 300px;
            height: 30px;
            margin-bottom: 5px;
            background: rgb(206, 151, 151);
        }
        .box1 {
            font-size: 12px;
        }
        .box2 {
            font-size: 10px;
            transform: scale(0.83333);
            transform-origin: 0 0;
            white-space: nowrap;
        }
    </style>
</head>
<body>
    <div class="box1">我是正常的12px的文字大小 Hello world!</div>
    <div class="box1">我是正常的12px的文字大小 Hello world!</div>
    <div class="box2">我是正常的10px的文字大小 Hello world!</div>
    <div class="box2">我是正常的10px的文字大小 Hello world!</div>
</body>
</html>

```



### 6.如何解决小于1px的问题

1、伪类+transform

把原先元素的`border`去掉，然后利用`:before`或者`:after`重做`border`，并 `transform`的`scale`缩小一半，原先的元素相对定位，新做的`border`绝对定位。

```css
/*底边边框一像素*/
.border-bottom-1px::after {
    content: "";
    position: absolute;
    left: 0;
    bottom: 0;
    width: 100%;
    height: 1px;
    transform-origin: 0 0;
}
 
/*上边边框一像素*/
.border-top-1px::after {
    content: "";
    position: absolute;
    left: 0;
    top: 0;
    width: 100%;
    height: 1px;
    transform-origin: 0 0;
}
 
/*左边边框一像素*/
.border-left-1px::after {
    content: "";
    position: absolute;
    left: 0;
    top: 0;
    width: 1px;
    height: 100%;
    transform-origin: 0 0;
}
 
/*右边边框1像素*/
.border-right-1px::after {
    content: "";
    box-sizing: border-box;
    position: absolute;
    right: 0;
    top: 0;
    width: 1px;
    height: 100%;
    transform-origin: 0 0;
}
 
/*边框一像素*/
.border-1px::after {
    content: "";
    box-sizing: border-box;
    position: absolute;
    left: 0;
    top: 0;
    width: 100%;
    height: 100%;
    border: 1px solid gray;
}


```

# 二、二级题目

## 1.css中可继承与不可继承属性

**一、无继承性的属性**
display：规定元素应该生成的框的类型
*文本属性：*
vertical-align：垂直文本对齐
text-decoration：规定添加到文本的装饰
text-shadow：文本阴影效果
white-space：空白符的处理
unicode-bidi：设置文本的方向
*盒子模型的属性*：width、height、margin、border、padding
*背景属性：*background、background-color、background-image、background-repeat、background-position、background-attachment
*定位属性*：float、clear、position、top、right、bottom、left、min-width、min-height、max-width、max-height、overflow、clip、z-index
生成内容属性：content、counter-reset、counter-increment
轮廓样式属性：outline-style、outline-width、outline-color、outline
页面样式属性：size、page-break-before、page-break-after
声音样式属性：pause-before、pause-after、pause、cue-before、cue-after、cue、play-during
**二、有继承性的属性**
*1.字体系列属性*
font-family：字体系列
font-weight：字体的粗细
font-size：字体的大小
font-style：字体的风格
*2.文本系列属性*
text-indent：文本缩进
text-align：文本水平对齐
line-height：行高
word-spacing：单词之间的间距
letter-spacing：中文或者字母之间的间距
text-transform：控制文本大小写（就是uppercase、lowercase、capitalize这三个）
color：文本颜色
*3.元素可见性*

visibility：控制元素显示隐藏
*列表布局属性*
list-style：列表风格，包括list-style-type、list-style-image等
*4.光标属性*

cursor：光标显示为何种形态

## 2.link和@import区别

1.link不仅可以导入样式表，还可以导入其他如如favicon，但@import只能导入样式表
2.link是XHTML语法，不存在兼容问题，但是@import是在css2.1才提出，在IE5+后才支持，所以对低版本的浏览器不兼容
3.可以通过 JS 操作 DOM ，插入link标签来改变样式；由于 DOM 方法是基于文档的，无法使用@import的方式插入样式。
4.link是在页面加载的的同时一起加载的，@import是页面加载完毕后才加载的
5.link引入的样式权重大于@import引入的样式（有争议）



## 3.伪元素和伪类的区别和作用

其中伪类和[伪元素](https://so.csdn.net/so/search?q=%E4%BC%AA%E5%85%83%E7%B4%A0&spm=1001.2101.3001.7020)的根本区别在于：它们是否创造了新的元素。

伪元素/伪对象：不存在在DOM文档中，是虚拟的元素，是创建新元素。代表某个元素的子元素，这个子元素虽然在逻辑上存在，但却并不实际存在于文档树中。

伪元素选择符
![](CSS.assets/伪元素.png)
伪类：存在DOM文档中，逻辑上存在但在文档树中却无须标识的“幽灵”分类。

伪类选择符
![](CSS.assets/伪类.png)

## 4.line-height的理解

**line-height，又称行高，指的是两行文字基线之间的距离，又可以称为这行文字所占的高度。**

如下图所示红色为基线

**内联元素的高度是由行高决定的！**

我们需要知道：

1、行高由于其继承性，影响无处不在，即使单行文本也不例外。

2、行高只是幕后黑手，高度的表现不是行高，而是内容区域和行间距。

只不过，内容区域高度(content area)+行间距(vertical spacing)=行高(line-height)

注意：
1、内容区域高度只与字号以及字体有关，与line-height没有任何关系。

2、在simsun字体(即宋体)下，内容区域高度等于文字大小值。



![img](CSS.assets/0a6e4b21cbaa42d8b0bd47c2d5e2808a.png)

## 5.对媒体查询的理解

1. 什么是媒体查询
  媒体查询（Media Query）是CSS3新语法。

使用@media查询，可以针对不同的媒体类型定义不同的样式
@media可以针对不同的屏幕尺寸设置不同的样式
当你重置浏览器大小的过程中，页面也会根据浏览器的宽度和高度重新渲染页面
目前针对很多苹果手机、Android手机，平板等设备都用得到媒体查询
2. 语法规范
  @media mediatype and|not|only (media feature){
      css-code;
  }

  用@media开通 注意@符号
  mediatype 媒体类型
  关键字 and not only
  media feature 媒体特性，必须有小括号包含
  2.1 mediatype查询类型
  将不同的终端设备划分为不同的类型，称为媒体类型

![](CSS.assets/查询类型.png)

2.2 关键字
关键字将媒体类型或多个特性连接到一起做为媒体查询的条件

and：可以将多个媒体特性连接到一起，相当"且"于的意思
not：排除某个媒体类型，相当于"非"的意思，可以省略
only：指定某个特定的媒体类型，可省略

2.3 媒体特性
每种媒体类型都具备各自不同的特性，根据不同媒体类型特性设置不同的展示风格，简单先了解三个

注意：他们要加小括号包含

![](CSS.assets/媒体特性.png)

```css
@media screen  (max-width:800px){
body{
background-color:pink;
}
}
```



------------------------------------------------


## 6.常见css布局单位

常见的CSS布局单位
**1.px**
px是屏幕能显示的最小区域。
**2.em和rem**
em和rem都是相对长度单位。em是相对于父元素，rem相对于root。
em：文本相对长度单位，相对父元素字体大小的倍数。相对于当前对象内文本的字体尺寸。如果当前行内文本的字体尺寸未被设置，则相对于浏览器默认字体尺寸（16px）进行设置。
rem：相对于根元素的字体大小的倍数。使用rem可以实现响应式布局，当屏幕分辨率发生变化时，元素也随之变化。
%
通过%可以实现响应式效果。一般认为子元素的百分比相对于父元素。
**3.vw和vh**
vw表示相对于视图窗口的宽度，vh表示相对于视图窗口的高度，除了vw和vh之外，还有vmin和vmax两个相关的单位。vmin代表vw和vh之中的较小值，vmax代表较大值。使用vw和vh也可以实现响应式。
px、em、rem的区别及使用场景
**区别**
px是固定的像素，一旦设置了就无法因为适应页面大小而改变。
em和rem相对于px有更高的灵活性，他们是相对长度单位，其长度不固定，更适用响应式布局。
em相对父元素设置字体大小，这就有个问题：进行任何元素设置，都需要知道它父元素的大小，而rem只需要知道根元素的大小。

## 7.px em rem 的使用场景

使用场景：
对于只需要适配少数移动设备，且分辨率对页面影响不大的，使用px即可。
对于需要适配各种移动设备，就用rem。

## 8.margin重叠问题，如何解决

margin重叠
margin重叠 也叫外间距重叠 或者是外间距合并,也或者叫做外间距穿透
外间距合并指的是:当两个垂直外间距相遇时,它们会合并成一个外间距
合并后的外间距高度等于两个发生合并的外间距的高度中的较大者。

发生的情况有以下几种:
1.兄弟元素之间
2.父子元素之间
3.空元素上下外间距之间
4.空元素上下外间距和其他元素之间。
不论出现上述哪种情况，重叠后取得都是较大值
消除外间距重叠的方法:
1.添加透明边框
2.外层设置padding
3.外层设置overflow:hidden
4.外层 zoom:1;(ie下清楚margin的重叠 了解)
一下方案也可以
5.绝对定位: 内层float display:inline;(元素会被认为是内联元素而显示)



## 9.display、float、position的关系

**1、display的值及作用**
block 转换成块状元素。
inline 转换成行内元素。
none 设置元素不可见（该种方法的不可见是使得整个dom元素从文档流中去掉，而不只是单纯的样式上的隐藏）。
inline-block 具备了行内元素不换行的特征，同时也有块元素可以设置宽高的特征
list-item 象块类型元素一样显示，并添加样式列表标记。
table 此元素会作为块级表格来显示
inherit 规定应该从父元素继承 display 属性的值
在CSS布局中，如果我们想要将一些元素在同一行显示，其中的一种方法就是把要同行显示的元素设置display属性为inline-block，但是你会发现这些同行显示的inline-block元素之间经常会出现一定的空隙，这就是【换行符/空格间隙问题】。

display:inline-block 什么时候不会显示间隙？

移除空格
使用margin负值
使用font-size:0
letter-spacing
word-spacing
**2、定位position的值及作用**
static 默认值。没有定位，元素出现在正常的流中。
absolute：生成绝对定位的元素，相对于定位值是static以外的第一个父辈元素进行定位
fixed：生成绝对定位的元素，相对于浏览器窗口进行定位
relative：生成相对定位的元素，相对于其正常位置进行定位
inherit 规定从父元素继承 position 属性的值
relative相对于自身定位，可以设置位置偏移，但是自身原本在正常文档流中的位置还保留，所以**relative是不脱离文档流的**。

定位值为absolute、fixed的时候，原本自身在正常文档流中的位置不保留，代码中后面的元素会顶上，absolute、fixed定位是脱离正常文档流的。

**3、浮动**
浮动的元素也会使其脱离正常文档流。浮动的框可以向左float: left或向右float: right移动，直到他的外边缘碰到包含框或另一个浮动框的边框为止。由于浮动框不在文档的普通流中，所以文档的普通流的块框表现得就像浮动框不存在一样。浮动的块框会漂浮在文档普通流的块框上。

行内元素float:left后是否变为块级元素？

行内元素设置成浮动之后变得更加像是inline-block（行内块级元素，设置成这个属性的元素会同时拥有行内和块级的特性，最明显的不同是它的默认宽度不是100%），这时候给行内元素设置padding-top和padding-bottom或者width、height都是有效果的

**4、display、float、position的关系**
如果display取值为none，那么position和float都不起作用，这种情况下元素的display不受影响。

如果position取值为absolute或者fixed，框就是绝对定位的，float属性不生效，display根据下面的表格进行调整。

设置值	                                                              计算值
inline-table	                                                        table
inline、inline-block、table-cell、	
table-row、table-column、table-caption、	
table-row-group、table-column-group、	
table-header-group、table-footer-group	            block
其他值	                                                               与设置值一样
如果position不为absolute或者fixed，若float的值不为none，那么display转化的规则和上面一条一样。另外，**如果position的值为relative并且float属性的值存在，则relative相对于浮动后的最终位置定位（先浮动生效再relative定位生效）。**

如果没有定位且float为none，则看是否为根元素。如果元素是根元素，display根据上面表格规则进行调整

其他情况下display的值为指定值

总结起来：

绝对定位、浮动、根元素都需要调整display
可以把它看作是一个类似优先级的机制，**"position:absolute"和"position:fixed"优先级最高，有它存在的时候，浮动不起作用，'display’的值也需要调整；**
元素的’float’特性的值不是"none"的时候或者它是根元素 的时候，调整’display’的值；
最后，非根元素，并且非浮动元素，并且非绝对定位的元素，'display’特性值同设置值。

------------------------------------------------
