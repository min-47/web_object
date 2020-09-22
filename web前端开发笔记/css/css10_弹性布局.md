# 前言

吐槽：这个章节很复杂，累觉不爱

#### 基本概念：

采用Flex布局的元素，称为Flex容器，简称容器，他所有的子元素自动成为容器成员，称为Flex项目

![](http://www.ruanyifeng.com/blogimg/asset/2015/bg2015071004.png)

容器默认存在两根轴：水平的主轴（main axis）和垂直的交叉轴（cross axis）。主轴的开始位置（与边框的交叉点）叫做`main start`，结束位置叫做`main end`；交叉轴的开始位置叫做`cross start`，结束位置叫做`cross end`。

# 容器属性

六种属性是设置在容器上

#### flex-direction属性

​	flex-direction属性决定主轴的方向**（即项目的排列方向）**

| 值             | 描述                       |
| -------------- | -------------------------- |
| row（默认值）  | 主轴为水平方向，起点在左端 |
| row-reverse    | 主轴为水平方向，起点在右端 |
| column         | 主轴为垂直方向，起点在上沿 |
| column-reverse | 主轴为垂直方向，起点在下沿 |

```html
<style type="text/css">
.container{
	width: 400px;
	margin: auto;
    f
	border: solid 2px black;
}
.container div{
	width: 100px;
	height: 100px;
	margin: 15px;
    display: flex;
	flex-direction: row;
	line-height: 100px;
	text-align: center;
	background-color: #FFFF00;
		}
	</style>
<body>
	<div class="container">
	<div>第一个项目</div>
	<div>第二个项目</div>
	<div>第三个项目</div>
</div>
</body>
```

#### flex-wrap属性

`flex-wrap`属性定义，如果一条轴线排不下，如何换行。

| 值             | 描述               |
| -------------- | ------------------ |
| nowrap（默认） | 不换行             |
| wrap           | 换行，第一行在上方 |
| wrap-reverse   | 换行，第一行在下方 |

```css
.container{
	width: 300px;
	margin: auto;
	display: flex;
	flex-direction: row;
	flex-wrap: wrap-reverse;
	border: solid 2px black;
}
.container div{
	width: 100px;
	height: 100px;
	margin: 15px;
	line-height: 100px;
	text-align: center;
	background-color: #FFFF00;
		}
```

#### flex-flow属性

`flex-flow`属性是`flex-direction`属性和`flex-wrap`属性的简写形式，默认值为`row nowrap`。

####  justify-content属性

`justify-content`属性定义了项目在主轴上的对齐方式

| 值                 | 描述                                                         |
| ------------------ | ------------------------------------------------------------ |
| flex-start（默认） | 左对齐                                                       |
| flex-end           | 右对齐                                                       |
| center             | 居中                                                         |
| space-between      | 两端对齐，项目之间的间隔都相等                               |
| space-around       | 每个项目两侧间隔相等,最前和最后元素跟边框的距离为中间元素距离的一半 |
| space-evenly       | 每个元素，元素与边界之间的距离全部平均分配                   |

```html
.container{
	width: 1000px;
	margin: auto;
	display: flex;
	flex-direction: row;
	justify-content: space-evenly;	 
	border: solid 2px black;
}
.container div{
	width: 100px;
	height: 100px;
	margiSn: 15px;
	line-height: 100px;
	text-align: center;
<style type="text/css">
.container{
	width: 1000px;
	margin: auto;
	display: flex;
	flex-direction: row;
	justify-content: space-evenly;	 
	border: solid 2px black;
}
.container div{
	width: 100px;
	height: 100px;
	margiSn: 15px;
	line-height: 100px;
	text-align: center;
	background-color: #FFFF00;
		}
	</style>
<body>

<main class="container">
	<div>第一个项目</div>
	<div>第二个项目</div>
	<div>第三个项目</div>
	<div>第四个项目</div>
	<div>第五个项目</div>
	<div>第六个项目</div>
</main>

</body>	background-color: #FFFF00;
		}
```

####  align-items属性

`align-items`属性定义项目在交叉轴上如何对齐。

| 值               | 描述                                               |
| ---------------- | -------------------------------------------------- |
| strech（默认值） | 如果项目未设置高度或者为auto，将占满整个容器的高度 |
| flex-sart        | 交叉轴的起点对齐                                   |
| flex-end         | 交叉轴的终点对齐                                   |
| center           | 交叉轴的中点对齐                                   |
| baseline         | 项目的第一行文字的基线对齐                         |

```css
.container{
	width: 1000px;
	height: 400px;
	margin: auto;
	display: flex;
	flex-direction: column;
	align-items: flex-end;	 
	border: solid 2px black;
}
.container div{
	width: 100px;
	height: 100px;
	margin: 15px;
	line-height: 100px;
	text-align: center;
	background-color: #FFFF00;
		}
```

#### align-content属性

`align-content`属性定义了多根轴线的对齐方式。如果项目只有一根轴线，该属性不起作用。

| 值            | 描述                                                         |
| ------------- | ------------------------------------------------------------ |
| stretch       | 轴线占满整个交叉轴。                                         |
| flex-start    | 与交叉轴的起点对齐                                           |
| flex-end      | 与交叉轴的终点对齐                                           |
| center        | 与交叉轴的中点对齐                                           |
| space-between | 与交叉轴两端对齐，轴线之间的间隔平均分布。                   |
| space-around  | 每根轴线两侧的间隔都相等。所以，轴线之间的间隔比轴线与边框的间隔大一倍 |

```html
<style type="text/css">
.container{
	width: 450px;
	height: 400px;
	margin: auto;
	display: flex;
	flex-direction: row;
	flex-wrap: wrap;
	align-items: stretch;
	align-content: stretch;	 
	border: solid 2px black;
}
.container div{
	width: 100px;
	/*height: 100px;*/
	margin: 15px;
	/*line-height: 100px;*/
	text-align: center;
	background-color: #FFFF00;
		}
	</style>
<body>

<main class="container">
	<div>第一个项目</div>
	<div>第二个项目</div>
	<div>第三个项目</div>
	<div>第四个项目</div>
	<div>第五个项目</div>
	<div>第六个项目</div>
</main>

</body>
```

# 项目属性

以下6个属性设置在项目上。

#### Oder属性

`order`属性定义项目的排列顺序。数值越小，排列越靠前，默认为0。

```html
<style type="text/css">
.container{
	width: 450px;
	height: 400px;
	margin: auto;
	display: flex;
	flex-direction: row;
	flex-wrap: wrap;
	align-content: stretch;	 
	border: solid 2px black;
}
.container div{
	width: 100px;
	height: 100px;
	margin: 15px;
	/*line-height: 100px;*/
	text-align: center;
	background-color: #FFFF00;
		}
.container div:nth-of-type(1){
	order: 0;
		}
.container div:nth-of-type(2){
	order: 1;
		}
.container div:nth-of-type(3){
	order: 2;
		}
.container div:nth-of-type(4){
	order: 3;
		}
</style>
<body>

<main class="container">
	<div>第一个项目</div>
	<div>第二个项目</div>
	<div>第三个项目</div>
	<div>第四个项目</div>
	<div>第五个项目</div>
	<div>第六个项目</div>
</main>
</body>
```

#### flex-grow属性

`flex-grow`属性定义项目的放大比例，默认为`0`，即如果存在剩余空间，也不放大。

```html
<style type="text/css">
.container{
	width: 1200px;
	height: 400px;
	margin: auto;
	display: flex;
	flex-direction: row;
	flex-wrap: wrap;
	align-content: stretch;	 
	border: solid 2px black;
}
.container div{
	width: 100px;
	height: 100px;
	margin: 15px;
	/*line-height: 100px;*/
	text-align: center;
	background-color: #FFFF00;
		}
.container div:nth-of-type(1){
	order: 0;
	flex-grow: 0;
		}
.container div:nth-of-type(2){
	order: 1;
	flex-grow: 1;
		}
.container div:nth-of-type(3){
	order: 2;
	flex-grow: 2;
		}
.container div:nth-of-type(4){
	order: 3;
	flex-grow: 3;
		}
</style>
<body>

<main class="container">
	<div>第一个项目</div>
	<div>第二个项目</div>
	<div>第三个项目</div>
	<div>第四个项目</div>
	<div>第五个项目</div>
	<div>第六个项目</div>
</main>

</body>
```

#### flex-shrink属性

`flex-shrink`属性定义了项目的缩小比例，默认为1，即如果空间不足，该项目将缩小

如果所有项目的`flex-shrink`属性都为1，当空间不足时，都将等比例缩小。如果一个项目的`flex-shrink`属性为0，其他项目都为1，则空间不足时，前者不缩小。

==负值对该属性无效。==

```html
<style type="text/css">
.container{
	width: 300px;
	/*height: 400px;*/
	margin: auto;
	display: flex;
	flex-direction: row;
	flex-wrap: nowrap;
	align-content: stretch;	 
	border: solid 2px black;
}
.container div{
	width: 100px;
	height: 100px;
	margin: 15px;
	/*line-height: 100px;*/
	text-align: center;
	background-color: #FFFF00;
		}
.container div:nth-of-type(1){	 
	flex-shrink:  0;
		}
.container div:nth-of-type(2){	 
	flex-shrink:  1;
		}
.container div:nth-of-type(3){
	flex-shrink:  0;
		}
.container div:nth-of-type(4){
	flex-shrink:  0;
		}
</style>
<body>
<main class="container">
	<div>第一个项目</div>
	<div>第二个项目</div>
	<div>第三个项目</div>
	<div>第四个项目</div>
	<div>第五个项目</div>
	<div>第六个项目</div>
</main>
</body>
```

#### flex-basis属性

`flex-basis`属性定义了在分配多余空间之前，项目占据的主轴空间（main size）。

浏览器根据这个属性，计算主轴是否有多余空间。它的默认值为`auto`，即项目的本来大小。

它可以设为跟`width`或`height`属性一样的值（比如350px），则项目将占据固定空间。

```html
<style type="text/css">
.container{
	width: 300px;
	/*height: 400px;*/
	margin: auto;
	display: flex;
	flex-direction: row;
	flex-wrap: nowrap;
	align-content: stretch;	 
	border: solid 2px black;
}
.container div{
	width: 100px;
	height: 100px;
	margin: 15px;
	/*line-height: 100px;*/
	text-align: center;
	background-color: #FFFF00;
		}
.container div:nth-of-type(1){	 
	flex-shrink:  0;
    /*添加在这里*/
	flex-basis: 200px;
		}
.container div:nth-of-type(2){	 
	flex-shrink:  1;
		}
.container div:nth-of-type(3){
	flex-shrink:  0;
		}
</style>
<body>
<main class="container">
	<div>第一个项目</div>
	<div>第二个项目</div>
	<div>第三个项目</div>
	<!-- <div>第四个项目</div>
	<div>第五个项目</div>
	<div>第六个项目</div> -->
</main>
</body>
```

####  flex属性

`flex`属性是`flex-grow`, `flex-shrink` 和 `flex-basis`的简写，默认值为`0 1 auto`。后两个属性可选。

该属性有两个快捷值：`auto` (`1 1 auto`) 和 none (`0 0 auto`)。

#### align-self属性

`align-self`属性允许单个项目有与其他项目不一样的对齐方式，可覆盖`align-items`属性。默认值为`auto`，表示继承父元素的`align-items`属性，如果没有父元素，则等同于`stretch`。

```html
<style type="text/css">
.container{
	width: 800px;
	height: 400px;
	margin: auto;
	display: flex;
	flex-direction: row;
	flex-wrap: nowrap;
	align-items: flex-start;
	align-content: stretch;	 
	border: solid 2px black;
}
.container div{
	width: 100px;
	height: 100px;
	margin: 15px;
	/*line-height: 100px;*/
	text-align: center;
	background-color: #FFFF00;
		}
.container div:nth-of-type(1){	 
	flex-shrink:  0;
	flex-basis: 200px;
	align-self: flex-end;
		}
.container div:nth-of-type(2){	 
	flex-shrink:  1;
		}
.container div:nth-of-type(3){
	flex-shrink:  0;
		}
</style>
<body>
<main class="container">
	<div>第一个项目</div>
	<div>第二个项目</div>
	<div>第三个项目</div>
	<div>第四个项目</div>
	<div>第五个项目</div>
	<div>第六个项目</div>
</main>
```

