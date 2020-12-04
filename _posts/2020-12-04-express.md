---
title: express项目创建
date: "2020-12-04T22:26:03.284Z"
description: ""
categories: [express]
comments: true
---

###### 1. 创建项目：

- 新建项目文件夹
- 打开cmd；cd到项目文件夹里
- 自动初始化指令：npm init -y
- 导入express框架并保存在package.json中：> npm install --save express(npm i -S express)

- 在项目文件夹中创建视图views文件夹和静态资源public文件夹；创建app.js

- 接下来配置`art-template`模板引擎：

  - 在项目文件夹下安装：> (c)npm i -S art-template express-art-template

  - 配置：

    ```javascript
    //第一个参数配置视图的后缀名，默认是art，可以改成html
    app.engine('html', require('express-art-template'))
    ```

- 在app.js写入代码：

  ```javascript
  var express = require('express')
  
  var app = express()
  
  app.engine('html', require('express-art-template'))
  
  app.get('/', function(req, res){
      res.render('index.html')
  })
  
  app.listen(3000, function(){
      console.log('running 3000...')
  })
  ```

- 控制台> nodemon app.js；打开浏览器进入http://localhost:3000/看响应

- 配置静态文件路由：

  ```javascript
  //第一个参数是路由前缀，第二个参数是静态文件路径
  app.use('/public/', express.static('./public'))
  ```

- （bootstrap上找一个示例网站cv网页源代码到index.html（别忘了npm网页需要的包并修改包路径，个别样式可以直接带你链接进去cv到本地/public/css中））

