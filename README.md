# Show an icon in the tray for UWP/为UWP显示托盘图标

It will stay running in the tray after you close the UWP main window.

在关闭UWP的主窗口后，托盘图标将继续运行，常驻于托盘。

![](screenshot.png)

# How does it work/如何工作

By declaring the `runFullTrust` capability in `Package.appxmanifest`, we can launch a bundled non-UWP executable when launching the app. We rely on that non-UWP exe to show the tray icon and its context menu. They use AppService to communicate with each other.

We also declared a command line alias for this UWP, so we can use command line to launch the UWP part in the non-UWP part after the UWP is closed.

通过在`Package.appxmanifest`里声明`runFullTrust`能力，我们可以在应用启动的同时启动一个非UWP的可执行文件；我们依赖它显示托盘图标和上下文菜单。二者通过AppService交流。

我们同时为应用声明了一个命令行别名，以便于我们在UWP关闭后唤起它。
