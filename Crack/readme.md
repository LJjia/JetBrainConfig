注意!!!!
这个文件不要随意移动,因为涉及CLion的破解,因此移动此文件或者更改上层目录结构将导致Clion打不开

如果迫不得已还是改了,修改`/Users/ljjia/Library/Preferences/CLion2018.3/clion.vmoptions`

如果是window系统,则是在对应的安装路径中`C:\software\Jetbrain\CLion 2018.3.4\bin\clion64.exe.vmoptions`

# 2018.3系列破解方法

使用pycharm2018.3.7和clion2018.3.4 安装在window上

首先要修改host文件,window中在`C:\Windows\System32\drivers\etc\hosts`

```shell
0.0.0.0 www.jetbrains.com
0.0.0.0 account.jetbrains.com
```

测试使用`JetbrainsIdesCrack-4.2.jar`这一个文件就可以,不过window上需要修改安装包bin目录下的`*vmoptions`和打开软件进入`Help->Edit Custom VM Option`产生的`*vmoptions`文件.注意pycharm分32位和64位,两个都要改

末尾添加

```shell
-javaagent:C:/software/Jetbrain/JetBrainConfig/Crack/JetbrainsIdesCrack-4.2.jar
```

加完后,重启软件

然后输入下面的注册码

```json
ThisCrackLicenseId-{
“licenseId”:”11011”,
“licenseeName”:”xxt”,
“assigneeName”:”xxtalhr”,
“assigneeEmail”:”87605025@qq.com”,
“licenseRestriction”:””,
“checkConcurrentUse”:false,
“products”:[
{“code”:”II”,”paidUpTo”:”2099-12-31”},
{“code”:”DM”,”paidUpTo”:”2099-12-31”},
{“code”:”AC”,”paidUpTo”:”2099-12-31”},
{“code”:”RS0”,”paidUpTo”:”2099-12-31”},
{“code”:”WS”,”paidUpTo”:”2099-12-31”},
{“code”:”DPN”,”paidUpTo”:”2099-12-31”},
{“code”:”RC”,”paidUpTo”:”2099-12-31”},
{“code”:”PS”,”paidUpTo”:”2099-12-31”},
{“code”:”DC”,”paidUpTo”:”2099-12-31”},
{“code”:”RM”,”paidUpTo”:”2099-12-31”},
{“code”:”CL”,”paidUpTo”:”2099-12-31”},
{“code”:”PC”,”paidUpTo”:”2099-12-31”}
],
“hash”:”2911276/0”,
“gracePeriodDays”:7,
“autoProlongated”:false}
```





对应文件的散列值为

```shell
~/CCppCode/dataStruct  md5 /Users/ljjia/CCppCode/ClionConfig/Crack/JetbrainsIdesCrack-4.2.jar
MD5 (/Users/ljjia/CCppCode/ClionConfig/Crack/JetbrainsIdesCrack-4.2.jar) = a577fe434dcf668222505d75eb4a9b58

$ md5sum JetbrainsCrack-release-enc.jar
a577fe434dcf668222505d75eb4a9b58 *JetbrainsCrack-release-enc.jar

```



 
