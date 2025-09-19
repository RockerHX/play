PixelExtended for clover XiaoMiPad4/plus

# 简介

PixelExtended 是一款基于 PixelExperience 的开源定制 ROM，完美融合了 Google 生态与精选优化功能。

Core features 核心特性:

* 原汁原味的 Pixel 体验

* Google服务 GoogleServe

* 性能优化

    1.在保持系统纯净的同时提供：

    2.增强的系统稳定性

    3.改进的安全防护机制

    4.精心挑选的实用功能补充


* 源码信息
  
    安卓版本：13

    建造者：Traveler Lynn

    设备来源 ： GitHub - Travelerext/android_device_xiaomi_clover

    供应商来源： GitHub - Travelerext/android_vendor_xiaomi_clover

    内核来源：GitHub - Travelerext/android_kernel_xiaomi_sdm660

    源代码：PixelExtended ROM
    Pixel扩展开发者：Aryan Gupta

* 其他

    屏幕超频到### 72hz

    CPU超频小核

    APatch（超级密钥：SDM660）

    KernelSU（不工作）

    系统优化


# 刷机

> 我的刷机宗旨，尽量不使用按键刷机，全是使用命令行，如果有不懂的命令，自行问AI或者搜索按钮的方式

## 命令解释

[刷机命令解释](./Command.md)

## 刷机步骤

资料下载：[https://github.com/Hy1Fly/PixelExtended-clover/releases](https://github.com/Hy1Fly/PixelExtended-clover/releases)

### 救砖

> 以 **TWRP3.7.1.img** 为例

```zsh
## 此命令刷写recovery分区（如果变砖，刷写recovery可以并不能成功引导，可以先刷写，再用boot命令引动recovery即可）

fastboot flash recovery TWRP3.7.1.img

## 如果变砖了，开机会进入bootloader，也就是fastboot界面模式，用于引导recovery镜像，进入recovery后就能救砖了

fastboot boot TWRP3.7.1.img
```

### 刷机

> 以 **PixelExtended-5.6_clover-13.0.zip** 为例

```zsh
## 先将卡刷包推送到设备上

adb push PixelExtended-5.6_clover-13.0.zip /sdcard/Download

## 然后使用TWRP3将设备分区都清理一遍（除开内置存储和存储卡），刷机完成后格式化data分区，重启即可
adb reboot
```