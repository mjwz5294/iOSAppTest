# iOSAppTest
## [简书主页]( https://www.jianshu.com/u/b37773b21ff3)

## 这是一个用于iOSApp测试的NodeJSWeb项目

## iOS通itms-services://协议安装ipa，省去https环境的搭建

## 原理
使用Apple的itms-services://协议,在IOS7.1系统以后，如果要使用企业证书(299美元)通过itms-services在线安装ipa的话必须走https协议，**其实需要https协议访问的只是manifest.plist文件的地址**如:`itms-services://?action=download-manifest&url=https://appInfo/manifest.plist`，
但是 `ipa的下载不需要走https协议也是可以的`。

因此我们就建立一个web项目可以不用支持https，然后把我们的项目提交的[GitHub](https://github.com/)（GitHub是https协议的或者其他https网站如[码云](https://gitee.com/)等）仓库，然后获取到manifest.plist文件的地址替换为
上面plist文件的地址。最后，启动我门本地的服务访问下载页面即可。



补充文档：https://blog.csdn.net/xlyrh/article/details/79078271，主要解决访问不到github.com的问题




使用说明：
1、IP设为192.168.1.220:8081
2、ipa名称修改为hello_world.jpa
3、将ipa放到www目录中
4、node http_server