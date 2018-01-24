---
title: CSS_Study
date: 2016-08-16 20:47:38
tags: [HTML,CSS]
---
# 1.  导入外部css样式
`<link href="base.css" rel="stylesheet" type="text/css" />`
```
其中rel="stylesheet" type="text/css"是固定写法不可改变
 内联式 > 嵌入式>外部式
 就近原则（离被设置元素越近优先级别越高）。
 ```
 <!-- more -->
# 2.类选择器
## 语法：
**.**类选器名称{css样式代码;}
## 注意
1. 英文圆点开头
2. .类选器名称{css样式代码;}

## 使用方法：
# 1. 使用合适的标签把要修饰的内容标记起来
2.  class="类选择器名称"为标签设置一个类
3.  设置类选器css样式，如下：
>  .stress{color:red;}/*类前面要加入一个英文圆点*/
# 3.ID选择器
在很多方面，ID选择器都类似于类选择符，但也有一些重要的区别：

1、为标签设置id="ID名称"，而不是class="类名称"。

2、ID选择符的前面是井号（#）号，而不是英文圆点（.）。
# 4.类和ID选择器的区别
1. 相同点：可以应用于任何元素
2. 不同点：

- **ID选择器只能在文档中使用一次。**与类选择器不同，在一个HTML文档中，ID选择器只能使用一次，而且仅一次。而类选择器可以使用多次。(一个ID 只能在同一个HTML中使用一次，class 可以重复使用)
- 一个元素只能有一个ID  但是可以有多个class
# 5.子选择器
还有一个比较有用的选择器子选择器，即大于符号(>),用于选择指定标签元素的第一代子元素。如右侧代码编辑器中的代码：
 ```
.food>li{border:1px solid red;}
```
# 6.包含(后代)选择器
包含选择器，即加入==空格==,用于选择指定标签元素下的后辈元素。如下面代码：

```
.first  span{color:red;}
```


```
.food>li
```
是控制class food下第一代li标签

而
```
.food li
```
是控制class下所有的li标签
# 7.通用选择器
通用选择器是功能最强大的选择器，它使用一个（*）号指定，它的作用是匹配html中所有标签元素，如下使用下面代码使用html中任意标签元素字体颜色全部设置为红色：

```
* {color:red;}
```
# 8.伪类选择符
伪类选择符,它允许给html不存在的标签（标签的某种状态）设置样式，比如说我们给html中一个标签元素的鼠标滑过的状态来设置字体颜色：

```
a:hover{color:red;}
```
hover   ---->  鼠标滑过
# 9.字体设置
- ## 文字排版--粗体
```
p span{font-weight:bold;}
```
- ## 文字排版--斜体
```
p a{font-style:italic;}
```
- ##  文字排版--下划线

```
p a{text-decoration:underline;}
```

参数 | 描述
---|---
none | 默认。定义标准的文本。
underline | 定义文本下的一条线。
overline | 定义文本上的一条线。
line-through |定义穿过文本下的一条线。
blink | 定义闪烁的文本。
inherit | 规定应该从父元素继承 text-decoration 属性的值。
# 10.段落排版
- ## 缩进

```
p{text-indent:2em;}
```
- ## 行间距（行高）

```
p{line-height:1.5em;}
```
- ## 中文字间距、字母间距
如果想在网页排版中设置文字间隔或者字母间隔就可以使用    letter-spacing 来实现，如下面代码：
```
h1{
    letter-spacing:50px;
}
...
<h1>了不起的盖茨比</h1>
```
注意：这个样式使用在英文单词时，是设置字母与字母之间的间距。
单词间距设置：

如果我想设置英文单词之间的间距呢？可以使用 word-spacing 来实现。如下代码：

```
h1{
    word-spacing:50px;
}
...
<h1>welcome to imooc!</h1>
```
- ## 对齐

```
text-align:center;//right    left
```
# 11.元素分类--内联元素--块状元素

```
div{
     display:inline;//将块状元素转换为内联元素
 }
```
```
a{
     display:block;//将内联元素转换为块状元素
 }
```
## 内联元素特点：

- 和其他元素都在一行上；

- 元素的高度、宽度及顶部和底部边距不可设置；

- 元素的宽度就是它包含的文字或图片的宽度，不可改变。

## 块级元素特点：

- 每个块级元素都从新的一行开始，并且其后的元素也另起一行。（一个块级元素独占一行）

- 元素的高度、宽度、行高以及顶和底边距都可设置。

