# 文档流

#### 什么是文档流

把网页水平方向当成x轴，垂直方向当成y轴，文档流就是z=0的一个平面，在这个平面里，窗体自上而下分成一行一行，并在每行按从左到右的顺序排放元素，无越级，秩序

#### 什么是脱离文档流

z-index：0;

在这个 x,y,z三维空间里，元素脱离了z=0这个平面，定位在了z！= 0 的位置上

# float浮动

两个最主要使用方式

* block元素水平排列
* 文字与图片环绕排版

:one:1脱离文档流，文档流就没有他的位置，所以2顶替了1 的位置

```html
<style type="text/css">
		div {
			width: 200px;
			height: 200px;
			display: inline-block;
		}
		div:nth-of-type(1){
			border: solid 5px red;
		}
		div:nth-of-type(2){
		background-color: green;
		}
	</style>
</head>
<body>
	<div></div>
	<div></div>
</body>
/*并列*/
```

:two:1和2都脱离文档流：脱离后的元素没有行的概念，只能跟在前面的脱离元素后面显示

:three:1回到文档流：1取消float回到文档流，占回原本的位置，2还是浮动。只是他前面没有浮动元素，只能在原有的位置上浮动

# 清除浮动

#### clearfix

属性： clearfix 对前后元素无效，只能作用于自身

| 取值  | 描述                             |
| ----- | -------------------------------- |
| none  | 默认值，允许两边都可以有浮动对象 |
| left  | 不允许左边有浮动对象             |
| right | 不允许右边有浮动对象             |
| both  | 左右都不允许有浮动对象           |

#### after伪元素优化clearfix



####  BFC

overflow：hidden：触发BFC，计算浮动元素高度，从而撑起父元素高度

















