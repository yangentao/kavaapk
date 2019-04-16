解析APK文件的版本号和图标等信息   

基于这个项目 https://github.com/hsiafan/apk-parser 修改.   
去掉了签名和dex相关代码    
ApkFile 不再需要调用close()   
-----------
`val dir = File("/Users/entaoyang/Downloads/")`  
`val f = File(dir, "a.apk")`   
`println(f.exists())`   
`val apkFile = ApkFile(f)`   
`println(apkFile.apkMeta)`   
`println(apkFile.manifestXml)`   
`val icon = apkFile.appIcon192 ?: return`   
`val fd = File(dir, "192.png")`   
`fd.writeBytes(icon.data!!)`   

输出:   
packageName: 	dev.entao.bath   
label: 	XXXX   
icon: 	res/mipmap-mdpi-v4/app.png   
versionName: 	1.98   
versionCode: 	98   
minSdkVersion: 	21   
targetSdkVersion: 	27   
maxSdkVersion: 	null   

 