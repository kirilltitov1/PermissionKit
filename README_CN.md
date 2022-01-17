
# PermissionKit
Permission Manager

![Swift](https://img.shields.io/badge/Swift-5.0-orange.svg)


## 特性

- [x] 相机.
- [x] 相册.
- [x] 联系人.
- [x] 日历.
- [x] 提醒.
- [x] 媒体库.
- [x] 麦克风.
- [x] Siri.
- [x] 动作.
- [x] 语音.
- [x] 定位.
- [x] 通知.
- [x] 应用广告追踪.
- [x] 蓝牙.

## 安装

**CocoaPods - Podfile**

```ruby
source 'https://github.com/lixiang1994/Specs'

// 完整
pod 'PermissionKit'

// 单独添加所需
pod 'PermissionKit/Camera'
pod 'PermissionKit/Photos'
pod 'PermissionKit/Contacts'
pod 'PermissionKit/Event'
pod 'PermissionKit/Motion'
pod 'PermissionKit/Speech'
pod 'PermissionKit/Media'
pod 'PermissionKit/Siri'
pod 'PermissionKit/Location'
pod 'PermissionKit/Notification'
pod 'PermissionKit/Tracking'
pod 'PermissionKit/Bluetooth'
```

**Carthage - Cartfile**

```ruby
github "lixiang1994/PermissionKit"
```

## 使用

首先导入:

```swift
import PermissionKit
```

下面是一些简单示例. 支持所有设备和模拟器:

### 属性
```swift
Provider.camera.isAuthorized

Provider.photos.isAuthorized

Provider.XXXXXX.isAuthorized
```

### 方法
```swift
Provider.camera.request { (result) in
    print("isAuthorized: \(result)")
}

Provider.XXXXXX.request { (result) in
    print("isAuthorized: \(result)")
}
```

### Alert

#### 协议
```swift
public protocol PermissionAlertable {

    init(_ source: PermissionAlertContentSource)

    func show(_ status: AlertStatus, with сompletion: @escaping (Bool) -> Void)
}
```
#### 系统Alert 基于 `UIAlertController`
```
let alert = SystemAlert(ChineseAlertContent())
Provider.camera.request(alert) { result in
    /* ... */
}
```
自定义Alert需要实现 `PermissionAlertable` 协议


## 贡献

如果你需要实现特定功能或遇到错误，请打开issue。 如果你自己扩展了 PermissionKit 的功能并希望其他人也使用它，请提交拉取请求。


## 协议

PermissionKit 使用 MIT 协议. 有关更多信息，请参阅 [LICENSE](LICENSE) 文件.
