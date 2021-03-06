# 涂鸦智能iOS SDK

---

## 功能概述

涂鸦智能APP SDK提供了与硬件设备、涂鸦云通讯的接口封装，加速应用开发过程，主要包括了以下功能：

- 硬件设备相关（配网、控制、状态上报、定时任务、群组、固件升级、共享）
- 账户体系（手机号、邮箱的注册、登录、重置密码等通用的账户功能）
- 家庭体系 （家庭管理，房间管理等功能）
- 涂鸦云HTTP API接口封装 (参见[涂鸦云api调用](https://docs.tuya.com/cn/cloudapi/appAPI/index.html))

## 快速集成

### 使用Cocoapods集成

在`Podfile`文件中添加以下内容：

```ruby
platform :ios, '8.0'

target 'your_target_name' do

   pod "TuyaSmartHomeKit", :git => "https://github.com/TuyaInc/tuyasmart_home_ios_sdk.git"

end
```

然后在项目根目录下执行`pod update`命令，集成第三方库。

CocoaPods的使用请参考：[CocoaPods Guides](https://guides.cocoapods.org/)

## 初始化SDK

在项目的`PrefixHeader.pch`文件添加以下内容：

```objc
#import <TuyaSmartHomeKit/TuyaSmartKit.h>
```

打开`AppDelegate.m`文件，在`[AppDelegate application:didFinishLaunchingWithOptions:]`方法中初始化SDK：

```objc
[[TuyaSmartSDK sharedInstance] startWithAppKey:<#your_app_key#> secretKey:<#your_secret_key#>];
```

至此，准备工作已经全部完毕，可以开始App开发啦。

### Debug 模式

在开发的过程中可以开启 Debug 模式，打印一些日志用于分析问题。

```
#ifdef DEBUG
    [[TuyaSmartSDK sharedInstance] setDebugMode:YES];
#else
#endif
```



