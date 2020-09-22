# 定位——position属性

position，用于指定元素的定位方式

#### 常用取值

| 取值     | 描述                         |
| -------- | ---------------------------- |
| static   | 默认值，位置偏移属性不起作用 |
| relative | 相对定位                     |
| absolute | 绝对定位                     |
| fixed    | 固定定位                     |
| sticky   | 粘性定位                     |

#### 位置偏移属性

| 属性名称 | 说明     |
| -------- | -------- |
| top      | 距离顶部 |
| right    | 距离右边 |
| bottom   | 距离下边 |
| left     | 距离左边 |

#### 默认static

不脱离文档流，就是文档流的position默认值

举例

```html
	<style type="text/css">
		.containter{
			background-color: #868686;
			width: 100%;
			height: 300px;  

		}
		.containt{
			background-color: yellow;
			width: 100px;
			height: 100px;
			position: static;
			/*left: 10px;*/不起作用
		}
	</style>
</head>
<body>
	<div class="containter">
		<div class="containt"></div>
		<div></div>
	</div>
</body>
```



#### relative属性

举例

元素的位置相对于其原位置进行移动

```html
<style type="text/css">
		.containter{
			background-color: #868686;
			width: 100%;
			height: 300px;  

		}
		.containt{
			background-color: yellow;
			width: 100px;
			height: 100px;
			position: relative;
			left: 50px;
		}
		.containt-c{
			background-color: red;
			width: 100px;
			height: 100px;
			/*position: relative;
			left: 50px;*/
		}
	</style>
</head>
<body>
	<div class="containter">
		<div class="containt"></div>
		<div class="containt-c"></div>
	</div>
</body>
```

# 绝对定位 absolute

脱离文档流，相对于最近的非==static定位祖先元素==的偏移，来确定位置，如果都没有，则相对于dody位置

绝对定位的元素可以设置外边距（margin）且不会与其他边距合并

#### 举例1 相对于body定位

祖先元素都没有非static的定位，则相对于body位置定位。不受父元素的影响

```html
<style type="text/css">
		.containter{
			background-color: #868686;
			width: 100%;
			height: 300px; 
			margin-top: 50px; 
		}
		.containt-absolute{
			background-color:red ;
			width: 100px;
			height: 100px;
			position:  absolute;
			top: 10px;
		}
	</style>
</head>
<body>
	<div class="containter">
		<div class="containt-absolute"></div>
	</div>
</body>
```

#### 举例2 祖先元素有非static定位

```html
<style type="text/css">
		.containter{
			background-color: #868686;
			width: 100%;
			height: 300px; 
			position: relative;
			margin-top: 50px; 

		}
		.containt-relative{
			background-color: yellow;
			width: 100px;
			height: 100px;
			position: relative;
			left: 50px;
			top: 30px;
		}
		.containt-absolute{
			background-color:red ;
			width: 100px;
			height: 100px;
			position:  absolute;
			top: 30px;
		}
	</style>
</head>
<body>
	<div class="containter">
		<div class="containt-relative"></div>
		<div class="containt-absolute"></div>
	</div>
</body>
```

#### 举例3控制块级元素尺寸

==四个位置偏移属性 都要设置==

```html
<style type="text/css">
		.containter{
			background-color: #868686;
			width: 300px;
			height: 300px; 
			position: relative; 
		}
		 
		.containt-absolute{
			background-color:red;
			position:  absolute;
			top: 20px;
			left: 10px;
			right: 0;
			bottom: 20px;
		}
	</style>
</head>
<body>
	<div class="containter">
		<div class="containt-absolute"></div>
	</div>
</body>
```

#### 举例4 水平垂直居中

让子块在父块中水平居中的几种方法

#### 直接计算宽度

```css
div{
margin: xxpx;
}
```

#### 计算宽度——绝对定位

```css
.father{
 
			width: 300px;
			height: 300px; 
			margin: auto;
			position: relative;
			border:solid 2px blue;	 
		}
		 
		.child{
			background-color:red;
			width: 100px;
			height: 100px;
			position:  absolute;
			top: 50%;
			left: 50%;
			transform: translate(-50%,-50%);

		}
```

#### 百分比定位，不受图片尺寸影响

```html
<style type="text/css">

		*{
			padding: 0;
			margin: 0;
		}
		.father{

			width: 300px;
			height: 300px; 
			margin: auto;
			position: relative;
			border:solid 2px blue;
		}
		 
		.child{
			background-color:red;
			width: 100px;
			height: 100px;
			position:  absolute;
            /*左上角的点定位正中心*/
			top: 50%;
			left: 50%;
            /*加外边距使其偏会正中心*/
             margin-left: -50px;
			margin-top: -50px; 
		}
	</style>
</head>
<body>
	<div class="father">
		<div class="child"></div>
	</div>
```

#### 定位+2D转换

```css
.father{
			width: 300px;
			height: 300px; 
			margin: auto;
			position: relative;
			border:solid 2px blue;	 
		}

		.child{
			background-color:red;
			width: 100px;
			height: 100px;
			position:  absolute;
			top: 50%;
			left: 50%;
			transform: translate(-50%,-50%);

		}
```

