
---
layout:     post
title:      5分钟带你看完 WWDC 2018
subtitle:   WWDC 2018 Keynote 全记录
date:       2018-06-05
author:     BY
header-img: img/post-bg-cook.jpg
catalog: true
tags:
    - iOS
    - WWDC
---

## asdas
```
---
layout:     post
title:      入门: 在Windows上搭建Flutter开发环境
subtitle:   Get Started: Install on Windows
date:       2018-06-29
author:     csjiabin
header-img: img/post-bg-cook.jpg
catalog: true
tags:
    - iOS
    - WWDC
---
```
# 开始:安装在Windows上

## 系统需求

> 要安装和运行Flutter，您的开发环境必须满足这些最小的需求:

  * 操作系统:Windows 7 SP1或更高版本(64位)
  * 磁盘空间:400 MB(不包括IDE/工具的磁盘空间)。
  * 工具:Flutter 取决于这些工具在您的环境中是否可用。
     * PowerShell 5.0或更新
     * Windows的Git(使用“Windows命令提示符使用Git”选项)
     > 如果Windows的Git已经安装，请确保可以从命令提示符或PowerShell运行Git命令。

## 获取Flutter SDK

  1. 下载以下安装包以获得最新的beta版本 Flutter SDK (有关其他发布渠道和旧版本，请参见[SDK archive]: https://flutter.io/sdk-archive/ 归档页面.):
    * [flutter_windows_v0.5.1-beta.zip]: https://storage.googleapis.com/flutter_infra/releases/beta/windows/flutter_windows_v0.5.1-beta.zip
  2. 提取zip文件，将包含的flutter放在flutter SDK所需的安装位置(例如)。 ** C:\src\flutter ** ;不要安装目录中的flutter ** C:\Program Files\ ** 这样需要提升权限)。.
  3. 找到该文件 ** flutter_console.bat ** 在 ** flutter ** 目录内。通过双击启动它。
> 您现在可以在Flutter控制台中运行Flutter命令了!

> 要更新Flutter的现有版本，请参阅升级[Flutter]: https://flutter.io/upgrading/。

## 更新你的路径

> 如果您希望在常规Windows命令提示符中运行Flutter命令，请执行以下步骤，向PATH环境变量添加Flutter:
  
  * 到“控制面板>用户帐户>用户帐户>更改我的环境变量”
  * 在“用户变量”下检查是否有一个名为“path”的条目:
    * 如果该条目确实存在，则添加使用flutter\bin的完整路径;作为现有值的分隔符。
    * 如果该条目不存在，则创建一个名为 ** Path ** 的新用户变量，其值为 ** flutter\bin ** 的完整路径。
> 重新启动Windows以完全应用此更改。

## Run flutter doctor

> 在Flutter控制台，运行以下命令，查看是否需要安装任何依赖项以完成安装:

  ```
    $ flutter doctor
  ```

> 此命令检查您的环境并向终端窗口显示报告。Dart SDK与Flutter绑定;不需要分别安装Dart。仔细检查输出，寻找可能需要安装的其他软件或需要执行的其他任务(以粗体文本显示)。

 > 示例：

```
[-] Android toolchain - develop for Android devices
    • Android SDK at D:\Android\sdk
    ✗ Android SDK is missing command line tools; download from https://goo.gl/XxQghQ
    • Try re-installing or updating your Android SDK,
      visit https://flutter.io/setup/#android-setup for detailed instructions.
```

> 下面的部分将描述如何执行这些任务并完成安装过程。一旦安装了任何丢失的依赖项，再次运行flutter doctor命令，以验证所有设置都是正确的。

>> ** flutter ** 工具使用谷歌分析匿名报告特性使用统计数据和基本崩溃报告。这些数据被用来帮助改进Flutter工具。分析不是在第一次运行或任何涉及 ** flutter config ** 的运行时发送的，因此您可以在发送任何数据之前选择退出分析。要禁用报告，键入 ** flutter config ** ——不分析和显示当前设置，输入 ** flutter config ** 。看到谷歌的隐私政策[www.google.com/intl/en/policies/privacy]:https://www.google.com/intl/en/policies/privacy。

## 安卓系统设置

> 注意:Flutter依赖于Android Studio的完整安装来提供Android平台的依赖项。但是，您可以在许多编辑器中编写您的Flutter应用程序;后面的步骤将讨论这个问题。

### 安装 Android Studio

  1. 下载并安装 Android Studio.
  2. 打开 Android Studio, 并通过“Android Studio安装向导”。这将安装最新的Android SDK、Android SDK平台工具和Android SDK构建工具，这些工具在开发Android时是需要的。

### 设置你的Android设备

> 要准备在Android设备上运行和测试Flutter应用程序，您需要一个运行Android 4.1 (API级别16)或更高的Android设备。

  1. 在您的设备上启用 ** 开发人员选项 ** 和 **USB调试 ** 。详细说明可在[Android文档]:https://developer.android.com/studio/debug/dev-options.html 中找到。
  2. 仅限windows:安装[谷歌USB驱动]:https://developer.android.com/studio/run/win-usb 程序
  3. 用USB数据线把手机插入电脑。如果提示您的设备，请授权您的计算机访问您的设备。
  4. 在终端中，运行flutter设备命令来验证flutter是否识别了连接的Android设备。
  
 > 默认情况下，Flutter使用您的adb工具所基于的Android SDK版本。如果您希望Flutter使用不同的Android SDK安装，则必须将ANDROID_HOME环境变量设置为该安装目录。
 
 ### 设置Android模拟器
 
  > 要准备在Android模拟器上运行和测试Flutter应用程序，请遵循以下步骤:
  
    1. 在您的机器上启用[VM加速]:https://developer.android.com/studio/run/emulator-acceleration.html。
    2. 启动 ** Android Studio>Tools>Android>AVD Manager ** ，选择 ** Create Virtual Device ** 。( ** Android ** 子菜单只在Android项目中出现。)
    3. 选择设备定义并选择 ** Next ** 。
    4. 为要模拟的Android版本选择一个或多个系统映像，然后选择 ** Next ** 。推荐使用x86或x86_64映像。
    5. 在仿真性能下，选择 ** Hardware - GLES 2.0 ** 来支持[硬件加速]:https://developer.android.com/studio/run/emulator-acceleration.html。
    6. 验证AVD配置是否正确，并选择 ** Finish ** 。
    
      >> 有关上述步骤的详细信息，请参见 [管理AVDs]:https://developer.android.com/studio/run/managing-avds.html。
      
    7. 在Android虚拟设备管理器中，单击工具栏中的Run。模拟器启动并显示选定的OS版本和设备的默认画布。
