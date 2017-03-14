---
layout: post
title:  "Installing nodejs and npm in Linux from binaries"
date:   2017-03-15 01:05:00 +0700
categories: [nodejs, Ubuntu, Elementary OS]
tags: [installing, binaries]
---

There are few ways to install nodejs in Linux. You can install it with:

  * Node Version Manager
  * Ubuntu Package Manager
  * Maintained Ubuntu Packages
  * Standard Binary Packages
  
Today, I am going to introduce you how to install Nodejs with Standard Binary Packages. There are some steps below:

  * Download Nodejs from main page, such as [node-v6.10.0-linux-x64.tar.xz](https://nodejs.org/dist/v6.10.0/node-v6.10.0-linux-x64.tar.xz)
  * Open cmd, then move to the folder contains nodejs. Assumming that folder is **Documents**
  
    ```
    cd Documents
    ```
    
  * Install nodejs binary package in **/usr/local**:
  
    ```
    tar -C /usr/local --strip-components 1 -xJf node-v6.10.0-linux-x64.tar.xz
    ```
    
  * Check with:
  
    ```
    node --version
    npm version
    ```
    
 Now, you have installed Nodejs in Linux (Ubuntu) from Standard Binary Packages. If you have some questions, feel free to ask me!
 
 Sincere,
 Pham Van Lam
