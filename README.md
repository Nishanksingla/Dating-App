Facebook-login-with-Phonegap
============================
For Successful login you need 2 things.

1.) Settings in facebook app developer.

	create facebook app for android platform
        set package name--> com.[phonegap package name](found in config file in "id" field)
       ([note: if you have "com." in your name then you don't need to add com. in the beginning]) 
     
       set Default Activity Class Name-->  com.[phonegap package name].MainActivity
       
       create key hashes--  
     
        1.) create keystore file using this link [https://github.com/amirudin/build/wiki/Android-Signing]
        
        2.) Then you need key hashes. To generate this hash key, first you need to install OpenSSL tool on windows.
        
            if you are generating this hash on Windows (specifically 64 bit versions), please use version 0.9.8e or 0.9.8d of OpenSSL for Windows and not 0.9.8k.
            
            You can download it from here https://code.google.com/p/openssl-for-windows/downloads/list
            
            using this command to generate hash key 
            
            keytool -exportcert -alias [alias name] -keystore [keystore location] | "C:\openssl\bin\openssl.exe" sha1 -binary | "C:\openssl\bin\openssl.exe" base64
            
      Then copy the key printed at terminal and paste it on Facebook APP config section (Android > Key Hashes)
      
2.)Then you need to set config file.

	Now you need to add phonegap facebook plugin in your config.xml file (https://build.phonegap.com/plugins/257).
	Fill the value of your app id and app name.
		<gap:plugin name="com.phonegap.plugins.facebookconnect">
		     <param name="APP_ID" value="737970306223941" />
		     <param name="APP_NAME" value="nishanktestapp" />
		 </gap:plugin>
        
	    [Note: when you will add this plugin and build it using adobe phonegap build it will automatically add 
	    facebook js sdk file in your app( you don't have to include fb sdk js file by yourself in your project)
	    Thr following javascript files will be included in your app automatically. 
	    	<script src="cordova.js"></script>
		    <!-- cordova facebook plugin -->
		<script src="cdv-plugin-fb-connect.js"></script>
		    <!-- facebook js sdk -->
		<script src="facebook-js-sdk.js"></script>
		You have to add these script tags in your index.html flie to use them
		]
		
	Now just use the Index.html file in my folder
	
For any Problem..ask me.. happy to help :)