- 元素宽度在不设置的情况下，是它本身父容器的100%（和父元素的宽度一致），除非设定一个宽度。
## 内联块状元素
内联块状元素（inline-block）就是同时具备内联元素、块状元素的特点，代码display:inline-block就是将元素设置为内联块状元素。(css2.1新增)，<img>、<input>标签就是这种内联块状标签。

inline-block 元素特点：

1、和其他元素都在一行上；

2、元素的高度、宽度、行高以及顶和底边距都可设置。

提示：下一小节是用视频动画来讲解css中的盒模型。
## border
dashed（虚线）| dotted（点线）| solid（实线）。

```
div{
    border:2px  solid  red;
}
```
## 可以只设置底边框

```
div{border-bottom:1px solid red;}
```

## 也可以实现其它三边(上、右、左)边框的设置：

```
border-top:1px solid red;
border-right:1px solid red; 
border-left:1px solid red;
```
# 12.层模型
- ## 绝对定位
- 如果想为元素设置层模型中的绝对定位，需要设置position:absolute(表示绝对定位)，这条语句的作用将元素从文档流中拖出来，然后使用left、right、top、bottom属性相对于其最接近的一个具有定位属性的父包含块进行绝对定位。如果不存在这样的包含块，则相对于body元素，即相对于浏览器窗口。
 
  如下面代码可以实现div元素相对于浏览器窗口向右移动100px，向下移动50px。

```
div{
    width:200px;
    height:200px;
    border:2px red solid;
    position:absolute;
    left:100px;
    top:50px;
}
```
- ## 相对定位
如果想为元素设置层模型中的相对定位，需要设置position:relative（表示相对定位），它通过left、right、top、bottom属性确定元素在正常文档流中的偏移位置。相对定位完成的过程是首先按static(float)方式生成一个元素(并且元素像层一样浮动了起来)，然后相对于以前的位置移动，移动的方向和幅度由left、right、top、bottom属性确定，偏移前的位置保留不动。

如下代码实现相对于以前位置向下移动50px，向右移动100px;

```
#div1{
    width:200px;
    height:200px;
    border:2px red solid;
    position:relative;
    left:100px;
    top:50px;
}

```
- ## 固定定位
fixed：表示固定定位，与absolute定位类型类似，但它的相对移动的坐标是视图（屏幕内的网页窗口）本身。由于视图本身是固定的，它不会随浏览器窗口的滚动条滚动而变化，除非你在屏幕中移动浏览器窗口的屏幕位置，或改变浏览器窗口的显示大小，因此固定定位的元素会始终位于浏览器窗口内视图的某个位置，不会受文档流动影响，这与background-attachment:fixed;属性功能相同。

以下代码可以实现相对于浏览器视图向右移动100px，向下移动50px。并且拖动滚动条时位置固定不变。

```
#div1{
    width:200px;
    height:200px;
    border:2px red solid;
    position:fixed;
    left:100px;
    top:50px;
}
```
- ## 缩写

```
注意：

1、使用这一简写方式你至少要指定 font-size 和 font-family 属性，其他的属性(如 font-weight、font-style、font-varient、line-height)如未指定将自动使用默认值。

2、在缩写时 font-size 与 line-height 中间要加入“/”斜扛。
```


一般情况下因为对于中文网站，英文还是比较少的，所以下面缩写代码比较常用：

```
body{
    font:12px/1.5em  "宋体",sans-serif;
}
```
# 13.长度值
## 1、像素

像素为什么是相对单位呢？因为像素指的是显示器上的小点（CSS规范中假设“90像素=1英寸”）。实际情况是浏览器会使用显示器的实际像素值有关，在目前大多数的设计者都倾向于使用像素（px）作为单位。

## 2、em

就是本元素给定字体的 font-size 值，如果元素的 font-size 为 14px ，那么 1em = 14px；如果 font-size 为 18px，那么 1em = 18px。如下代码：

```
p{font-size:12px;text-indent:2em;}
```


上面代码就是可以实现段落首行缩进 24px（也就是两个字体大小的距离）。

### 下面注意一个特殊情况：

但当给 font-size 设置单位为 em 时，此时计算的标准以 p 的父元素的 font-size 为基础。如下代码：

```
html:

<p>以这个<span>例子</span>为例。</p>
css:

p{font-size:14px}
span{font-size:0.8em;}
```


结果 span 中的字体“例子”字体大小就为 11.2px（14 * 0.8 = 11.2px）。

## 3、百分比

```
p{font-size:12px;line-height:130%}
```


