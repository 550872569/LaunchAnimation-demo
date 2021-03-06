[![Build Status](https://travis-ci.org/Kejiasir/LaunchAnimation-demo.svg?branch=master)](https://travis-ci.org/Kejiasir/LaunchAnimation-demo)
[![CocoaPods](https://img.shields.io/cocoapods/v/LaunchAnimation.svg)](http://cocoadocs.org/docsets/LaunchAnimation)
[![CocoaPods](https://img.shields.io/cocoapods/p/LaunchAnimation.svg)](http://cocoadocs.org/docsets/LaunchAnimation)
[![CocoaPods](https://img.shields.io/cocoapods/l/LaunchAnimation.svg)](https://raw.githubusercontent.com/kejiasir/LaunchAnimation/master/LICENSE)

## 这是什么鬼?
*  这是一个简单的启动图动画.
*  动画执行时间提供参数可以自行调整. 
*  您只需要一句代码就能使启动图开启一个动画效果.
*  暂时有三种效果, 提供一个枚举可任意选择, 后续再增加一些其他的效果.
*  哈哈, 话说之前写过这个Demo [一个裁剪图片的小工具类,通过一句代码调用](http://www.cnblogs.com/arvin-sir/p/5094445.html), 当时是不知道如何获取应用的启动图的, 现在呢, 知道了O(∩_∩)O哈哈哈~, 所以就写了这个简单的依赖库, 核心代码都是一样一样的, 写的不好希望大家多多鼓励多多包涵...


### 0824更新, 版本: 0.2.0
* 新增了三种动画效果, 具体请看示例图片
* 同样是枚举, 可以任意选择使用您想要的效果
* 感觉后面两种有点bug, 如果有大神的话请指点下
```Objective-C
// 设置为NO(默认)的话, LaunchImageView 会被强引用导致内存无法释放
// 如果是设置为YES, 内存可以释放, LaunchImageView 会调用 dealloc 方法, 但是结束会'闪'一下
[positionAnima setRemovedOnCompletion:YES];
```


##  要怎么集成?
### 手动添加:<br>
*   1. Clone or download 本项目
*   2. 将Demo中的 `LaunchAnimaiton` 文件夹Copy到您的工程目录中<br> 

### CocoaPods:<br>
*   1. 在 Podfile 中添加 `pod 'LaunchAnimaiton', '~> 0.2.0'`<br>
*   2. 在终端执行 `pod install` 或 `pod update` 命令<br> 

## 它如何使用?
*  如您所见, 一句代码(两种方式初始化) :
*  在 `AppDelegate.m` 文件中 `import "LaunchImageView.h"` 头文件即可
```Objective-C
// 切记:在添加前必须先设置window的视图可见并显示
// 即调用:[self.window makeKeyAndVisible],否则不会展示动画效果
// 方式一: 类方法
[self.window addSubview:[LaunchImageView
                             launchImageWithFrame:self.window.bounds
                             animationType:AnimationTypeUpAndDown
                             duration:1.5f]];
// 方式二: 实例方法
[self.window addSubview:[[LaunchImageView alloc]
                             initWithFrame:self.window.bounds
                             animationType:AnimationTypeUpAndDown
                             duration:1.5f]];
```

## 另外需要注意的<br>
**请把启动图片放在项目的 `Assets.xcassets` 文件中, 应当从Brand Assets中加载**

<img src="IMAGE/img_000.png?v=3&s=100" alt="GitHub" title="启动图片应当从Brand Assets中加载" width="780" height="220"/>

### 嗯, 最后放几张图吧(模拟器录的gif有点卡, 使用真机测过没问题)

<table>
 <tr>
  <td>
    <img src="IMAGE/001.gif" width="300"/>
  </td>
  <td>
    <img src="IMAGE/002.gif" width="300"/>
  </td>
  <td>
    <img src="IMAGE/003.gif" width="300"/>
  </td>
 </tr>
 <tr>
  <td>
    <img src="IMAGE/004.gif" width="300"/>
  </td>
  <td>
    <img src="IMAGE/005.gif" width="300"/>
  </td>
  <td>
    <img src="IMAGE/006.gif" width="300"/>
  </td>
 </tr>
 </table>
 

##License
**LaunchAnimaiton 使用 MIT 许可证，详情见 LICENSE 文件**