#### 滚动

会随着祖先元素滚动而滚动

```html
<style type="text/css">
		*{
			padding: 0;
			margin: 0;
		}
.father{
			margin: auto;
			width: 300px;
			height: 300px; 
			margin: auto;
			position: relative;
			top: 100px;
			overflow: scroll;
			border:solid 2px blue;

		}
		.mather{
			background-color: yellow;
			width: 300px;
			height: 1300px;
			position: relative;
			 
		}
		.child{
			background-color:red;
			width: 100px;
			height: 100px;
			position:  absolute;
			top: 100px;

		}
	</style>
</head>
<body>
	<div class="father">
		<!-- <div class="containt-relative"></div> -->
		<div class="mather">
		<div class="child"></div>
		</div>
		
		
	</div>
</body>
```



# 固定定位 fixed

脱离文档流

相对于屏幕窗口固定，元素位置在屏幕滚动时不会改变

打印时，元素回湖村乡每页的固定位置

##### 举例

```html
 	<style type="text/css">

		*{
			padding: 0;
			margin: 0;
		}
		.father{
			/*background-color: #868686;*/
			margin: auto;
			width: 300px;
			height: 300px; 
			margin: auto;
			position: relative;
			/*left: 50%*/
			top: 100px;
			overflow: scroll;
			border:solid 2px blue;
			/*margin-top: 50px; */

		}
		.mather{
			background-color: yellow;
			width: 300px;
			height: 1300px;
			position: relative;
			 
		}
		.child{
			background-color:red;
			width: 100px;
			height: 100px;
			position: fixed;
            /*这里使用了fixed*/
			top: 100px;

		}
	</style>
</head>
<body>
	<div class="father">
		<div class="mather">
		<div class="child"></div>
		</div>
```

#### 粘性定位：sticky

吸附，常见的吸顶，吸底（移动端网站的头返回栏）的效果适用

sticky 是容器相关的，也就说 sticky 的特性只会在他所处的容器里生效。

如果是兄弟元素会出现覆盖效果

如果是同级元素会出现顶替效果

```html
	<style type="text/css">
 		section {
 		  width: 200px;
 		  margin: auto;
		  border: 2px solid green;
		  margin-bottom: 40px;
}
		h2 {
		  position: sticky;
		  position: -webkit-sticky;
		  top: 0;
		  background-color: red;
		  color: #fff;
}
	</style>
</head>
<body>
	<section>
  <h2>I am sticky1</h2>
  <p>  B  lood, Sweat And Tears   Winston Churchill May 13, 1940    On Friday evening last I received from His Majesty the mission to form a new administration.   It was the evident will of Parliament and the nation that this should be conceived on the broadest possibl idered it in the public interest to suggest to the Speaker that the House should be summoned today. At the end of today's proce al reconstruction will make al  I feel sure that our cause will not be suffered to fail among men.   I feel entitled at this juncture, at this time, to claim the aid of all and to say, Come then, let us go forward together with our united strength. </p>
 </section><section>
  <h2>I am sticky2</h2>
  <p>Blood, Sweat And Tears   Winston Churchill May 13, 1940    On Friday evening last I received from His Majesty the mission to form a new administration.   It was the evident will of Parliament and the nation that this should be conceived on the broadest possible basis and that it should include all parties.    I have already completed the most  the aid of all and to say, Come then, let us go forward together with our united strength. </p>
 </section><section>
  <h2>I am sticky3</h2>
  <p>Blood, Sweat And Tears   Winston Churchill May 13, 1940    On Friday evening last I received from His Majesty the mission to form a new administration.   It was the evident will of Parliament and the nation that this should be conceived on the broadest pos  and lamentable catalogue of human crime. That is our policy.   You ask, what is our aim I can answer in one word, It is victory. Victory at all costs-victory in spite of all terrors-victory, however long and hard the road may be, for without victory there is no survival.   Let that be realized. No survival for the British Empire, no survival for all that the British Empire has stood for, no survival for the urge, the impulse of the ages, that mankind shall move forward toward his goal.   I take up my task in buoyancy and hope. I feel sure that our cause will not be suffered to fail among men.   I feel entitled at this juncture, at this time, to claim the aid of all and to say, Come then, let us go forward together with our united strength. </p>
 </section>
</body>
```

#### position取值小结

* static

  默认值，元素在文档流中，元素框正常生成

* relative

  元素在文档流中，可相对于原始位置偏移某距离

  元素仍保持其未定位前的形状，它原本所占的位置不会被顶替

* absolute

  脱离文档流，并相对于另一个非static元素定位

  元素原先在正常文档流中所占的为主不复存在

  不论原先它在文档流中是何种类型的框，定位会自动生成一个块级框

* fixed

     脱离文档流，元素相当于浏览器窗口定位，其他和absolute一样

* sticky

  元素在文档流中，以摸个div为区域定位

#### 层级z-index

确定z轴方向上元素的显示层级（也可以理解为z轴上的元素显示优先级）

##### 举例

z-index仅对非static元素生效

父元素无法优先显示子元素

z-index不是作用于全局







