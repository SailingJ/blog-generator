---
title: CSS基本布局
date: 2019-04-22 16:20:00
tags:
---
## 1.左右布局
左右布局可以通过float来实现
``` 
    <div class="clearfix">
      <div style="float:left">左边<div>
      <div style="float:right">右边<div>
    </div>
```
其中clearfix如下，ps（::after为伪元素，相当于一个div）
```
.clearfix::after{
    content: '';
    display: block;
    clear: both;
}
```
## 2.左中右布局
如上，但要将float统一为left，通过调节margin来布局位置。

## 3.水平居中
块级元素占据布局的一整行，内联元素则可以多个布局在同一行内，两者均由文档流决定其大小。
<img src="./水平布局.PNG" alt="水平布局">
例如区域的红色部分，则是一个div元素，单纯在CSS中写入tac(text-align: center)，仅能将div中的文字居中

而下区域的绿色部分，则是由1个div里面包裹着3个div
红色的小div则是写入disploy：inline-block（将块级元素转化为内联元素，本人理解为将块看作文字这一类）
绿色的大div只要写入tac 就可以将里面的红色div居中。

## 4.垂直居中
本人暂时尝试出一个方法，就是在一个使布局部分脱离文档流 top:50%;
```
<div class="area">
    <div class="content">垂直居中</div> 
</div>
```
css部分
```
.area{
    position: relative;
}
.content{
    position: absolute;
    top:50%;
}
```
## 5.其他小技巧
### （1）按钮下阴影
<img src="./按钮阴影.PNG" alt="按钮阴影">
搜索CSS shadow generate （css阴影生成）
```
.buttom:hover {
    box-shadow: 0px 4px 10px 0px rgba(0,0,0,0.2);
    transition: 0.3s;
```

### （2）导航栏中部空隙
<img src="./中间空隙.png" alt="中间空隙">
首先将用float实现左右布局，(目标：中部空隙)，先将每一LAN适当缩小，本次选用48%
```
li{
    width: 48%;
    float: left;
    box-sizing: border-box;
}
```
然后，如果能够仅仅将右侧li都有margin-left的话，可实现中间空隙,可以采取伪类
```
li:nth-child(even){
    margin-left：4%;
```
或者直接float：right也是可以的

### （3）导航栏
<img src="./导航栏.PNG" alt="导航栏">
首先，先做出分别点击后的结果状态（css）,留意：.Bar.status1 中间并没有空格，表示既满足Bar又满足status1(其中123为不同的状态)

```
.portfolioNav .Bar.status1 .portfolioBar-inner  {
    width: 35px;
    margin-left:0px;
}
.portfolioNav .Bar.status2 .portfolioBar-inner {
    width: 45px;
    margin-left:50px;
}

.portfolioNav .Bar.status3 .portfolioBar-inner {
    width: 100px;
    margin-left:100px;
}
```

然后，在div下方写入script（js），代码可见，点击了对应的区域后，将nav的class更改，即改成status（123），通过改class的名字进行选择

```
    <div class="portfolio">
      <h2>作品集</h2>
      <nav class="portfolioNav">
        <ol class="clearfix">
          <li id="portfolioAll">所有</li>
          <li id="portfolioFramework">框架</li>
          <li id="portfolioVallina">原生JS&amp;CSS</li>
        </ol>
        <div id="portfolioBar" class="Bar status1">
          <div class="portfolioBar-inner"></div>
        </div>
      </nav>
    <script>
      portfolioAll.onclick=function(){
        portfolioBar.className="Bar status1"
      }
      portfolioFramework.onclick=function(){
        portfolioBar.className="Bar status2"
      }
      portfolioVallina.onclick=function(){
        portfolioBar.className="Bar status3"
      }
    </script>
    </div>
```
