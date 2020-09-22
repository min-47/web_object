





# 设置字体

* font-family:属性，定义文本字样
* css选择器  属性顺序是从左往右
* 元素顺序是从左往右

```css
h1{font-family: Georgia, serif}
```

ps:可声明多种字体，依次往右。

#### 引用外部字体文件

```html
@font-face{
    font-family:"别名";
    src: url(路径);
}
```

#### 设置字体倾斜

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Document</title>
    <style type="text/css">
        p.normal{font-style: normal;}//文本正常显示
        p.italic{font-style: italic;}//文本斜体显示
        p.oblique{font-style: oblique;}//文本倾斜显示
    </style>
</head>
<body>
    <p class="normal">我倾斜了吗。没有</p>
    <p class="italic">我倾斜了吗。有的</p>
    <p class="oblique">我倾斜了吗。有的</p>
    
</body>
</html>
```

#### 字体加粗

font-weight属性，设置文本粗细

* 使用bold 关键字==400
* 关键字100~900是九级粗度。100最细，900最粗。

```css
p.normal{font-style: normal;font font-weight: 400;} p.italic{font-style: italic;font-weight: 100;}
p.oblique{font-style: oblique;font-weight: 900;}
```

#### 字体大小

 font-size属性

* px使用像素
* em  相对于父类元素大小 1em相当于100%

```css
p{font-size:14px;}
p{font-size: 2em;}
```

#### 组合设置

font属性，设置组合字体样式，**必须设置字体和大小**

:exclamation:字体规则声明写在最后

:exclamation:font顺序：斜体  粗体  字号/行高   字体   **不可改变**

```html
 p { font: bold italic 40px Georgia;  }        
