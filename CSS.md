# CSS是什么



# 语法

![](C:\Users\demo\Desktop\frontend\CSS.assets\img_selector.gif)

# selector分类

## 元素选择器

```
p {
  text-align: center;
  color: red;
}
```

## id选择器

```
#para1 {
  text-align: center;
  color: red;
}
```

## class选择器

class名字不能以数字开头。

```
.center {
  text-align: center;
  color: red;
}
```

```
p.center {
  text-align: center;
  color: red;
}
```

## 全体选择器

```
* {
  text-align: center;
  color: blue;
}
```

## grouping选择器

```
h1, h2, p {
  text-align: center;
  color: red;
}
```

# CSS位置

Inline优先级最高。

## Inline

```
<h1 style="color:blue;text-align:center;">This is a heading</h1>
```

## External CSS

放在head中，link引用文件。

```
<!DOCTYPE html>
<html>
<head>
<link rel="stylesheet" href="mystyle.css">
</head>
<body>

<h1>This is a heading</h1>
<p>This is a paragraph.</p>

</body>
</html>
```

## Internal CSS

放在head中，style引入。

```
<!DOCTYPE html>
<html>
<head>
<style>
body {
  background-color: linen;
}

h1 {
  color: maroon;
  margin-left: 40px;
}
</style>
</head>
<body>

<h1>This is a heading</h1>
<p>This is a paragraph.</p>

</body>
</html>
```

# 颜色表示

## RGB

## HEX

## HSL

字体颜色：`color`

```
<h1 style="color:Tomato;">Hello World</h1>
```



背景颜色：`background-color`

```
<h1 style="background-color:DodgerBlue;">Hello World</h1>
```



边框颜色：`border`

```
<h1 style="border:2px solid Tomato;">Hello World</h1>
```

# CSS Box模型

![image-20241021142506792](C:\Users\demo\Desktop\frontend\CSS.assets\image-20241021142506792.png)

