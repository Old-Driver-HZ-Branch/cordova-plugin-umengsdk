# cordova-plugin-umengsdk
[![platform](https://img.shields.io/badge/platform-iOS%2FAndroid-lightgrey.svg?style=flat)](https://github.com/Old-Driver-HZ-Branch/cordova-plugin-umengsdk)
[![GitHub license](https://img.shields.io/github/license/mashape/apistatus.svg?style=flat)](https://github.com/Old-Driver-HZ-Branch/cordova-plugin-umengsdk/blob/master/LICENSE)


## 安装要求
- Cordova Version 5.0+
- Cordova-Android >= 4.0
- Cordova-iOS >= 4.0			

## 安装方式
1. ```cordova plugin add https://github.com/Old-Driver-HZ-Branch/cordova-plugin-umengsdk```            
2. cordova build

## 关于友盟SDK
本插件的大部分源码来自友盟官方的 SDK，本插件只是在此基础上面进行了小修改和整合， Android 使用了 6.1.0 的版本， iOS 使用了4.2.5，no-idfa 的版本。
由于友盟 iOS SDK 在 framework 中使用了替身，Cordova 在安装完插件以后会出现 ‘UMMobClick/MobClick.h’ file not found 问题，因此本插件采用了直接拷贝 framework 中二进制文件和头文件的方式。如果不想采用这种方式，可以通过修改 Plugin.xml  和 UMPlugin.m 中的头文件，在安装完插件以后需要重新替换一遍 UMMobClick.framework。

## 关于渠道号
在 JS 接口中，调用 init 方法的时候需要传入 App_Key 和 渠道号。 如果 iOS 不填写默认为 App Store。如果 Android 不填写,会读取 AndroidManifest application 节点中的值
```<meta-data android:name="UMENG_CHANNEL" android:value="${CHANEL_NAME}"/>```,如果都没有填写，默认渠道号为 "defualt"。

## 使用
```js
MobclickAgent.init('xxxxxxxxx');
MobclickAgent.onEvent(9527);
```
详细的 API 使用请参考 wwww 文件夹中的 Umeng.js 有里面有每个方法的使用说明

