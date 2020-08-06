---
title: 结构体与类（Structures and Classes）
description: 结构体与类的基本概念、用法、选择
---
## 定义 
```swift
struct Resolution {
    var width = 0
    var height = 0
}
class VideoMode {
    var resolution = Resolution()
    var interlaced = false
    var frameRate = 0.0
    var name: String?
}
```
## 初始化
```swift
let someResolution1 = Resolution()
let someResolution2 = Resolution(width: 640, height: 480) // 结构体默认生成全成员（memberwise）初始化方法
let someVideoMode = VideoMode()
```
## 属性访问
```swift
someVideoMode.resolution.width = 1280
print("The width of someVideoMode is now \(someVideoMode.resolution.width)")
// Prints "The width of someVideoMode is now 1280"
```

## 相同点
* 定义属性
* 定义方法
* 支持角标语法（subscript syntax）
* 支持初始化方法（initializers）
* 支持扩展（Extensions）
* 支持协议（Protocols）

## 类的额外特点
* 支持继承和类型转化（Type Casting）
* 支持反初始化（Deinitialization）
* 支持ARC

## 值类型与引用类型
* 结构体是值类型
```swift
// before
let hd = Resolution(width: 1920, height: 1080)
// after
var cinema = hd
cinema.width = 2048
```
![](https://docs.swift.org/swift-book/_images/sharedStateStruct_2x.png)

* 类是引用类型
```swift
// before
let tenEighty = VideoMode()
tenEighty.resolution = hd
tenEighty.interlaced = true
tenEighty.name = "1080i"
tenEighty.frameRate = 25.0
// after
let alsoTenEighty = tenEighty
alsoTenEighty.frameRate = 30.0
```
![](https://docs.swift.org/swift-book/_images/sharedStateClass_2x.png)

## 结构体和类的选择
* 默认使用结构体
* 涉及到与OC的引用时使用类
* 当涉及到继承时候，优先考虑使用结构和协议方式实现
* 单例设计使用类