设置行高（行间距）为字体的130%（12 * 1.3 = 15.6px）。
# 14.水平居中设置-定宽块状元素
当被设置元素为 块状元素 时用 text-align：center 就不起作用了，这时也分两种情况：定宽块状元素和不定宽块状元素。

这一小节我们先来讲一讲定宽块状元素。(定宽块状元素：块状元素的宽度width为固定值。)

满足定宽和块状两个条件的元素是可以通过设置“左右margin”值为“auto”来实现居中的。我们来看个例子就是设置 div 这个块状元素水平居中：

```
html代码：

<body>
  <div>我是定宽块状元素，哈哈，我要水平居中显示。</div>
</body>
css代码：

<style>
div{
    border:1px solid red;/*为了显示居中效果明显为 div 设置了边框*/
    
    width:200px;/*定宽*/
    margin:20px auto;/* margin-left 与 margin-right 设置为 auto */
}

</style>
```
注意：元素的“上下 margin” 是可以随意设置的。
- ## 水平居中总结-不定宽块状元素方法（一）

利用table标签的长度自适应性---即不定义其长度也不默认父元素body的长度（table其长度根据其内文本长度决定），因此可以看做一个定宽度块元素，然后再利用定宽度块状居中的margin的方法，使其水平居中。

第一步：为需要设置的居中的元素外面加入一个 table 标签 ( 包括 <tbody>、<tr>、<td> )。

第二步：为这个 table 设置“左右 margin 居中”（这个和定宽块状元素的方法一样）。

举例如下：

```
html代码：

<div>
 <table>
  <tbody>
    <tr><td>
    <ul>
        <li>我是第一行文本</li>
        <li>我是第二行文本</li>
        <li>我是第三行文本</li>
    </ul>
    </td></tr>
  </tbody>
 </table>
</div>
css代码：

<style>
table{
    border:1px solid;
    margin:0 auto;
}
</style>
```
## 第二种方法：改变块级元素的 display 为 inline 类型
（设置为 行内元素 显示），然后使用 text-align:center 来实现居中效果。如下例子：

```
html代码：

<body>
<div class="container">
    <ul>
        <li><a href="#">1</a></li>
        <li><a href="#">2</a></li>
        <li><a href="#">3</a></li>
    </ul>
</div>
</body>
css代码：

<style>
.container{
    text-align:center;
}
/* margin:0;padding:0（消除文本与div边框之间的间隙）*/
.container ul{
    list-style:none;
    margin:0;
    padding:0;
    display:inline;
}
/* margin-right:8px（设置li文本之间的间隔）*/
.container li{
    margin-right:8px;
    display:inline;
}
</style>
```
## 方法三：
通过给父元素设置 float，然后给父元素设置 position:relative 和 left:50%，子元素设置 position:relative 和 left: -50% 来实现水平居中。
- 代码如下：
- 
```
<body>
<div class="wrap">
    <div class="wrap-center">我们来学习一下这种方法。</div>
</div>
</body>
css代码：
<stlye>
.wrap{
    float:left;
    position:relative;
	left:50%;

}
.wrap-center{
    background:#ccc;
    position:relative;
	left:-50%;

}
</stlye>
```
- ## 垂直居中-父元素高度确定的单行文本
- 父元素高度确定的单行文本的竖直居中的方法是通过设置父元素的 height 和 line-height 高度一致来实现的。(height: 该元素的高度，line-height: 顾名思义，行高（行间距），指在文本中，行与行之间的 基线间的距离 )。

- line-height 与 font-size 的计算值之差，在 CSS 中成为“行间距”。分为两半，分别加到一个文本行内容的顶部和底部。

- 这种文字行高与块高一致带来了一个弊端：当文字内容的长度大于块的宽时，就有内容脱离了块。
- 如下代码：
```


<div class="container">
    hi,imooc!
</div>
css代码：

<style>
.container{
    height:100px;
    line-height:100px;
    background:#999;
}
</style>
```
- ## 垂直居中-父元素高度确定的多行文本（方法一）
父元素高度确定的多行文本、图片等的竖直居中的方法有两种：

方法一：使用插入 table  (包括tbody、tr、td)标签，同时设置 vertical-align：middle。

css 中有一个用于竖直居中的属性 vertical-align，在父元素设置此样式时，会对inline-block类型的子元素都有用。下面看一下例子：

```
html代码：

<body>
<table><tbody><tr><td class="wrap">
<div>
    <p>看我是否可以居中。</p>
</div>
</td></tr></tbody></table>
</body>
css代码：

table td{height:500px;background:#ccc}
//因为 td 标签默认情况下就默认设置了 vertical-align 为 middle，所以我们不需要显式地设置了。
```
