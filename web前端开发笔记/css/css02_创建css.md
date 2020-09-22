# css笔记02--创建css样式

## 一、样式表

插入样式表的方法有三种

### 1.1外部样式表

使用link标签连接到样式表<link>标签在文档的头部

文件不包含任何HTML的标签，标签样式以.css扩展名保存

```css
<head>
<link rel="stylesheet" type="text/css" href="mystyle.css" />
</head>
```

### 1.2 内部样式表

使用style标签在文档头部定义样式表

```css
<head>
<style type="text/css">
  hr {color: sienna;}
  p {margin-left: 20px;}
  body {background-image: url("images/back40.gif");}
</style>
</head>
```

### 1.3内联样式表

使用style属性，在标签内部定义css属性

```css
<p style="color: sienna; margin-left: 20px">
This is a paragraph
</p>
```

ps:属性和值都需要用双引号括起来，每一个属性都需要分号做分隔

最好不要用内联样式，是一种打补丁式写法。有点丑还没优势。:smile:

### 1.4样式的优先级

1. ​	内联样式>内部样式>链接样式>默认样式
2. 如果相同属性的样式表定义不同属性值，则不同属性值会被优先级高的样式继承:sweat_smile:就是组合吧
3. 如果相同属性的样式表定义相同的属性值，则会被优先级高的样式覆盖

***



## 二、css背景

| 描述     | 属性                  | 备注                                                         |
| -------- | :-------------------- | ------------------------------------------------------------ |
| 背景色   | background-color：    | 该属性不能被继承（所有背景属性都不能被继承）                 |
| 背景图像 | background-image：    | 默认无图像，设置时必须设置URL放置相对路径                    |
| 背景重复 | background-repeat：   | repeat-x在水平方向重复，repeat-y在竖直方向上重复，no-repeat不允许图像在任何方向上重铺 |
| 背景定位 | background-position： | 关键字：top、bottom、left、right 和 center。可成对出现，可以使用长度值，如 100px 或 5cm，可以使用百分数值。 |
|          |                       |                                                              |
|          |                       |                                                              |











