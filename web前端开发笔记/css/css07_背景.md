# 基础

#### 背景色

属性： background-color 属性

```css
p {background-color: gray;}
```

#### 背景图像

属性： background-image 属性

* 设置一个背景图像需要设置URL值
* 背景属性不能被继承
* 可为其他元素设置背景图像

```css
body {background-image: url(/i/eg_bg_04.gif);}
```

####  背景重复

属性：background-repeat 属性

| 值        | 描述                       |
| --------- | -------------------------- |
| repeat-x  | 图像只水平 向上重复        |
| repeat-y  | 图像只 垂直方向上重复      |
| no-repeat | 不允许图像在任何方向上平铺 |
| v         | 图像在水平垂直方向上都平铺 |

```css
body{ background-repeat: repeat-y;}
```

#### 背景定位

属性： background-position属性

* 设置背景位置

* 使用一些关键字：top、bottom、left、right 和 center。通常，这些关键字会成对出现

#### 背景关联

属性： background-attachment:属性

值：fixed

* 通过这个歌属性可以声明图像相对于可视区是固定的，因此不会受到滚动的影响

```css
body 
  {
  background-image:url(/i/eg_bg_02.gif);
  background-repeat:no-repeat;
  background-attachment:fixed
  }
```

# 进阶

#### 颜色渐变

##### 线性渐变

属性：background-image:*Linear Gradients*属性

举例1：顶部渐变

```css
background-image: linear-gradient(direction, color-stop1, color-stop2, ...);
/*默认是从顶部开始线性渐变*/
```

举例2：左到右渐变

```css
#grad {
  height: 200px;
  background-image: linear-gradient(to right, red , yellow);
}
/*从左边开始的线性渐变，起点是红色，过渡到蓝色*/
```

举例3：对角

```css
#grad {
  height: 200px;
  background-image: linear-gradient(to bottom right, red, yellow);
}
/* 从左上角开始（到右下角）的线性渐变。起点是红色，慢慢过渡到黄色*/
```

举例4：使用角度

```css
background-image: linear-gradient(angle, color-stop1, color-stop2);
```

