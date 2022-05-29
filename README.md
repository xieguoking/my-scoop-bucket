# 1、安装scoop

## 1.1、在powershell安装

```powershell
# 在 PowerShell 中打开远程权限
Set-ExecutionPolicy RemoteSigned -scope CurrentUser;

# 自定义 Scoop 安装目录
$env:SCOOP='e:\scoop_home'
[Environment]::SetEnvironmentVariable('SCOOP', $env:SCOOP, 'User')

# 下载并安装 Scoop
iwr -useb get.scoop.sh | iex
# Invoke-Expression (New-Object System.Net.WebClient).DownloadString('https://get.scoop.sh')
scoop update
```



## 2.2、常用命令

```powershell
# 安装
scoop install <app>
scoop install <bucket>/<app>

# 卸载
scoop uninstall <app>

# 列出已安装
scoop list

# 查看仓库
scoop bucket list

# 查看官方推荐仓库
scoop bucket known

# 配置
scoop config key value
```



# 2、安装扩展库

## 2.1、安装Aria2来加速

```powershell
# 安装 Aria2 来加速下载
scoop install aria2

#　如果使用代理，有时需要通过如下命令关闭 aria2
scoop config aria2-enabled false

# aria2 在 Scoop 中默认开启
scoop config aria2-enabled true
# 关于以下参数的作用，详见aria2的相关资料
scoop config aria2-retry-wait 4
scoop config aria2-split 16
scoop config aria2-max-connection-per-server 16
scoop config aria2-min-split-size 4M
```

## 2.2、配置代理

```powershell
scoop config proxy 127.0.0.1:8999
```



## 2.3、安装仓库前需要安装git

```powershell
scoop install git
```



## 2.4、添加常见仓库

```powershell
#　添加官方维护的extras库（含大量GUI程序）
scoop bucket add extras
scoop update

# 国内镜像
# scoop bucket add extras https://gitee.com/scoop-bucket/extras.git

scoop bucket add scoopet https://github.com/ivaquero/scoopet.git
scoop update

scoop bucket add dorado https://github.com/chawyehsu/dorado
scoop update

# add bucket
scoop bucket add java https://github.com/ScoopInstaller/Java.git
scoop update
```



# 3、常用软件

```powershell
# 安装包
scoop install <app_name>
scoop install sudo

# 使用 Linux 命令行
scoop install gow

# 调用管理员权限
scoop install sudo

# windows 终端模拟器
scoop install cmder
```



## 3.1、开发工具



```powershell
# windows-terminal
scoop install windows-terminal

# install java jdk
scoop install java/zulu13-jdk
scoop install java/zulu8-jdk

# 切换不同的jdk
scoop reset java/zulu13-jdk

# install nvm
# scoop install nvm
scoop install dorado/nvm-windows

# list available node
nvm list available

# install node by nvm
nvm install 16.15.0

# list installed node 
nvm list
```



|           App           |                             介绍                             |
| :---------------------: | :----------------------------------------------------------: |
|    windows-terminal     |                      Windows 新版本终端                      |
|     java/zulu8-jdk      |                          Zulu JDK 8                          |
|     java/zulu13-jdk     |                                                              |
|   dorado/nvm-windows    |                                                              |
|         WinGet          |                                                              |
|     tencent-meeting     |                           腾讯会议                           |
|     CopyTranslator      |                                                              |
|      neteasemusic       |                                                              |
|       tencent-edu       |                           腾讯教学                           |
|       wechatwork        |                           企业微信                           |
|         wechat          |                             微信                             |
|         deepgit         |                    一款git可视化分析工具                     |
|      googlechrome       |                        Google Chrome                         |
|       llvm-mingw        |  一个基于 LLVM/Clang/LLD 的 **mingw-w64** 工具链 (LLVM 13)   |
|        msys2-cn         |    专为国人安装使用而配置的 MSYS2，全自动无人值守安装即用    |
|     nuwen-mingw-gcc     | 来自微软职工 STL 的极简 C/C++ 编译器，源自 [MinGW Distro](https://nuwen.net/mingw.html), 快速使用 GCC 的最佳选择 (GCC GCC 11.x) |
|  winlibs-mingw-msvcrt   | winlibs](http://winlibs.com/) 编译的完整 MSVCRT 运行库 **mingw-w64** 工具链发行版 (GCC 11.x) |
| winlibs-mingw-llvm-ucrt |           包含 LLVM 13 支持的 *winlibs-mingw-ucrt*           |
|   winlibs-mingw-ucrt    | winlibs](http://winlibs.com/) 编译的完整 UCRT 运行库 **mingw-w64** 工具链发行版 (GCC 11.x) |
|                         |                                                              |



## 3.2、其它工具

|        app        |                             介绍                             |
| :---------------: | :----------------------------------------------------------: |
| Clash-for-Windows | Clash for Windows 是目前在 Windows 上唯一可用的图形化 Clash 分支。通过 Clash API 来配置和控制 Clash 核心程序，便于用户可视化操作和使用。 |
|                   |                         小狼毫输入法                         |
|  M3u8-Downloader  | M3U8-Downloader是基于Electron框架开发的一款可以下载、播放HLS视频流的APP |
|     RustDesk      | 远程桌面软件，开箱即用，无需任何配置。您完全掌控数据，不用担心安全问题。您可以使用我们的注册/中继服务器，或者自建，亦或者开发您的版本 |
|     dingtalk      |                           阿里钉钉                           |
|      DownKyi      |                       bilibili下载工具                       |
|     Edgeless      |                      一款半开源的PE工具                      |
|      MagnetW      |                     最强BT种子搜索神器！                     |
|      listary      | 一款用于Windows的文件搜索、定位的辅助软件。它提供了便捷、人性化的文件定位方式，改善Windows传统低效的文件打开/保存对话框，同时改善了常见文件管理器中文件夹切换的效率。 |
|                   |                                                              |
|                   |                                                              |
|                   |                                                              |

