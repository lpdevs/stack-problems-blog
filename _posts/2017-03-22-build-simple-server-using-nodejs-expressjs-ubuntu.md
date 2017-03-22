---
layout: post
title:  "Build a simple http server in Ubuntu using Nodejs and ExpressJs"
date:   2017-03-22 23:00:00 +0700
categories: [Ubuntu, Nodejs, Expressjs]
tags: [http server]
---

Today, I am going to talk about how to build a simple http server in ubuntu using Nodejs and Expressjs. 
If you have not installed Nodejs, please install it or check [this](https://lpdevs.github.io/nodejs/ubuntu/elementary%20os/2017/03/14/installing-nodejs-and-npm-in-linux-from-binaries.html).
By now, I am assumming that you have installed Nodejs. Let's start now:
  
  * Create new project:
  
    ```
    npm init
    ```
    then just hit Enter...After that **package.json** file is generated. (Notice: Name can no longer contain capital letters).

  * Install **express** module: open Terminal, then:
  
    ```
    npm install --save express
    ```
    using **--save** to save it as a dependency in the **package.json** file. Then **node_modules** is generated.
    
  * Create a new file: **index.js**, write the code like below:
    
    ``` 
    var express = require('express');

    var app = express();
    var port = process.env.port || 8080;

    app.listen(port, function(){
	     console.log('The server is listening on port:' + port);
    });
    ```
    
    This code will create a server which is bound with **localhost** in port **8080**.
    
  * Start this server:
  
    ```
    node index.js
    ```
    If the console displays log as **The server is listening on port: 8080**, then the server is started successfully.
    
    then navigate to [http://localhost:8080](http://localhost:8080). For now, you will receive an error, which is **Cannot GET /**.
    It is because we are never implementing routing for the server.
    
  * Routing by adding the below in **index.js**:
  
    ```
    app.get('/', function(req, res){
	    res.send('Hello from main page');
    });
    ```
    
    * That means when you navigate to the [http://localhost:8080](http://localhost:8080), you requested to get '/'. Then the server
      responses by sending **Hello from main page** to your browser. So starting the server again, then navigate to [http://localhost:8080](http://localhost:8080).
      You will receive that message.
    
    * For now, you just can access the server from your computer. Because the server is bound with **localhost**. If you want to access the server from other computers in the same network. You must bind it with your **ip address**. So **index.js** must be modified like below:
    
      ``` 
      var express = require('express');

      var app = express();
      var port = process.env.port || 8080;
      var host = '<your_ip>'; // change it with your ip

      app.get('/', function(req, res){
	      res.send('Hello from main page');
      });

      app.listen(port, host, function(){
	      console.log('The server is listening on port:' + port + ' and host:' + host);
      });
      ```
      
      Start the server again, then navigate to [http://<your_ip>:8080. 
      
 OK, it is just simple way to create a server on Ubuntu using Nodejs and Expressjs. If you want to create more complicated server or have some questions, feel free to ask me. I am really happy to help you.
 
 LP Devs.
  
    
    
