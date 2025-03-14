---
layout: default
title: 环境配置
---

# 石大时光圈项目环境配置指南

## 必要软件安装（预计时间：20-30分钟）

### 1. Flutter SDK 安装

**Windows:**
1. 下载 Flutter SDK zip压缩包：[flutter.dev/docs/get-started/install/windows](https://flutter.dev/docs/get-started/install/windows)
2. 解压到不含空格的路径（例如：`C:\dev\flutter`）
3. 添加`flutter\bin`到系统环境变量Path中
4. 在命令提示符中运行`flutter doctor`检查是否安装成功

**macOS:**
1. 下载 Flutter SDK zip压缩包：[flutter.dev/docs/get-started/install/macos](https://flutter.dev/docs/get-started/install/macos)
2. 解压到合适的目录（例如：`~/development/flutter`）
3. 添加Path：在终端运行 `export PATH="$PATH:`pwd`/flutter/bin"` 
4. 添加到`.bash_profile`或`.zshrc`确保永久生效
5. 运行`flutter doctor`检查

**Linux:**
1. 下载 Flutter SDK zip压缩包：[flutter.dev/docs/get-started/install/linux](https://flutter.dev/docs/get-started/install/linux)
2. 解压到合适目录（例如：`~/development/flutter`）
3. 添加Path：`export PATH="$PATH:`pwd`/flutter/bin"` 
4. 添加到`.bashrc`确保永久生效
5. 运行`flutter doctor`检查

### 2. Git 安装

**Windows:** 下载并安装 [Git for Windows](https://git-scm.com/download/win)

**macOS:** 
- 通过终端运行 `xcode-select --install` 或
- 使用Homebrew: `brew install git`

**Linux:** `sudo apt install git` 或 `sudo yum install git`

### 3. IDE 安装（选择一个）

**推荐：VS Code**
1. 下载安装 [VS Code](https://code.visualstudio.com/)
2. 安装Flutter和Dart插件：
   - 打开VS Code
   - 按Ctrl+Shift+X(Windows/Linux)或Cmd+Shift+X(Mac)打开扩展
   - 搜索"Flutter"并安装

**或者：Android Studio**
1. 下载安装 [Android Studio](https://developer.android.com/studio)
2. 安装Flutter和Dart插件：
   - 打开Android Studio → Preferences/Settings → Plugins
   - 搜索"Flutter"并安装（会自动包含Dart）

## 石大时光圈项目获取（预计时间：5-10分钟）

### 1. 克隆项目
打开终端/命令提示符，运行：
```
git clone https://github.com/[用户名]/ShidaTimeCircle.git
cd ShidaTimeCircle
```

### 2. 获取依赖
在项目目录下运行：
```
flutter pub get
```

### 3. 运行项目
连接手机或启动模拟器，然后运行：
```
flutter run
```

## 环境验证检查清单

- [ ] `flutter doctor`命令显示所有组件均通过检查
- [ ] 成功克隆项目代码
- [ ] 成功运行`flutter pub get`无错误
- [ ] 项目能在模拟器或实机上启动

## 常见问题快速解决

1. **Flutter SDK未找到**  
   确保环境变量正确设置，重启终端/命令提示符

2. **Android SDK许可问题**  
   运行 `flutter doctor --android-licenses` 并接受所有许可

3. **依赖获取失败**  
   检查网络连接，或使用国内镜像：
   ```
   export PUB_HOSTED_URL=https://pub.flutter-io.cn
   export FLUTTER_STORAGE_BASE_URL=https://storage.flutter-io.cn
   ```

4. **模拟器/设备未检测到**  
   - Android: 确保开启USB调试
   - iOS: 确保安装Xcode和配置开发者账号

## 获取帮助
- 扫描下方二维码加入项目交流群
- 在GitHub上提Issues: [项目Issues页面]
- 发送邮件至: asher.ji@icloud.com