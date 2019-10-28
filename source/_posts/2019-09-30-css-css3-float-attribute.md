---
title: "css/css3 中的float详解"
categories: note
date: 2019-09-30 16:45:17
tags:
  - css/css3
  - 大前端
---
# 前言
CSS中的float是个常用的属性，如果没有很好的理解，常常会懵逼，至少我自己以前常常懵逼。  
所以根据自己的理解，踩着前人的脚步，总结记录一下，方便查阅。

# 这是个啥玩意（float）
float，可以理解为浮动，设置了float的元素会根据属性进行各种“飘移”，对于这类元素常常被称为浮动元素。

先看一个常用的例子：
```html
<div class="box">
  <span class="float-ele">
    浮动元素        
  </span>        
  普通文档流普通文档流普通文档流普通文档流普通文档流普通文档流普通文档流普通文档流普通文档流普通文档流普通文档流普通文档流普通文档流普通文档流普通文档流
</div>
```
```css
.box { background: #00ff90; padding: 10px; width: 500px; }
.float-ele { float: left; margin: 10px; padding: 10px; background: #ff6a00; width: 100px; text-align: center; }
```
效果图：  
![1.png](https://i.loli.net/2019/09/30/EjR95H3NKmXMnLB.png)

# 开始正经的说float，一些常用规则
首先我们先看一个概念：  
**包含块**：就是离浮动元素最近的块级祖先元素，前面叙述的例子中，div.box就是span元素的包含块。

那么，这里有个float的特性：  
> 不管一个元素是行内元素还是块级元素，如果被设置了浮动，那浮动元素会生成一个块级框，可以设置它的width和height。  

因此,float常常用于制作横向配列的菜单，可以设置大小并且横向排列。

开始说细则，浮动元素的展示在不同情况下会有不同的规则:

## 浮动元素在浮动的时候，其margin不会超过包含块的padding
浮动元素的浮动位置不能超过包含块的内边界
```html
<div class="box">        
  <span class="rule1">            
    浮动元素        
  </span>    
</div>
```
```css
.box { background: #00ff90; padding: 10px; width: 500px; height: 400px; }        
.rule1 { float: left; margin: 10px; padding: 10px; background: #ff6a00; width: 100px; text-align: center; }
```
效果图：  
![2.png](https://i.loli.net/2019/09/30/jqonzdbKUSM3yL2.png)

这个例子中，box的padding是10px，浮动元素的margin是10px，合起来为20px，即浮动元素不会超过包含块的padding。  
> PS: 如果想要元素超出，可以设置margin属性

## 如果有多个浮动元素，后面的浮动元素的margin不会超过前面浮动元素的margin
简单说就是如果有多个浮动元素，浮动元素会按顺序排下来而不会发生重叠的现象。

```html
<div class="box">        
  <span class="rule1">            
    浮动元素1        
  </span>        
  <span class="rule1">            
    浮动元素2        
  </span>        
  <span class="rule1">            
    浮动元素3        
  </span>    
</div>
<!-- css还是和上面的一样 -->
```
效果图：  
![3.png](https://i.loli.net/2019/09/30/l6aRyq4tmQ1xXEF.png)

浮动元素会一个一个排序下来而不会发生重叠现象。

## 如果两个元素一个向左浮动，一个向右浮动，左浮动元素的marginRight不会和右浮动元素的marginLeft相邻。
这里分为两种情况：

- 包含块的宽度大于两个浮动元素的宽度总和，举例如下：
```html
<div class="box">        
  <span class="rule1">            
    浮动元素1        
  </span>        
  <span class="rule2">           
    浮动元素2        
  </span>    
</div>
```
```css
.box { background: #00ff90; padding: 10px; width: 500px; height: 400px; }
.rule1 { float: left; margin: 10px; padding: 10px; background: #ff6a00; width: 100px; text-align: center; }
.rule2 { float: right; margin: 10px; padding: 10px; background: #ff6a00; width: 100px; text-align: center; }
```
效果图：  
![4.png](https://i.loli.net/2019/09/30/pzBwL6X8CH4r2JK.png)

包含块元素的宽度足够大，两个元素一个向左浮动，一个向右浮动，井水不犯河水。

- 包含块的宽度小于两个浮动元素的宽度总和

修改上述代码的浮动元素的宽度为300px，如下图：  
![5.png](https://i.loli.net/2019/09/30/jHwh5SkX4Vo93dK.png)

如果包含块宽度不够高，后面的浮动元素将会向下浮动，其顶端是前面浮动元素的底端。

## 浮动元素顶端不会超过包含块的内边界底端，如果有多个浮动元素，下一个浮动元素的顶端不会超过上一个浮动元素的底端
如果有多个浮动元素，后面的元素高度不会超过前面的元素，并且不会超过包含块。
```html
<div class="box">        
  <p>在浮动元素之前在浮动元素之前，在浮动元素之前，在浮动元素之前，在浮动元素之前，在浮动元素之前，在浮动元素之前，在浮动元素之前，</p>        
  <p class="rule1">            
    浮动元素1浮动元素1浮动元素1浮动元素1浮动元素1浮动元素1浮动元素1浮动元素1浮动元素1浮动元素1浮动元素1浮动元素1        
  </p>        
  <p>在浮动元素之后在浮动元素之后在浮动元素之后在浮动元素之后在浮动元素之后在浮动元素之后在浮动元素之后在浮动元素之后</p>        
  <p class="rule1">            
    浮动元素2浮动元素2浮动元素2浮动元素2浮动元素2浮动元素2浮动元素2浮动元素2浮动元素2浮动元素2浮动元素2浮动元素2浮动元素2        
  </p>    
</div>
```
```css
.box { background: #00ff90; padding: 10px; width: 500px; height: 400px; }
.rule1 { float: left; margin: 10px; padding: 10px; background: #ff6a00; width: 250px; text-align: center; }
p { margin-top: 20px; margin-bottom: 20px; }
```
效果图：  
![6.png](https://i.loli.net/2019/09/30/BCo41AJhjPwZVHT.png)

两个浮动元素，后面的浮动元素不会超过前面的浮动元素

## 如果有非浮动元素和浮动元素同时存在，并且非浮动元素在前，则浮动元素不会不会高于非浮动元素
在上一条规则的例子，浮动元素有一个非浮动元素p，而浮动元素没有超过它。

## 浮动元素会尽可能地向顶端对齐、向左或向右对齐
在满足其他规则下，浮动元素会尽量向顶端对齐、向左或向右对齐。  
在上上条的规则中，浮动元素会尽可能靠近不浮动的p元素，左侧对齐。

# 除了以上那些常用规则，还有一些特殊的
## 浮动元素的延伸性
先看一个特殊的例子。  
我们将span元素放在p元素内，并将其高度设置成高于p元素并且左浮动，这个例子的关键在浮动元素高度高于父元素。
```html
<p>        
  在浮动元素之前在浮动元素之前，在浮动元素之前，在浮动元素之前，在浮动元素之前，在浮动元素之前，在浮动元素之前，在浮动元素之前，        
  <span class="high-float">            
    浮动元素比父级元素高        
  </span>    
</p>    
<p>在浮动元素之后在浮动元素之后在浮动元素之后在浮动元素之后在浮动元素之后在浮动元素之后在浮动元素之后在浮动元素之后</p>
```
```css
p { margin-top: 20px; margin-bottom: 20px; background-color: #00ff21; width: 500px; }
.high-float { float: left; height: 80px; line-height: 80px; background-color: orangered; }
```
效果图：  
![8.png](https://i.loli.net/2019/09/30/GEU53FYqXaAT7or.png)

浮动元素高度高于父元素，可以看到浮动元素超出了父元素的底端。

这种情况，只要将父元素也设置成浮动即可。  
将第一个p元素设置成左浮动，效果图：  
![9.png](https://i.loli.net/2019/09/30/qi9IpPmco7jLA12.png)

将父元素p设置成float:left后，浮动元素就会被包含到父元素里面，这就是浮动元素的延伸性。

## 浮动元素超出父级元素的padding
在前面提到的第一条规则：浮动元素的外边界不会超过父级元素的内边界。但有些情况会出现特殊现象：  
- 负margin  
我们将浮动元素的margin-left设置成负数。
```html
<p>    
  在浮动元素之前在浮动元素之前，在浮动元素之前，在浮动元素之前，在浮动元素之前，在浮动元素之前，在浮动元素之前，在浮动元素之前，    
  <span class="minus-margin">        
    负margin-left    
  </span>
</p>
```
```css
p { margin-top: 20px; margin-bottom: 20px; margin-left: 50px; background-color: #00ff21; width: 500px; }
.minus-margin { float: left; height: 80px; line-height: 80px; background-color: orangered; margin-left: -20px; }
```
效果图：  
![10.png](https://i.loli.net/2019/09/30/flOU9wyvXoZsRB4.png)

将margin-left设置成负数之后，浮动的子元素明显超出了父元素的内边界，这难道不是违反了第一条规则吗？  
但仔细想想，这其实是合理的，因为默认情况下marign-left就是0，所以不会超出父元素的内边界，但是将其设置成负数之后，就相当于浮动元素覆盖了自己的内边界一样。

- 浮动元素宽度大于父级元素宽度  
如果我们将浮动元素的宽度设置大于父级元素，效果会如何呢？  
元素左浮动，width大于父级元素
```html
<p>    
  在浮动元素之前在浮动元素之前，在浮动元素之前，在浮动元素之前，在浮动元素之前，在浮动元素之前，在浮动元素之前，在浮动元素之前，    
  <span class="big-width">        
    width大于父级元素    
  </span>
</p>
```
```css
p { margin-top: 20px; margin-bottom: 20px; margin-left: 50px; background-color: #00ff21; width: 250px; }
.big-width { float: left; height: 80px; line-height: 80px; background-color: orangered; width: 300px; }
```
效果图：  
![11.png](https://i.loli.net/2019/09/30/YBcQi5pC7y2fVIl.png)

将浮动元素左浮动，并且宽度超出父级元素时，由于浮动元素宽度较大，它会超过父级元素的右内边界
如果将其设置成右浮动，情况又会怎么样呢？  
![12.png](https://i.loli.net/2019/09/30/XOJFZcU7gDHABbh.png)
可以看到，设置成右浮动后，会超出父级元素的左内边界。

## 重叠问题
重叠问题是指两个元素再同一个位置，会出现上下重叠的问题。    
首先浮动元素要怎么样才会发生重叠呢，设置其margin-top为负数即可。  
```html
<p>        
  <span>            
    在浮动元素之前在浮动元素之前，在浮动元素之前，在浮动元素之前，在浮动元素之前，在浮动元素之前，在浮动元素之前，在浮动元素之前。        
  </span>        
  <span class="overlay">            
    浮动元素重叠        
  </span>    
</p>
```
```css
p { margin-top: 20px; margin-bottom: 20px; margin-left: 50px; background-color: #00ff21; width: 250px; }
.overlay { float: left; height: 80px; line-height: 80px; background-color: orangered; width: 300px; margin-top: -30px; }
```
效果图：  
![13.png](https://i.loli.net/2019/09/30/KdnC1tM3Vi4gjUv.png)

如果浮动元素不设置负margin时，是这样的  
![14.png](https://i.loli.net/2019/09/30/7OVZdyuWJHNT3Bj.png)

可以看到p中正常流元素span的内容会显示在浮动元素上面。  
我们给设置span设置背景图片  
![15.jpg](https://i.loli.net/2019/09/30/s9OVax8cFo7gI2E.jpg)

元素设置背景后，重叠的部分还是会显示背景  
如果将span标签换成div标签，如下：  
```html
<p>     
  <div style="background-image:url(../images/banner1.jpg)">         
    在浮动元素之前在浮动元素之前，在浮动元素之前，在浮动元素之前，在浮动元素之前，在浮动元素之前，在浮动元素之前，在浮动元素之前。     
  </div>     
  <span class="overlay">         
    浮动元素重叠     
  </span> 
</p>
```
效果图：  
![16.jpg](https://i.loli.net/2019/09/30/ja9dZW1OlFkxMAt.jpg)

这种情况下，重叠的部分不会显示背景图片。
那么总结下来就是：
> 1. 行内元素与浮动元素发生重叠，其边框，背景和内容都会显示在浮动元素之上  
> 2. 块级元素与浮动元素发生重叠时，边框和背景会显示在浮动元素之下，内容会显示在浮动元素之上

## clear属性
有的时候，我们不希望一些元素会被旁边的浮动元素影响到，这个时候就需要用到clear属性了。  
**clear属性**：确保当前元素的左右两侧不会有浮动元素。

例如，一下有3个浮动元素：  
![17.png](https://i.loli.net/2019/09/30/XB8O1UEvbDzrno6.png)

代码如下：
```html
<div class="box">        
  <div class="float">浮动元素1</div>        
  <div class="float">浮动元素2</div>        
  <div class="float">浮动元素3</div>    
</div>
```
```css
 .float { float: left; width: 150px; background: #0094ff; border: 1px solid red; margin-left: 5px; }
.cl { clear: left; }
.cr { clear: right; }
.cb { clear: both; }
```
假设有我们有想让第二个浮动元素另起一行进行浮动  
我们对第一个浮动元素添加clear:right保证其右侧不会有浮动元素。修改HTML代码如下  
```html
<div class="box">    
  <div class="float cr">浮动元素1</div>    
  <div class="float">浮动元素2</div>    
  <div class="float">浮动元素3</div>
</div>
```
查看效果，你会发现没啥变化，why？  
因为用错了。。  
那试试给第二个元素添加clear:left保证其左侧不会出现浮动元素  
![18.png](https://i.loli.net/2019/09/30/uH2QaJO4XxrlU7p.png)

可以看到这次clear属性有效果了。  
**原因是：clear只对元素本身的布局起作用。**  
第一个浮动元素添加了clear属性，它并不会影响到其他元素的布局，只会影响自己，所以第二个浮动元素并不会另起一行。  
而第二个浮动元素设置了clear后，我们可以看到clear作用于自己，所以元素另起一行。  

## 清除浮动
清除浮动是一个常见的用法。  
至于为什么要用，首先我们要理解使用浮动会带来什么问题，以及为什么要清除浮动。  

一个块级元素如果没有设置height，其height是由子元素撑开的。  
对子元素使用了浮动之后，子元素会脱离标准文档流。  
也就是说，父级元素中没有内容可以撑开其高度，这样父级元素的height就会被忽略，这就是所谓的高度塌陷。  
要解决这样的问题，我们就是要使用清除浮动。  

对于IE浏览器来说，要清除浮动带来的问题，只需要触发器hasLayout就可以，直接设置样式zoom:1就可以触发。  
对于非IE浏览器，主要有下面几种方法：
### 增加额外的div
这是最简单直接的方法，哪里有浮动元素，就在其父级元素的内容中增加一个（作为最后一个子元素）  
```html
<div style="clear:both"></div>
```
这样就会清除浮动元素带来的问题。  
> 优点：简单直接，初学者常常使用的方法，也易于理解  
> 缺点：增加额外的无意义标签，不利于语义化，每次清除都要添加额外的空标签，造成浪费

### 父级元素添加overflow:hidden
这种方法关键在于触发了[BFC](https://xxsnake28.github.io/2019/09/09/bfc-box-formatting-context-attributes/)
```css
.clearfix{overflow:hidden;zoom:1}
```
> 优点：代码量少，没有额外的标签
> 缺点：如果子元素超出父元素的范围，会造成超出的部分被隐藏

### after伪元素
after表示子元素的后面，通过它可以设置一个具有clear的元素，然后将其隐藏  
```css
clearfix:{    
  zoom:1
}
clearfix:after{    
  display:block; 
  content:''; 
  clear:both; 
  height:0; 
  visibility:hidden;
}
```
> 优点：没有额外标签，综合起来算是比较好的方法  
> 缺点：稍显复杂，但是理解其原理后也挺简单的  
> 值得推荐!!!

# 再来看看float的应用
## 文字环绕效果
float最初的应用就是文字环绕效果，这对图文并茂的文章很有用。  
```html
<div class="box">        
  <img src="1.jpg" class="float" />        
  我是环绕的文字我是环绕的文字我是环绕的文字我是环绕的文字我是环绕的文字我是环绕的文字我是环绕的文字我是环绕的文字我是环绕的文字我是环绕的文字我是环绕的文字我是环绕的文字我是环绕的文字我是环绕的文字我是环绕的文字    
</div>
```
```css
.box { background: #00ff90; padding: 10px; width: 500px; }  
.float {background: #0094ff none repeat scroll 0 0;border: 1px solid red;float: left;margin-left: 5px;width: 400px;}
```
效果图：  
![19.jpg](https://i.loli.net/2019/09/30/28H3Youwmscky14.jpg)

## 横向菜单排列
```html
<ul class="menu clearfix">    
  <li>首页</li>    
  <li>政治</li>    
  <li>娱乐</li>    
  <li>体育</li>    
  <li>游戏</li>
</ul>
```
```css
.clearfix: { zoom: 1; }    
.clearfix:after { display: block; content: ''; clear: both; height: 0; visibility: hidden; }
.menu { background: #0094ff; width: 500px; }    
.menu li { float: left; width: 100px; list-style-type: none; }
```
效果图： 
![20.png](https://i.loli.net/2019/09/30/QwnrxFHO4JzIMXv.png)

这种方式可以很轻松的实现横向菜单效果，但需要注意的是要注意清除浮动，推荐使用display:inline-block来实现

## 布局
float最经常使用的场景就是布局。  
使用float可以很简单的实现布局，而且易于理解。下面我们来实现一个三栏两列的固定布局。  
```html
<div class="header">    
  我是头部</div>
<div class="content clearfix">    
  <div class="side">左侧</div>    
  <div class="main">        
    右侧    
  </div>
</div>
<div class="footer">    
  我是底部
</div>
```
```css
.clearfix: { zoom: 1; }    
.clearfix:after { display: block; content: ''; clear: both; height: 0; visibility: hidden; }
.header, .footer { height: 50px; background: #0094ff; text-align: center; }
.content { margin: 0 auto; width: 1000px; background: #000000; }
.side { float: left; height: 500px; width: 280px; background: #ff006e; }
.main { float: right; height: 500px; width: 700px; background: #fbcfcf; }
```
效果图：  
![21.png](https://i.loli.net/2019/09/30/tRZlSkDoJz8UiMb.png)

> 要注意的就是清除浮动的问题

# 最后总结一下，收个尾
最重要的是要理解下面几点：
- float会造成元素脱离文档流
- float影响元素的几个规则
- 浮动带来的问题以及如何清除浮动
