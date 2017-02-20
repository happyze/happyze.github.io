---
layout: post
title: box-sizing
description: box-sizing 属性允许您以特定的方式定义匹配某个区域的特定元素。
category: coding
---


### css3 box-sizing属性  

box-sizing属性可以为三个值之一：content-box（default），border-box，padding-box。
content-box，border和padding不计算入width之内
padding-box，padding计算入width内
border-box，border和padding计算入width之内，其实就是怪异模式了~  
ie8+浏览器支持content-box和border-box；
ff则支持全部三个值。

##### 使用时:  

```
-webkit-box-sizing: 100px; // for ios-safari, android

-moz-box-sizing:100px; //for ff

box-sizing:100px; //for other
```  

例子  

```
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta http-equiv="X-UA-Compatible" content="ie=edge">
  <title>Document</title>
  <style media="screen">
    .content-box{
        box-sizing:content-box;
        -moz-box-sizing:content-box;
        width: 100px;
        height: 100px;
        padding: 20px;
        border: 5px solid #E6A43F;
        background: blue;
    }
    .border-box{
        box-sizing:border-box;
        -moz-box-sizing:border-box;
        width: 100px;
        height: 100px;
        padding: 20px;
        border: 5px solid #3DA3EF;
        background: yellow;
    }
  </style>
</head>
<body>
  <div class="box">
    <div class="content-box"></div>
    <div class="border-box"></div>
  </div>
</body>
</html>
```
