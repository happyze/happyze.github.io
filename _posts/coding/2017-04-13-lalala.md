---
layout: post
title: sendcloud和nodemailer的配合使用
description:  SendCloud由搜狐武汉研发中心孵化的项目，是致力于为开发者提供高质量的触发邮件服务的云端邮件发送平台，为开发者提供便利的API接口来调用服务，让邮件准确迅速到达用户收件箱并获得强大的追踪数据。
category: coding
---

### sendcloud和nodemailer的配合使用  

注册sendcloud   

1. 打开[sendcloud](https://sendcloud.sohu.com/)  

2. 注册登陆  

3. 在欢迎页面里找到API_USER,API_KEY这两项  

nodemailer代码展示  

```
const nodemailer = require('nodemailer');

const transporter = nodemailer.createTransport({
  host: "smtpcloud.sohu.com",
  port: 25,
  auth: {
    user: 'API_USER',
    pass: 'API_KEY'

  }
  });
  const mailOptions = {
    from: '', // 发送者
    to: '', // 接受者,可以同时发送多个,以逗号隔开
    subject: , // 标题
    html: ''//文章连接
  };
  return transporter.sendMail(mailOptions, function (err, info) {
    if (err) {
      console.log(err);
      return;
    }
    console.log('发送成功');
  });
```
## 赶快发邮件喽!!!
