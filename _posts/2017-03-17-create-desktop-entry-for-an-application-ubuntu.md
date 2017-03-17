---
layout: post
title:  "Create desktop entry for an application in Ubuntu"
date:   2017-03-17 21:00:00 +0700
categories: [Ubuntu, Android Studio]
tags: [installing, desktop entry]
---

I just installed Android Studio 2.3 in my Ubuntu computer. Everything is fine. But there is a little problem that there is no an icon for it.
So today, I want to share with you how I create an desktop entry for an application, such as: Android Studio. 

### Step 1: Create file <yourfilename>.desktop (androidstudio.desktop)

  ```
  sudo nano /usr/share/applications/androidstudio.desktop
  ```
  
### Step 2: Write below:

  ```
  [Desktop Entry]
  Version=2.3
  Type=Application
  Terminal=false
  Icon[en_US]=/home/lampv/Documents/android-studio/bin/studio.png
  Name[en_US]=Android Studio
  Exec=/home/lampv/Documents/android-studio/bin/studio.sh
  Name=Android Studio
  Icon=/home/lampv/Documents/android-studio/bin/studio.png
  ```
  
  * /home/lampv/Documents/android-studio/bin/studio.png : path for the icon
  * /home/lampv/Documents/android-studio/bin/studio.sh : path for the script to execute the application.
  * ...
  For now, everything is alright.

### Step 3: (Optional) Set permissions

  ```
  sudo chmod 644 /usr/share/applications/androidstudio.desktop
  sudo chown root:root /usr/share/applications/androidstudio.desktop
  ```
  
It is easy, right? If you have some questions, feel free to ask me!
 
 Sincere,
 Pham Van Lam
