---
layout: post
title: nodemailer使用方法
description: Nodemailer是Node.js应用程序的一个模块，可以方便地发送蛋糕电子邮件。该项目于2010年开始，当时没有理智的选择发送电子邮件，今天，这是大多数Node.js用户默认情况下的解决方案。
category: coding
---


### 一、Nodemailer使用方法

1. 安装 nodemailer  

```
npm install nodemailer --save
```  

### 二、调用  

```
var nodemailer = require("nodemailer");
// 开启一个 SMTP 连接池
var smtpTransport = nodemailer.createTransport("SMTP",{
  host: "smtp.qq.com", // 主机
  secureConnection: true, // 使用 SSL
  port: 465, // SMTP 端口
  auth: {
    user: "xxxxxxxx@qq.com", // 账号
    pass: "xxxxxxxx" // 密码
  }
});
// 设置邮件内容
var mailOptions = {
  from: "Fred Foo <xxxxxxxx@qq.com>", // 发件地址
  to: "2838890xx@qq.com, minimixx@126.com", // 收件列表
  subject: "Hello world", // 标题
  html: "<b>thanks a for visiting!</b> 世界，你好！" // html 内容
}
// 发送邮件
smtpTransport.sendMail(mailOptions, function(error, response){
  if(error){
    console.log(error);
  }else{
    console.log("Message sent: " + response.message);
  }
  smtpTransport.close(); // 如果没用，关闭连接池
});
```