```

# html颜色

有三种方法定义css中的颜色值

#### 预定义/跨浏览器颜色名

html和css颜色规范定义147种颜色名（17种标准颜色和130种其他颜色）

```css
p{color: red;}
```

#### 十六进制色

* 所有浏览器都支持
* 规定：#RRGGBB，其中RR（红色）GG（绿色）BB（绿色）值定义：00~FF
* #ff0000值显示为红色。因为红色设置为ff最高值，其他成分设置为0

```css
p{color:#ff0000;}
```

#### RGB颜色

* 所有浏览器都支持三原色（红绿蓝）
* 规定：rgb（red，green，blue）每个参数值在0~255之间（255,255,255）
* 百分比（0%，0%，0%）**不推荐**

```css
p{color:rgb(0,0,255);}
```

#### RGBA颜色

* rgba(red,green,blue,alpha)
* alpha通道，规定了对象的不透明度
* 参数结余0.0~1.0之间
* **透明色如果有背景，可以透出背景图**

```css
p{color:rgba(0,0,255,0.5);}
```

####  全透明

 关键字 transparent

```css
p{color:transparent;}
```



#### html单位

| 单位   | 描述                                               |
| ------ | -------------------------------------------------- |
| **%**  | 百分比                                             |
| in     | 英寸                                               |
| cm     | 厘米 不推荐使用                                    |
| mm     | 毫米 不推荐使用                                    |
| **em** | 1em等于当前字体的尺寸                              |
| ex     | 一个ex等于一个字体的x-height（是指字体尺寸的一半） |
| pt     | 磅                                                 |
| pc     | 12点活字（等于12个点）                             |
| **px** | 像素（屏幕上一个点）                               |

# 大小写转换

text-transform属性处理文本的大小写

* none(默认值)
* lowercase(全大写)
* capitalze(首字母大写)

```html

<head>
	<meta charset="UTF-8">
	<title>Document</title>
	<style type="text/css">
		p.uppercase{text-transform:uppercase;}
		p.lowercase{text-transform: lowercase;}
		p.captialize{text-transform: capitalize;}
	</style>
</head>
<body>
	<p class="uppercase" >this is some text in a paragraph</p>
	<p class="lowercase">this is some text in a paragraph</p>
	<p class="capitalize">this is some text in a paragraph</p>
	
</body>

```

# 文本线条

text-decoration有5个值

* none  (无)
* underline （下划线）
* overline  （上划线）
* line-through  （中间线） 
* blink 

```html
<head>
	<meta charset="UTF-8">
	<title>Document</title>
	<style type="text/css">
		.a1{text-decoration: none;}
		.a2{text-decoration: underline;}
		.a3{text-decoration: overline;}
		.a4{text-decoration: line-through;}
		.a5{text-decoration: blink;}//不支持
		.a6{text-decoration: underline overline;}

	</style>
</head>
<body>
		<a href="" class="a1"> this is a1</a>
		<a href="" class="a2"> this is a2</a>
		<a href="" class="a3"> this is a3</a>
		<a href="" class="a4"> this is a4</a>
		<a href="" class="a5"> this is a5</a>
		<a href="" class="a6"> this is a6</a>
	
</body>
```

# 文本阴影

text-shadow属性，参数顺序为：阴影颜色，水平偏移量，垂直偏移量，模糊度

```html
	<style type="text/css">
		p{
			text-shadow: rgb(0,0,255) 3px 3px 3px;
		}
	</style>
</head>
<body>
	<p>hello world </p>
</body>
```

# 空白溢出处理

#### 处理空白符

white-space属性会影响到用户对源文档中的空格，换行和tab字符的处理

| 值       | 空白符 | 换行符 | 自动换行 |
| -------- | ------ | ------ | -------- |
| pre-line | 合并   | 保留   | 允许     |
| normal   | 合并   | 忽略   | 允许     |
| nowrap   | 合并   | 忽略   | 不允许   |
| pre      | 保留   | 保留   | 不允许   |
| pre-wrap | 保留   | 保留   | 允许     |

```html
<head>
	<meta charset="UTF-8">
	<title>Document</title>
	<style type="text/css">
		p{white-space:pre-wrap;}
	</style>
</head>
<body>
	<p>	JavaScript 是世界上最流行的编程语言。                这门语言可用于 HTML 和 web，更可广泛用于服务器、PC、笔记本电脑、平板电脑和智能手机等设备   这门语言可用于 HTML 和 web，更可广泛用于服务器、PC、笔记本电脑、平板电脑和智能手机等设备 这门语言可用于 HTML 和 web，更可广泛用于服务器、PC、笔记本电脑、平板电脑和智能手机等设备</p>
</body>
```

#### 溢出

overflow属性规定当内容溢出元素框发生的事情

| 值      | 描述                                                         |
| ------- | ------------------------------------------------------------ |
| visible | 默认值，内容不会被修剪，会呈现在元素框外                     |
| hidden  | 内容会被修剪，并且其余内容是不可见的                         |
| scroll  | 如果内容被修剪，则浏览器会显示滚动条以便查看其余的内容//下滚动条和侧滚动条 |
| auto    | 如果内容被修剪，则浏览器会显示滚动条以便查看其余的内容//只有下滚动条 |
| inherit | 规定应该从 父元素继承overflow属性的值                        |

```html
	<style type="text/css">
		p{white-space:pre-wrap;
		  border: solid 1px red;
		  width: 100px;
		  overflow: auto;}

	</style>
</head>
<body>
	<p>	JavaScript 是世界上最流行的编程语言。                这门语言可用于 HTML 和 web，更可广泛用于服务器、PC、笔记本电脑、平板电脑和智能手机等设备</p>
</body>
```

# 对齐与缩进

***

#### 文本缩进

text-indent属性，设置首行缩进

text-indent写成像素有一个问题就缩进后比例就不是原来的了，改进的方法是采用单位em。

```html
<head>
	<meta charset="UTF-8">
	<title>Document</title>
	<style type="text/css">
		p{
		 	text-indent: 2em;
		 	font-size: 10px;  
		}

	</style>
</head>
<body>
	<p>	JavaScript 是世界上最流行的编程语言。 这门语言可用于 HTML 和 web，更可广泛用于服务器、PC、笔记本电脑、平板电脑和智能手机等设备这是段落中的一些文本。 这是段落中的一些文本。 这是段落中的一些文本。 这是段落中的一些文本。 这是段落中的一些文本。 这是段落中的一些文本。 这是段落中的一些文本。 这是段落中的一些文本。 这是段落中的一些文本。 这是段落中的一些文本。 这是段落中的一些文本。 这是段落中的一些文本。</p>
</body>
```

#### 文本属性对齐

text-align属性，只对元素中的文本有效，对元素无效

可取值：left  center  right  justify等

```html
	<style type="text/css">
	h1{text-align: left;}	
	h2{text-align: right;}
	p{text-align: justify;
	   width: 150px;
	  }
        /*这个地方两端对齐的思路很巧妙*/
	p:after{
		content:"";
		display: inline-block;
		width: 100%;
	}
	</style>
</head>
<body>
	<h1 >this is some text in a paragraph</h1>
	<h2 >this is some text in a paragraph</h2>
	<p >this is some text in a paragraph</p>
</body>	
```

#### 垂直对齐

vertical-align属性，使用满足两点 文本；inline类元素或表格单元格

| 值          | 描述                                                      |
| ----------- | --------------------------------------------------------- |
| baseline    | 默认，元素放在基准线上                                    |
| sub         | 垂直对齐文本的下标                                        |
| super       | 垂直对齐文本的上标                                        |
| top         | 把元素的顶端与行内最高元素的顶端对齐                      |
| text-top    | 把元素的顶端与父元素字体顶端对齐                          |
| middle      | 把此元素放在父元素的中部                                  |
| bottom      | 把元素的顶端与行中最低的元素的顶端对齐                    |
| text-bottom | 把元素的底端与父元素字体底端对齐                          |
| length      |                                                           |
| %           | 使用“line-height"属性的百分比值来排列此元素，允许使用负值 |
| inherit     | 规定应该从父类元素继承vertical-align属性的值              |

```html
<head>
<style type="text/css">
img.top {vertical-align:text-top}
img.bottom {vertical-align:text-bottom}
</style>
</head>

<body>

<p>
这是一幅<img class="top" border="0" src="https://www.w3school.com.cn//i/eg_cute.gif" />位于段落中的图像。
</p> 

<p>
这是一幅<img class="bottom" border="0" src="https://www.w3school.com.cn//i/eg_cute.gif" />位于段落中的图像。
</p>

</body>
```

# 行高

line-height属性：是一行文字的高度，即两行文字基线的距离

常用单位是em

```html
<head>
	<meta charset="UTF-8">
	<title>Document</title>
	<style type="text/css">
		p{
            font-size；2em；
		 line-height: 1.5em;
            /*等价于 font-size：2em/1.5;
		}

	</style>
</head>
<body>
	<p>	JavaScript 是世界上最流行的编程语言。 这门语言可用于 HTML 和 web，更可广泛用于服务器、PC、笔记本电脑、平板电脑和智能手机等设备这是段落中的一些文本。 这是段落中的一些文本。 这是段落中的一些文本。 这是段落中的一些文本。 这是段落中的一些文本。 这是段落中的一些文本。 这是段落中的一些文本。 这是段落中的一些文本。 这是段落中的一些文本。 这是段落中的一些文本。 这是段落中的一些文本。 这是段落中的一些文本。</p>
</body>
```











