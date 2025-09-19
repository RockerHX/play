# 命令解释

fastboot: 引导或者刷写img

* fastboot boot [arg]
* fastboot flash [arg]
* fastboot reboot [arg]

adb: 操作设备（需要进入recovery或者开机打开调试模式）

* adb install [arg]
* adb push [arg]
* adb pull [arg]
* adb reboot [arg]

## fastboot 

### boot

```zsh
## 如果变砖了，开机会进入bootloader，也就是fastboot界面模式，用于引导recovery镜像，进入recovery后就能救砖了

fastboot boot *.img
```

### flash

> fastboot flash recovery

```zsh
## 此命令刷写recovery分区（如果变砖，刷写recovery可以并不能成功引导，可以先刷写，再用boot命令引动recovery即可）

fastboot flash recovery *.img
```

> fastboot flash boot

```zsh
## 此命令刷写boot分区（用于mgisk或者apatch破解boot分区后刷入使用）

fastboot flash boot *.img
```

### reboot

```zsh
## 重启到bootloader

fastboot reboot bootloader
## 重启到recovery分区

fastboot reboot recovery

## 重启到system

fastboot reboot system
```

## adb 

### install

```zsh
## 安装应用

adb install *.apk
```

### push

```zsh
## 推送文件到设备上

adb push *.* /sdcard/Download
```

### pull

```zsh
## 拉取问津到本地

adb pull *.* ～/Desktop
```

### reboot

```zsh
## 重启到recovery分区，用于刷入卡刷包

adb reboot recovery

## 重启到bootloader，也就是fastboot，用于救砖

adb reboot bootloader
```