#### 升级Xcode10 后, 项目编译时可能会出现`libstdc++.6.0.9`系列的错。
##### 原因:
 苹果早在 Xcode 8中 就废弃了libstdc++, 给了开发者两年时间过渡, 如今从Xcode 10中已不再支持. 在Build Phases > Link Binary With Libraries 中已经搜不到libstdc++的库了

#### 解决
将缺少的库加入xcode10/11的相应目录。缺失的库可以在老版xcode目录中找
> 模拟器需要的tbd： `libstdc++.6.0.9.tbd`
路径：
`/Applications/Xcode.app/Contents/Developer/Platforms/iPhoneSimulator.platform/Developer/SDKs/iPhoneSimulator.sdk/usr/lib/`

> 真机需要的tbd： `libstdc++.6.0.9.tbd`
路径：
`/Applications/Xcode.app/Contents/Developer/Platforms/iPhoneOS.platform/Developer/SDKs/iPhoneOS.sdk/usr/lib/`

> dylib : `libstdc++.6.0.9.dylib` (两个，包括快捷方式)
xcode11之前路径：
`/Applications/Xcode.app/Contents/Developer/Platforms/iPhoneOS.platform/Developer/Library/CoreSimulator/Profiles/Runtimes/iOS.simruntime/Contents/Resources/RuntimeRoot/usr/lib/`
xcode11路径：
`/Applications/Xcode.app/Contents/Developer/Platforms/iPhoneOS.platform/Library/Developer/CoreSimulator/Profiles/Runtimes/iOS.simruntime/Contents/Resources/RuntimeRoot/usr/lib`


![image.png](https://upload-images.jianshu.io/upload_images/1956050-e957a19d0bf78a42.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)



### 这里有所需要的库与打开相应路径的脚本：
链接: https://github.com/sy5075391/XcodeDeletion
![image.png](https://upload-images.jianshu.io/upload_images/1956050-8487c130477a2396.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

