# Frontend Mentor - QR code component solution

This is a solution to the [QR code component challenge on Frontend Mentor](https://www.frontendmentor.io/challenges/qr-code-component-iux_sIO_H). Frontend Mentor challenges help you improve your coding skills by building realistic projects. 

## Table of contents

- [Overview](#overview)
  - [Screenshot](#screenshot)
  - [Links](#links)
- [My process](#my-process)
  - [Built with](#built-with)
  - [What I learned](#what-i-learned)
  - [Continued development](#continued-development)
  - [Useful resources](#useful-resources)
- [Author](#author)
- [Acknowledgments](#acknowledgments)

**Note: Delete this note and update the table of contents based on what sections you keep.**

## Overview

### Screenshot

![](C:\Users\11857\AppData\Roaming\marktext\images\2025-01-03-00-14-35-image.png)



### Links

- Solution URL: [GitHub - VickTan/VickTan.github.io: QR code component](https://github.com/VickTan/VickTan.github.io.git)
- Live Site URL: https://vicktan.github.io/

## My processhttps://github.com/VickTan/VickTan.github.io.git

### Built with

- Semantic HTML5 markup
- CSS custom properties
- Flexbox

### What I learned

1. 了解盒模型以及Content、Padding、Border、Margin属性，知道如何控制组件与组件间的间隔

2. 了解了display属性，了解可以通过display属性来控制元素是block元素还是inline元素。或者通过display属性来指定父容器的布局是什么？flex、grid等等！！

3. 了解了flex布局，用于控制元素的排列和对齐



#### 盒模型(Box Model)

CSS显式的所有内容哦个都是一个方框，即使只是一些文本。或者可以通过设置`border-radius`属性使其看起来像一个圆形

##### 盒模型的组成

![](C:\Users\11857\AppData\Roaming\marktext\images\2025-01-02-23-36-48-image.png)

盒模型由以下四部分组成的。

- **内容区域（Content）**：
  
  - 这是元素的实际内容部分，例如文字、图片或其他 HTML 元素。
  - 内容区域的尺寸由 `width`（宽度）和 `height`（高度）属性定义。

- **内边距（Padding）**：
  
  - 内边距是内容区域和元素边框之间的空白区域。
  - 内边距的大小可以通过 `padding` 属性来控制，增大内边距会增加内容区域与边框之间的距离。
  - **内边距会影响元素的实际宽度和高度**。（可以通过改变盒模型为边框盒模型，就不会影响元素得实际宽度和高度)

- **边框（Border）**：
  
  - 边框围绕着内边距和内容区域。它的宽度、样式和颜色可以通过 `border` 属性来设置。
  - **边框占用额外的空间，会影响元素的总尺寸**。（可以通过改变盒模型为边框盒模型，就不会影响元素得实际宽度和高度）

- **外边距（Margin）**：
  
  - 外边距是元素的边框和其他元素之间的空白区域。
  - 外边距的大小通过 `margin` 属性控制，外边距不会影响元素的尺寸，只会改变元素的位置和与其他元素之间的距离。



##### 常见的盒模型类型

一边上通过指定`box-sizing`属性来指定使用的是什么盒模型,如指定div元素为边框盒模型

```css
div{
    box-sizing:border-box;
}
```



###### 标准盒模型（Content-box）（默认盒模型）

- 在标准盒模型中，width和height只设置**内容区域的尺寸**，不包括内边距、边框和外边距

- 元素的实际宽度和高度会受到**内边距**和**边框**的影响。

例如：如果设置了div元素的宽度为200px，那么width只指内容区域的宽度，内边距和边框的宽度会加到元素的总宽度上：

```css
div {
  width: 200px;
  padding: 10px;
  border: 5px solid black;
}
```

上面例子中的div元素宽度会是200px+10px（左内边框）+10px（右内边框）+5px（左边框）+5px（右边框）！！！！

###### 

###### 边框盒模型（Border-box）

- 在边框模型中，width和height设置的尺寸是包括了内边距和边框的。这意味这设置的width和height值已经包含了内边距和边框的尺寸，元素的实际宽度不会增加。

- 这种模型常用于布局设计，尤其是在需要精确控制元素尺寸时。

例如：

```css
div {
    width: 200px;
    padding: 10px;
    border: 5px solid black;
    box-sizing: border-box;
}
```

在上面的css代码中，div的实际宽度就是200px，内边距和边框的宽度已经包含在内了。因此，div的内容区域（Content）的宽度会变小，实际的内容区域的宽度是：

`200px - 10px(左内边距) - 10px(右内边距) - 5px(左边框)-5px(右边框)`，即170px



###### box-sizing 属性

CSS的box-sizing属性控制盒模型的计算方式，它





##### Padding(内边距)

Padding是指元素内容与边框之间的距离，控制的是元素的内部分隔；**增加了元素内部的空间**，使得内容不会紧贴着边框显式，从而改善视觉效果和可读性

###### 内边距的特性

- **内边距影响元素的尺寸**：增加内边距会增大元素的总尺寸。例如，一个div元素的宽度是100px，内边距为20px，元素的实际宽度就变为140px（包括内容区域和内边距）

- **增加可读性和美观性**：通过内边距，元素内的内容不会紧贴着边框，增加空间感和视觉舒适度。

- **内边距继承元素的背景颜色或背景图像**：padding是内部空间，意味着它位于元素的边框和内容之间。这个内边框的区域会继承元素的背景颜色或背景图像。



###### 注意事项

当元素设置了`Overflow`属性的时候，显示的滚动条会占用内边距的空间。也就是说，滚动条（水平和垂直滚动条）会出现在内边距区域内，覆盖一部分内边距的空间。

`Overflow`属性控制元素内容溢出容器的行为。当元素的内容溢出其边框时，`overflow`属性决定如何显示溢出的内容，常见的值为：

- `overflow: auto` : 如果内容溢出，浏览器会自动显示滚动条

- `overflow: scroll `: 无论是否有内容溢出，始终显示滚动条。



```html
<div class="qr-code-class">
      <img src="./images/image-qr-code.png" alt="qr-code" id="qr-code-01"/>
      <div class="qr-code-text">
        <p class="qr-code-sub-01">Improve your front-end skills by building projects</p>
        <p class="qr-code-sub-02">Scan the QR code to visit Frontend Mentor and take your coding skills to the next level</p>
      </div>
    </div>
```

```css
.qr-code-class{
    width: 288px; 
    height: 443px;
    background-color: white;
    padding-top: 16px;
    padding-right: 16px;
    padding-left: 16px;
    padding-bottom: 40px;
    margin: 0 auto;
    border-radius: 20px;
}
```

此代码中，左、右、上边距设置为20px；下边距设置为40px。也就是为元素内部添加32的左右内边距、56的上下内边距。 **同时也会增加指定div元素的实际宽度、高度**。宽度从288 变成320；高度从443变成499！！！！！



###### Padding属性的语法

padding属性是一个简写属性，可以接受1到4个值，分别用于设置四个方向的内边距

```css
padding: <top> <right> <bottom> <left>;
```

- **1个值**：所有四个方向的内边距相同。
  
  ```css
  padding: 20px; /* 四个方向的内边距都为 20px */
  ```

- **2个值**：第一个值用于设置上下方向的内边距，第二个值用于设置左右方向的内边距。
  
  ```css
  padding: 20px 10px; /* 上下内边距为 20px，左右内边距为 10px */
  ```
  
  

- **3个值**：第一个值用于设置上方向的内边距，第二个值用于设置左右方向的内边距，第三个值用于设置下方向的内边距。
  
  ```css
  padding: 20px 10px 30px; /* 上边距 20px，左右边距 10px，下边距 30px */
  ```

- **4个值**：分别用于设置上、右、下、左方向的内边距（顺时针方向）。
  
  ```css
  padding: 20px 10px 30px 40px; /* 上边距 20px，右边距 10px，下边距 30px，左边距 40px */
  ```



除了通过pading属性来设置各个方向的内边距外，还可以通过以下属性分别设置各个方向的内边距:

- padding-top

- padding-right

- padding-bottom

- padding-left

##### 

##### border(边框)



- border围绕着Padding，其空间由边框值定义。

- boeder为元素创建了一个视觉框架，为元素提供了一个清晰的外观框架，通常用于突出显示元素或为其提供一定的层次感。例如，按钮、卡片、输入框等通常都会有一个边框

- boeder是由边框定义的区域，它确定了元素的外部边界。元素的边框线就是你看到的边界，可以帮组你明确元素的视觉限制。



###### 边框的组成

一个元素的边框由三个主要属性组成

- border-width : 设置边框的宽度，定义边框的粗细。可以接受以下值：
  
  - 长度值（如px，em，rem等）
  
  - 可以指定不同方向的边框值
    
    - border-top-width
    
    - border-right-width
    
    - border-bottom-width
    
    - border-left-width

- border-style : 设置边框的样式，定义了边框的外观，常见的样式有：
  
  - none ： 无边框
  
  - solid  ： 实线边框
  
  - dashed：虚线边框
  
  - dotted：点状边框
  
  - double：双线边框

- border-color：设置边框的颜色，可以使用常见的颜色值（`#ff0000`、`rgb(255, 0, 0)` 等）。它控制边框的颜色。



除了分开指定这三个属性外，还可以综合指定这三个属性。使用border属性即可

CSS提供了border的简写形式，允许开发者在一个声明中同时设置边框的宽度、样式和颜色。

每个属性之间通过空格分隔开

```css
border: 2px solid red;
border: 2px solid rgba(0,0,0,0.5);
```

这行代码表示：

- **2px** 是边框宽度。
- **solid** 是边框样式。
- **red** 是边框颜色。





###### 设置单独边框（每个方向）

可以单独控制元素的各个方向的边框，如上、下、左、右边框

```css
/* 设置顶部边框 */
border-top: 2px solid black;

/* 设置右边框 */
border-right: 3px dashed blue;

/* 设置底部边框 */
border-bottom: 1px dotted green;

/* 设置左边框 */
border-left: 4px double red;

```



###### 影响布局的行为：

- **占用空间**：边框会影响元素的布局，它会增加元素的总占用空间，尤其是当 `box-sizing` 为 `content-box` 时，边框会被加到元素的宽度和高度之上，增加了该元素的实际占用面积。

- **溢出处理**：如果元素内容超出了边框的空间，且设置了 `overflow` 属性（例如 `overflow: hidden`、`overflow: auto`），则会依据该属性来处理溢出的内容。滚动条会出现在**边框内边距区域**或**边框区域中**。



##### Margin（外边距）

- margin（外边距）是指元素与其他元素之间的空白区域，位于边框区域（border）外面。

- margin主要用于控制元素之间的距离和间隔，不会影响元素的内容、内边距或边框的大小，但会影响元素的位置和布局
  
   

###### margin的作用

- **调整元素间距**：margin的主要作用是调整元素之间的距离。可以精确控制一个元素与其他元素之间的空白区域，帮助构建清晰的布局。

- **避免重叠**：当相邻的两个元素的margin重叠时，浏览器会根据特定规则来合并这些margin，以避免内容的重叠或出现不必要的空白区域

- **影响元素的位置**: margin会影响元素在页面中的布局和位置。通过调整margin，可以控制元素在其父容器中的相对位置。例如，通过设置`margin:auto`, 可以将元素居中



###### margin的语法

margin是一个简写属性，可以接受1到4个值，分别用于设置四个方向的外边距。

```css
margin: <top> <right> <bottom> <left>;
```

- **1个值**：所有四个方向的外边距相同。
  
  ```css
  margin: 20px; /* 四个方向的外边距都为 20px */
  ```

- **2个值**：第一个值用于设置上下方向的外边距，第二个值用于设置左右方向的外边距。
  
  ```css
  margin: 20px 10px; /* 上下外边距 20px，左右外边距 10px */
  ```

- **3个值**：第一个值用于设置上方向的外边距，第二个值用于设置左右方向的外边距，第三个值用于设置下方向的外边距。
  
  ```css
  margin: 20px 10px 30px; /* 上边距 20px，左右边距 10px，下边距 30px */
  ```

- **4个值**：分别用于设置上、右、下、左方向的外边距（顺时针方向）。
  
  ```css
  margin: 20px 10px 30px 40px; /* 上边距 20px，右边距 10px，下边距 30px，左边距 40px */
  
  ```



###### margin 与 position属性

后续再补充





###### margin 与 auto属性

后续再补充



###### margin 与 outline属性

后续再补充



###### margin与box-shadow属性

后续再补充









#### display 属性、inline元素、block元素

display属性是用来指定元素如何在页面上显式的。它可以控制元素的布局行为，包括元素是否表现为行内元素（inline）或块级元素（block），以及如何影响其他元素的排列

**display属性一般可以用来，改变元素的性质** 。例如将inline元素变成block元素,如

```html
display: inline-block;  
display: block; 
```

**也可以使用display属性，指定该容器的布局**，如：

```html
display:flex;
```

通过上面语句设置了display属性后，该容器使用的就是flex布局，该容器内的元素就会按照flex布局进行布局！！！！

### 行内元素（Inline）

行内元素不会强行换行，会与周围的元素在同一行内显式，通常用于在文本中嵌入小的内容。

常见的行内元素有：

- <span>
- <a>
- <strong>
- <em>    



除了使用行内元素外，我们还可以通过指定元素的display属性为inline，来使得元素变为行内元素

当连续使用多个行内元素的时候，不会一个元素占据一行。他们会在同一行显式，知道占满整个父容器的宽度才会换行。例如：

```csharp
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    <span>这是为了测试行内元素</span>
    <a>a 元素是inline元素哦！</a>
    <strong>strong 元素也是inline元素哦！！！！</strong>
    <em>em也是inline元素</em>
    <a>好多好多的行内元素，这是第5行了</a>
</body>
</html>
```

![image.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/b3594d76-f981-428c-a471-cfca62835955/13dacd63-579e-4f70-a8e5-3d41e562600f/image.png)

**行内元素的特点**

- 并排显示：多个行内元素会并排显示，知道一行空间不足，然后自动换行
- 不占据完整宽度：行内元素的宽度由其内容决定的，无法显示设置宽度
- 不会破坏页面的布局流：行内元素不会让其他元素移到下一行，它们会尽量和其他行内元素共享一行空间。
- 保留周围的空白字符：行内元素会保留它们前后的空白字符（比如空格、换行等），并按原样呈现。

**行内元素的限制**：

- **行内元素不能设置宽度和高度（width、height）**
  
  行内元素的大小是由其内容决定的，因此无法像块级元素那样显式地设置其宽度和高度。即使你为一个行内元素设置了 `width` 和 `height`，它们也不会生效。这是因为行内元素的大小是自适应的，通常会根据其内容（如文本或其他内联元素）来扩展，而不会占据额外的空间。
  
  如果真的想为行内元素设置宽度和高度，可以通过指定display属性来解决：将它们转换为块级元素（`display: block;` 或 `display: inline-block;`），这允许你为元素设置宽度和高度。

- **行内元素的上下外边距（margin-top、margin-bottom）和内边距对布局(padding-top、padding-bottom)不起作用**
  
  行内元素的 `margin-top` 和 `margin-bottom` （即上下外边距）以及 `padding-top` 和 `padding-bottom` （即上下内边距）通常对布局不起作用。也就是说，行内元素的上下外边距不会影响到周围的其他元素的排列或间距。
  
  行内元素的 `margin-left` 和 `margin-right` 仍然有效，它们会在水平方向上产生空白，但 **上下方向的外边距和内边距将被忽略**，这是行内元素的一个限制。
  
  **解决办法**：如果你需要设置行内元素的垂直外边距或内边距，可以将其转换为 `inline-block` 或 `block` 元素。

### 块内元素（block元素）

block元素会占据一整行，通常用于构建页面的结构区域。block元素会自动开始新的一行并占据父容器的整个宽度。

常见的块内元素有：

- div
- p
- h1-h6
- ul、ol
- form
- section、article、aside、nav
- header、footer

**块级元素的特点**：

- **占据整行宽度**：
  - 块级元素会自动占据父元素容器的整个可用宽度，除非你设置了其宽度。
  - 例如：`<div>`, `<p>`, `<h1>`, `<ul>` 等默认就是块级元素，它们会将后续的元素推到新的一行。
- **可以设置宽高**：
  - 块级元素的宽度和高度是可设置的，并且通常是基于父容器的宽度进行渲染。
  - 例如：你可以给 `<div>` 元素指定 `width` 和 `height`，它会遵循这些尺寸来布局。
- **外边距和内边距会生效**：
  - 块级元素的外边距（margin）和内边距（padding）会正常影响布局，尤其是外边距会推动元素周围其他元素的位置。
  - **块级元素的上下外边距会发生“合并”现象**，即相邻两个块级元素的外边距会合并为一个（通常是较大的那个）。
- **在页面中生成新行**：
  - 每个块级元素都会在其前后创建一个“断行”，即后续的元素会被推到下方。它不会与其他块级元素在同一行内显示，除非你明确指定它们在同一行内。
- **可以包含其他块级元素和内联元素**：
  - 块级元素可以包含其他块级元素或内联元素。比如你可以在一个 `<div>` 内放置另一个 `<div>` 或 `<p>`，同时也可以放置 `<span>` 或 `<a>` 等内联元素。





## Flex布局

Flexbox（弹性布局）是一个CSS布局模块，旨在提供一种更有效的方式来分配空间并对齐内容，尤其是当布局需要动态调整时。它使得在一个容器中对子元素的排列、对齐和分配空间变得更加简单，特别是在响应式设计中。

flexbox的基本思想是，容器中的项目（元素）可以灵活地适应容器的尺寸（通常是父容器）。它的工作原理是通过设置容器为display:flex 来激活弹性布局，使得容器中得子元素可以根据指定得规则自动调整尺寸、对齐方式和排列方式。

## 关键属性

### 容器相关属性

这些属性设置在父容器上，控制子元素的布局行为：

- **`display: flex;`**
  
  激活弹性布局。在父元素上应用此属性后，所有直接子元素将变成“弹性项目”。

- **`flex-direction`**
  
  定义弹性项目的排列方向。默认值是 `row`，表示水平排列（从左到右）。
  
  - `row`：水平排列，默认值。
  - `row-reverse`：水平排列，反向。
  - `column`：垂直排列。
  - `column-reverse`：垂直排列，反向。

- **`flex-wrap`**
  
  控制弹性项目是否换行。默认情况下，所有弹性项目都被压缩到一行中。
  
  - `nowrap`：不换行（默认）。
  - `wrap`：允许换行。
  - `wrap-reverse`：允许换行，并反转换行的顺序。

- **`justify-content`**
  
  控制弹性项目在主轴（水平或垂直方向）上的对齐方式。主要用于空间分配。
  
  - `flex-start`：默认，项目靠主轴的起始位置对齐。
  - `flex-end`：项目靠主轴的结束位置对齐。
  - `center`：项目居中对齐。
  - `space-between`：项目之间的间隔相等，第一项靠起始位置，最后一项靠结束位置。
  - `space-around`：项目之间的间隔相等，项目两端的间隔为 `space-between` 的一半。
  - `space-evenly`：项目之间的间隔相等，两端的间隔也相等。

- **`align-items`**
  
  控制弹性项目在交叉轴（垂直方向）上的对齐方式。
  
  - `stretch`：默认，项目拉伸以填充容器。
  - `flex-start`：项目与交叉轴的起始位置对齐。
  - `flex-end`：项目与交叉轴的结束位置对齐。
  - `center`：项目居中对齐。
  - `baseline`：项目的基线对齐。

- **`align-content`**
  
  控制多行的对齐方式（当 `flex-wrap: wrap;` 时）。它与 `align-items` 类似，但影响的是多行容器的对齐。
  
  - `flex-start`：容器的起始位置对齐。
  - `flex-end`：容器的结束位置对齐。
  - `center`：容器居中对齐。
  - `space-between`：多行之间的间隔相等。
  - `space-around`：多行之间的间隔相等，且两端的间隔为 `space-between` 的一半。
  - `stretch`：多行被拉伸以填充容器。

### 子元素相关属性

这些属性控制每个弹性项目（子元素）的行为。

- **`flex-grow`**
  
  指定弹性项目如何放大以填充容器剩余的空间。默认值是 `0`，表示项目不会放大。
  
  - `flex-grow: 1;` 表示该项目会占用剩余空间。

- **`flex-shrink`**
  
  指定弹性项目如何缩小以适应容器。如果容器空间不足，项目会缩小。默认值是 `1`，表示项目会缩小。
  
  - `flex-shrink: 0;` 表示该项目不会缩小。

- **`flex-basis`**
  
  指定弹性项目的初始主轴尺寸（即在分配空间之前的尺寸）。可以设置为 `auto`（默认）或者一个具体的像素值。
  
  - `flex-basis: 100px;` 让项目的初始宽度为 100px。

- **`flex`**
  
  是 `flex-grow`, `flex-shrink` 和 `flex-basis` 的简写。通常用于设置项目的伸展和收缩行为。
  
  - `flex: 1;` 等同于 `flex-grow: 1; flex-shrink: 1; flex-basis: 0;`，意味着该项目会占用容器的剩余空间。
  - `flex: 0 1 100px;` 表示项目的初始宽度为 `100px`，并允许其收缩，但不放大。

- **`align-self`**
  
  控制单个弹性项目在交叉轴上的对齐方式，覆盖 `align-items` 对该项的影响。
  
  - `auto`：使用父容器的 `align-items` 对齐方式。
  - `flex-start`：对齐到交叉轴的起始位置。
  - `flex-end`：对齐到交叉轴的结束位置。
  - `center`：对齐到交叉轴的中心。
  - `baseline`：对齐到项目的基线。
  - `stretch`：拉伸以填充容器。

# 第三方布局

常用的第三方布局有：

- Bootstrap：[https://getbootstrap.com/](https://getbootstrap.com/)
- Foundation
- Tailwind CSS
- Materialize
- Bulma



### Continued development

- 后续可以尝试使用第三方布局来控制页面布局

- 进一步了解各种布局

- 需要进一步了解一下margin与position的关系

### Useful resources

- [CSS Padding 和 Margin 全解析_css padding margin-CSDN博客](https://blog.csdn.net/licy__/article/details/144238039) - 该博客让我对于Padding和Margin属性有了更深的了解
- [Box Model](https://web.dev/learn/css/box-model?continue=https://web.dev/learn/css&hl=zh-cn#article-https://web.dev/learn/css/box-model&hl=zh-cn)-该文章使得对CSS的Box Model有更深的理解



## Author



## Acknowledgments
