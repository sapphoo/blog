# px、em、rem,其实很简单
>合理运用px、em、rem影响font-size、padding、margin，可以让你事半功倍。

---
划重点（敲黑板~~）
* px--固定
* em-相对于父级元素的font-size
    * **注意**：本元素的font-size大小会影响到本元素以em为单位的一切属性值(width height padding border margin...)
* rem（css3）--root em，相对于html节点（根）的font-size大小
---
## 0. px
px--pixel。相对长度单位。相对于显示器屏幕分辨率而言。


## 1. em
### em的便利之处
首先要知道的一点是，任何浏览器在未经css调整的情况下都默认

1em == 16px

通常，为了简化运算，我们可以在css的body选择器种声明font-size:62.5%,这样就会使1em == 16px*62.5% == 10px

```css
body{font-size: 62.5%;} /*1em = 10px;*/
section{font-size：4em;} 
h1{font-size: 1em;}/*1em = 40px;*/
h2{font-size: 0.5em;}
@media(max-width: 800px){
    body{
        font-size: 100%;
    }
}/*在手机端显示，字体为100%，相比px定义省略了很多代码*/

```
效果图

![](em.PNG "桌面浏览器")

h1为40px，h2为20px

![](em_media.PNG "手机端")

h1为64px，h2为32px

### 你需要知道的em的影响
虽然em很好用，但是有时用em又会出现问题，如下面的例子。
```css
body{font-size: 62.5%;} /*1em = 10px;*/
section{font-size：4em;} 
h1{font-size: 1em;}/*1em = 40px;*/
h2{font-size: 0.5em; padding: 1em 0 0;}

```
效果图

![](em_padding.PNG)

可以看到h2的上内边距与h2等高，为20px，为什么不是40px？

这是因为本元素的所有以em为单位的属性值(width height padding border margin...)

## 2.rem
rem和em的区别就是，rem是不会受父级元素和本元素的font-size影响的，永远都是
相对于html节点的font-size值
```css
html{font-size: 62.5%;} /*1em = 10px;*/
section{font-size：4em;} 
h1{font-size: 1em;}/*1em = 40px;*/
h2{font-size: 0.5em; padding: 1rem 0 0;}
```
效果图
![](rem_padding.PNG)

这里的h2的上内边距就变成了10px，而非上面em例子中的20px

