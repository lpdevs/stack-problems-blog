---
layout: post
title:  "Request permissions by java in Android version 23+"
date:   2017-02-25 17:30:00 +0700
categories: [java, android]
tags: [permissions]
---

In android with version >= 23, you need to request some permissions
in java code. To register some permissions, follow these steps:

  * **Step 1**: Declare variables
  
    ```java
	private List<String> permissions;
	private static final int REQUEST_PERMISSION_RESULT = 0xFF;
	```

  * **Step 2**: Implement **CheckPermission()** function

    ```java
	private boolean CheckPermission() {
		permissions = new ArrayList<String>();
		if (Build.VERSION.SDK_INT >= 23) {
			int hasPermission;
			hasPermission = checkSelfPermission(Manifest.permission.CAMERA);
			if (hasPermission != PackageManager.PERMISSION_GRANTED)
				permissions.add(Manifest.permission.CAMERA);

			hasPermission = checkSelfPermission(Manifest.permission.RECORD_AUDIO);
			if (hasPermission != PackageManager.PERMISSION_GRANTED)
				permissions.add(Manifest.permission.RECORD_AUDIO);
		}
		if (permissions.isEmpty()) return true;
		return false;
	}
	```
	
  * **Step 3**: Request permissions 
	
    ```
	if (!CheckPermission()){
      if (Build.VERSION.SDK_INT >= 23){
		requestPermissions( permissions.toArray(new String[permissions.size()]), REQUEST_PERMISSION_RESULT );
      }
    }
	```
	
If you have some questions, feel free to ask me.

Pham Van Lam.
