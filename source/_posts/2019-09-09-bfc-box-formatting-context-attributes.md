---
title: 'BFC(box formatting context)详解'
categories: note
date: 2019-09-09 15:20:32
tags: bfc
---
# BFC是个啥？
在解释 BFC 是什么之前，需要先介绍 Box、Formatting Context的概念。

## BOX：CSS布局的基本单位
Box是CSS布局的对象和基本单位， 直观点来说，就是一个页面是由很多个 Box 组成的。  
元素的类型和 display 属性，决定了这个 Box 的类型。 不同类型的 Box， 会参与不同的 **Formatting Context**（一个决定如何渲染文档的容器），因此Box内的元素会以不同的方式渲染。让我们看看有哪些盒子：
- block-level box:display 属性为 block, list-item, table 的元素，会生成 block-level box。并且参与 block fomatting context
- inline-level box:display 属性为 inline, inline-block, inline-table 的元素，会生成 inline-level box。并且参与 inline formatting context
- run-in box: css3 中才有， 这儿先不扯淡了。

> 这里有必要复习下block-level box一些知识

### block-level box
- w3.org中对块级元素的定义  
  块级元素是那种源文档被格式化为可视块了的元素，然后使这个元素变成块级元素的display属性取值如下： ‘block’, ‘list-item’, 和 ‘table’。  
  块级盒block-level box是这种参与了块级排版上下文的一种盒子，每个块级元素都生成了一个包含后代盒子和生成的内容的主要块级盒，并且这个盒子参与了任何定位的计算。
  ![1150998504-57c26b8536413_articlex.png](https://i.loli.net/2019/08/20/HyvxPksCrXmLKDU.png)
  ![1941446682-57c26b9670ce3_articlex.jpeg](https://i.loli.net/2019/08/20/34ftXl9RuTWJMxb.jpg)
- block-level box特性  
  块状元素排斥其他元素与其位于同一行，可以设定元素的宽（width）和高（height），块级元素一般是其他元素的容器，可容纳块级元素和行内元素。  
  块状元素具有流体特性，即：在默认情况下（非浮动、绝对定位等），水平方向会自动填满外部的容器

## Formatting context
Formatting context 是 W3C CSS2.1 规范中的一个概念。它是页面中的一块渲染区域，并且有一套渲染规则，它决定了其子元素将如何定位，以及和其他元素的关系和相互作用。最常见的 Formatting context 有 Block fomatting context (简称BFC)和 Inline formatting context (简称IFC)。  
CSS2.1 中只有 BFC 和 IFC, CSS3 中还增加了 GFC 和 FFC。
> IFC也就是inline formatting content的缩写。

## BFC定义
BFC(Block formatting context)直译为"块级格式化上下文"。它是一个独立的渲染区域，只有Block-level box参与， 它规定了内部的Block-level Box如何布局，并且与这个区域外部毫不相干。
> BFC是 W3C CSS 2.1 规范中的一个概念，它决定了元素如何对其内容进行定位，以及与其他元素的关系和相互作用。当涉及到可视化布局的时候，Block Formatting Context提供了一个环境，HTML元素在这个环境中按照一定规则进行布局。   
> 一个环境中的元素不会影响到其它环境中的布局。比如浮动元素会形成BFC，浮动元素内部子元素的主要受该浮动元素影响，两个浮动元素之间是互不影响的。这里有点类似一个BFC就是一个独立的行政单位的意思。也可以说BFC就是一个作用范围。可以把它理解成是一个独立的容器，并且这个容器的里box的布局，与这个容器外的毫不相干。  
> 另一个通俗点的解释是：在普通流中的 Box(框) 属于一种 formatting context(格式化上下文) ，类型可以是 block ，或者是 inline ，但不能同时属于这两者。并且， Block boxes(块框) 在 block formatting context(块格式化上下文) 里格式化， Inline boxes(块内框) 则在 inline formatting context(行内格式化上下文) 里格式化。任何被渲染的元素都属于一个 box ，并且不是 block ，就是 inline 。即使是未被任何元素包裹的文本，根据不同的情况，也会属于匿名的 block boxes 或者 inline boxes。所以上面的描述，即是把所有的元素划分到对应的 formatting context 里。

canvas会设立一个BFC，这也是最外层的formatting context了，问题的复杂性在于有些块级盒内部也可以产生BFC（至少它必须也能包含块级盒），于是说BFC是可以嵌套。不是所有块级盒内部都可以产生BFC，比如说要是这盒里面连块级盒都没有，都是行内盒那就产生IFC。不过，只要它的子节点里面有一个块级盒，它就产生BFC，那些行内元素，会自动套一个匿名的块级行盒。

## BFC的布局规则
- 内部的Box会在垂直方向，一个接一个地放置
- Box垂直方向的距离由margin决定。属于同一个BFC的两个相邻Box的margin会发生重叠
- 每个元素的margin-box的左边， 与包含块border-box的左边相接触(对于从左往右的格式化，否则相反)。即使存在浮动也是如此。
- BFC的区域不会与float box重叠。
  > 关于这条规则的几点说明：  
  > 当容器有足够的剩余空间容纳 BFC 的宽度时，所有浏览器都会将 BFC 放置在浮动元素所在行的剩余空间内。   
    当 BFC 的宽度大于容器剩余宽度时，最新版本的浏览中只有firefox会在同一行显示，其它浏览器均换行。
- BFC就是页面上的一个隔离的独立容器，容器里面的子元素不会影响到外面的元素。反之也如此。
- 计算BFC的高度时，浮动元素也参与计算。

# 哪些元素会生成BFC
- 根元素
- float属性不为none
- position为absolute或fixed
- display为inline-block, table-cell, table-caption, flex, inline-flex
- overflow不为visible
> 关于overflow:visible：  
  overflow:visible的块盒就不产生BFC，不但不产生BFC，啥FC都不产生，它的子元素直接搞进自己外层的BFC鸟：  
  overflow:visible这个限制只对所谓的块盒（既包含块级盒、自己又是块级盒）存在，有些盒内部也能包含块级元素，但是它本身又不是块级元素（比如display为table-cell、inline-block、或者盒本身是flex item等），因为外面不是BFC，所以它们不论如何一定会给包含的块级盒创建一个新的BFC出来。
>
> 关于浮动：  
  浮动是个行级的行为，当遇到浮动元素的时候，会首先"假装"它是个行内元素进行排版，排好后就往浮动的方向挤到挤不过去为止（遇到边界或者其它浮动元素）。  
  某一方向有clear的时候，浮动元素总是挤到边界，在垂直方向上的行为类似"换行"。
  排好一个浮动元素之后，这一行就要重排一次。所以说浮动元素会造成行级的reflow。重排的时候，行盒会躲开浮动元素。之后的块级盒（不论是行盒还是其它盒）也都会躲开浮动元素排布。

## BFC的作用及原理
### 自适应的两栏布局
```html
<style>
    body {
        width: 300px;
        position: relative;
    }
    .aside {
        width: 100px;
        height: 150px;
        float: left;
        background: #f66;
    }
    .main {
        height: 200px;
        background: #fcc;
    }
</style>
<body>
    <div class="aside"></div>
    <div class="main"></div>
</body>
```
生成的页面长这样：  
![3517522082-57c2591cad033_articlex.png](https://i.loli.net/2019/08/20/SvkeMW4g3OnJmY8.png)

根据BFC布局规则第3条：  
> 每个元素的margin-box的左边， 与包含块border-box的左边相接触(对于从左往右的格式化，否则相反)。即使存在浮动也是如此。

因此，虽然存在浮动的元素aslide，但main的左边依然会与包含块的左边相接触。  
根据BFC布局规则第四条：
> BFC的区域不会与float box重叠。

我们可以通过通过触发main生成BFC， 来实现自适应两栏布局。
```css
.main {
    overflow: hidden;
}
```
当触发main生成BFC后，这个新的BFC不会与浮动的aside重叠。因此会根据包含块的宽度，和aside的宽度，自动变窄。效果如下：  
![1661171205-57c25a55e227f_articlex.png](https://i.loli.net/2019/08/20/sp4u5DPxfIOKX38.png)  

**对比**： 实现布局的另一种方式利用块状元素流体特性实现的自适应布局
> 利用块状元素流体特性实现的自适应布局  
  常用方法：浮动或者定位+margin撑开  
  不足之处：我们需要知道浮动或绝对定位内容的尺寸。然后，流体内容才能有对应的margin或padding或border值进行位置修正。

### 清除内部浮动
```html
<style>
    .par {
        border: 5px solid #fcc;
        width: 300px;
    }
 
    .child {
        border: 5px solid #f66;
        width:100px;
        height: 100px;
        float: left;
    }
</style>
<body>
    <div class="par">
        <div class="child"></div>
        <div class="child"></div>
    </div>
</body>
```
效果如下图：  
![1494766287-57c25ac9a0710_articlex.png](https://i.loli.net/2019/08/20/mB26PJcZ5b3KQt7.png)  

根据BFC布局规则第六条：
> 计算BFC的高度时，浮动元素也参与计算  

为达到清除内部浮动，我们可以触发par生成BFC，那么par在计算高度时，par内部的浮动元素child也会参与计算。  
```css
.par {
    overflow: hidden;
}
```
效果如下：  
![4197597101-57c265f90133e_articlex.png](https://i.loli.net/2019/08/20/PSUHTqQYc98AKjo.png)

### 防止margin重叠
```html
<style>
    p {
        color: #f55;
        background: #fcc;
        width: 200px;
        line-height: 100px;
        text-align:center;
        margin: 100px;
    }
</style>
<body>
    <p>Haha</p>
    <p>Hehe</p>
</body>
```
页面：  
![577253204-57c2667b4c284_articlex.png](https://i.loli.net/2019/08/20/oheDkX3Q89wvyzb.png)  

两个p之间的距离为100px，发送了margin重叠。  
根据BFC布局规则第二条：
> Box垂直方向的距离由margin决定。属于同一个BFC的两个相邻Box的margin会发生重叠

我们可以在p外面包裹一层容器，并触发该容器生成一个BFC。那么两个P便不属于同一个BFC，就不会发生margin重叠了。  
```html
<style>
    .wrap {
        overflow: hidden;
    }
    p {
        color: #f55;
        background: #fcc;
        width: 200px;
        line-height: 100px;
        text-align:center;
        margin: 100px;
    }
</style>
<body>
    <p>Haha</p>
    <div class="wrap">
        <p>Hehe</p>
    </div>
</body>
```

效果如下:  
![3493982590-57c2672f379f7_articlex.png](https://i.loli.net/2019/08/20/aW4K9TlJr1noz2E.png)

### 总结
以上的几个例子都体现了BFC布局规则第五条：
> BFC就是页面上的一个隔离的独立容器，容器里面的子元素不会影响到外面的元素。反之也如此。

因为BFC内部的元素和外部的元素绝对不会互相影响，因此， 当BFC外部存在浮动时，它不应该影响BFC内部Box的布局，BFC会通过变窄，而不与浮动有重叠。同样的，当BFC内部有浮动时，为了不影响外部元素的布局，BFC计算高度时会包括浮动的高度。避免margin重叠也是这样的一个道理。