![](https://www.runoob.com/wp-content/uploads/2014/07/7B0CC41A-86DC-4E1B-8A69-A410E6764B91.jpg)

举例5：使用多个节点渐变

```css
#grad {
  background-image: linear-gradient(red, yellow, green);
}
#grad {
  /* 标准的语法 */
  background-image: linear-gradient(to right, red,orange,yellow,green,blue,indigo,violet);
}
```

举例6：使用透明度

```css
#grad {
  background-image: linear-gradient(to right, rgba(255,0,0,0), rgba(255,0,0,1));
}

/*从左到右的线性渐变，带有透明度*/
```

举例7; 重复性渐变

repeating-linear-gradient() 函数用于重复线性渐变

```css
#grad {
  /* 标准的语法 */
  background-image: repeating-linear-gradient(red, yellow 10%, green 20%);
}
```

##### 径向渐变

属性：background-image: radial-gradient属性

* 径向渐变由它的中心定义

* 渐变的中心是 center（表示在中心点），渐变的形状是 ellipse（表示椭圆形），渐变的大小是 farthest-corner（表示到最远的角落）。

```css
background-image: radial-gradient(shape size at position, start-color, ..., last-color);
```

举例：颜色结点

```css
#grad {/*颜色节点均匀分布*/
  background-image: radial-gradient(red, yellow, green);
}
#grad {/*颜色结点不均匀分布*/
  background-image: radial-gradient(red 5%, yellow 15%, green 60%);
}
```

举例2：设置形状

shape 参数定义了形状。它可以是值 circle 或 ellipse。其中，circle 表示圆形，ellipse 表示椭圆形。默认值是 ellipse。

```css
#grad {
  background-image: radial-gradient(circle, red, yellow, green);
}
```

举例3：重复径向渐变

```css
#grad {
  background-image: repeating-radial-gradient(red, yellow 10%, green 15%);
}
```

#### 背景裁切

background-clip属性，以盒子模型为基准，设置背景显示范围

| 值          | 描述                       |
| ----------- | -------------------------- |
| border-box  | 默认值，背景被裁剪到边框盒 |
| padding-box | 背景被裁剪到内边距框       |
| content-box | 背景被裁剪到内容框         |

```html
<style type="text/css">
		.container{
			border: dashed 5px black;
			padding: 30px;
			background-clip: padding-box;
			background-color: pink;
			height: 400px;
			width:400px;

		}
	</style>
</head>
<body>
	 <div class="container">
	 	<div>hello</div>
	 </div>
</body>
```

#### 背景图像尺寸

属性： background-size

| 值      | 描述                         |
| ------- | ---------------------------- |
| auto    | 背景图片的真实大小           |
| cover   | 背景图片等比例缩放到铺满盒子 |
| contain | 背景图片拉伸以适应盒子大小   |

```html
<style type="text/css">
		.container{
			border: dashed 5px black;
			padding: 30px;
			background-clip: padding-box;
			background-color: pink;
			height: 400px;
			width:400px;
			background-image: url(https://c-ssl.duitang.com/uploads/item/201710/15/20171015094202_BHwPK.thumb.1000_0.jpeg  );
			background-size: cover;

		}
	</style>
</head>
<body>
	 <div class="container">
	 	<div>hello</div>
	 </div
```

#### 多图背景

```html
	<style type="text/css">
		.container{
			border: dashed 5px black;
			padding: 30px;
			background-clip: padding-box;
			background-color: pink;
			height: 800px;
			width:800px;
			background-image: url(https://c-ssl.duitang.com/uploads/item/201710/15/20171015094202_BHwPK.thumb.1000_0.jpeg  ),url(https://ss2.bdstatic.com/70cFvnSh_Q1YnxGkpoWK1HF6hhy/it/u=3184040087,2141402221&fm=26&gp=0.jpg);
			background-repeat: no-repeat,repeat-x;
			background-position: top left ,center;
			background-size: 100px 100px, auto ;
		}
	</style>
</head>
<body>
	 <div class="container">
	 	<div>hello</div>
	 </div>
</body>
```

#### 颜色渐变

##### 线性渐变

属性：background-image:*Linear Gradients*属性

举例1：顶部渐变

```css
background-image: linear-gradient(direction, color-stop1, color-stop2, ...);
/*默认是从顶部开始线性渐变*/
```

举例2：左到右渐变

```css
#grad {
  height: 200px;
  background-image: linear-gradient(to right, red , yellow);
}
/*从左边开始的线性渐变，起点是红色，过渡到蓝色*/
```

举例3：对角

```css
#grad {
  height: 200px;
  background-image: linear-gradient(to bottom right, red, yellow);
}
/* 从左上角开始（到右下角）的线性渐变。起点是红色，慢慢过渡到黄色*/
```

举例4：使用角度

```css
background-image: linear-gradient(angle, color-stop1, color-stop2);
```

![](https://www.runoob.com/wp-content/uploads/2014/07/7B0CC41A-86DC-4E1B-8A69-A410E6764B91.jpg)

举例5：使用多个节点渐变

```css
#grad {
  background-image: linear-gradient(red, yellow, green);
}
#grad {
  /* 标准的语法 */
  background-image: linear-gradient(to right, red,orange,yellow,green,blue,indigo,violet);
}
```

举例6：使用透明度

```css
#grad {
  background-image: linear-gradient(to right, rgba(255,0,0,0), rgba(255,0,0,1));
}

/*从左到右的线性渐变，带有透明度*/
```

##### 重复性渐变

repeating-linear-gradient() 函数用于重复线性渐变

```css
#grad {
  /* 标准的语法 */
  background-image: repeating-linear-gradient(red, yellow 10%, green 20%);
}
```

##### 径向渐变

属性：background-image: radial-gradient属性

* 径向渐变由它的中心定义

* 渐变的中心是 center（表示在中心点），渐变的形状是 ellipse（表示椭圆形），渐变的大小是 farthest-corner（表示到最远的角落）。

```css
background-image: radial-gradient(shape size at position, start-color, ..., last-color);
 background-image: radial-gradient(at center, yellow, green);
}
/* 使用at 确定圆心位置*/
```

举例：颜色结点

```css
#grad {/*颜色结点均匀分布*/
  background-image: radial-gradient(red, yellow, green);
}
#grad {/*颜色结点不均匀分布*/
  background-image: radial-gradient(red 5%, yellow 15%, green 60%);
}
```

举例2：设置形状

shape 参数定义了形状。它可以是值 circle 或 ellipse。其中，circle 表示圆形，ellipse 表示椭圆形。默认值是 ellipse。

也可以设置像素决定半径，一般成对出现

```css
#grad {
  background-image: radial-gradient(circle, red, yellow, green);
}
#grad {
  background-image: radial-gradient( 100px 200px, red, yellow, green);
}
```

举例3：重复径向渐变

```css
#grad {
  background-image: repeating-radial-gradient(red, yellow 10%, green 15%);
}
```

##### 渐变中点

指渐变的中心位置

在两个颜色之间加百分比

```css
background: linear-gradiernt(90deg,yellow,20%,blue)
```



##### 色标

























