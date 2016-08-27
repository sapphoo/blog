# px、em、rem,其实很简单
>合理运用px、em、rem影响font-size、padding、margin，可以让你事半功倍。

* px--固定
* em-相对于父级元素的font-size
    * **注意**：本节点的font-size大小会影响到本节点以em为单位的一切属性值(width height padding border margin...)
* rem（css3）--root em，相对于html节点（根）的font-size大小

## 0. px
px--pixel。相对长度单位。相对于显示器屏幕分辨率而言。

ie无法调整那些使用px作为单位的字体大小。


## 1. em
首先要知道的一点是，任何浏览器在未经css调整的情况下都默认

1em == 16px

通常，为了简化运算，我们可以在css的body选择器种声明font-size:62.5%,这样就会使1em == 16px*62.5% == 10px

```css
body{font-size: 62.5%;} /*1em = 10px;*/
section{font-size：4em;} 
h1{font-size: 1em;}/*1em = 40px;*/
h2{font-size: 0.5em;}

```
效果图

![](em.PNG)

## 2. em vs. rem