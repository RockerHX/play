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

    5.72HZ刷新率

    6.集成双击开关屏幕（延缓开机键使用寿命）

* 理念

    我们坚持"少即是多"的原则：

```
严格筛选功能添加，避免功能膨胀
保持 Pixel 原生的简洁美学
只集成真正提升用户体验的优化
```


# 刷机

> 我的刷机宗旨，尽量不使用按键刷机，全是使用命令行，如果有不懂的命令，自行问AI或者搜索按钮的方式

## 命令解释

fastboot: 引导或者刷写img

* fastboot boot [arg]
* fastboot flash [arg]
* fastboot reboot [arg]

### fastboot boot

```zsh
## 如果变砖了，开机会进入bootloader，也就是fastboot界面模式，用于引导recovery镜像，进入recovery后就能救砖了

fastboot boot *.img
```

### fastboot flash

#### fastboot flash recovery

```zsh
## 此命名刷写recovery分区（如果变砖，刷写recovery可以并不能成功引导，可以先刷写，再用boot命令引动recovery即可）

fastboot flash recovery *.img
```

#### fastboot flash boot

```zsh
## 此命名刷写boot分区（用于mgisk或者apatch破解boot分区后刷入使用）

fastboot flash boot *.img
```

### fastboot reboot

```zsh

## 重启到bootloader

fastboot reboot bootloader
## 重启到recovery分区

fastboot reboot recovery

## 重启到system

fastboot reboot system
```

