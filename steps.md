# 重装 macOS 流程

2017-05-12

## 制作安装盘

* 在 App Store 中搜索最新版的 macOS，并点击「下载」
* 下载完成后，会弹出安装提示，不要理会
* 找一个大于 8G 的 U盘
* 清空磁盘
    * 通过 Spotlight 或 Launchpad 启动「磁盘工具」，并点击「继续」
    * 从左侧的列表中选择插入的 U盘，然后选择「抹掉」标签
    * 格式【Mac OS 扩展（日志式）】
    * 磁盘名称【MyVolume】（此名称可随便起，后边会用到）
    * 点击「抹掉」
* 创建安装盘
    * 通过 Spotlight 或 Launchpad 启动「终端」
    * 刚才下载的 macOS 会放在 `/Applications` 目录下，假设文件名为 `Install macOS Sierra.app`
    * 执行：`sudo /Applications/Install\ macOS\ Sierra.app/Contents/Resources/createinstallmedia --volume /Volumes/MyVolume --applicationpath /Applications/Install\ macOS\ Sierra.app`
    * 会给出提示并需要确认，然后开始制作安装盘
        * 在 `Copying installer files to disk...` 这一步时可能要多等一会儿
        * 最后会提示 `Copy complete. Done` 表示制作完成

## 系统安装

* 重启电脑并按住 option 键，在启动菜单中选择刚刚制作的 U盘
* 保证整个过程联网，否则会提示「安装器有效负载签名检查失败」
* 如果需要全新安装，需要先通过「磁盘工具」抹掉硬盘上的内容（做好备份），随后开始安装
* 一定不要应用 FileVault 特性

## 系统设置

以下流程，都基于在安装时已联网并登录 iCloud 账号，所以会缺少一些关于 iCloud 的配置细节

### 系统偏好设置

* Dock
    * 调整 Dock 大小
    * 置于屏幕【左边】
    * 【勾选】将窗口最小化为应用程序图标
* Mission Control
    * 【取消勾选】根据最近的使用情况自动重新排列 Space
    * Dashboard 【作为叠层】
* 语言和地区
    * 【24小时制】
* 显示器
    * 【取消勾选】在菜单栏中显示镜像选项（可用时）
* 键盘
    * 文本
        * 【取消勾选】自动纠正拼写
        * 【取消勾选】自动大写字词的首字母
    * 快捷键
        * 输入法 => 选择上一个输入法【Command + 空格键】
        * 输入法 => 【取消勾选】选择「输入法」菜单中的下一个输入法
        * Spotlight => 显示 Spotlight 搜索【Control + 空格键】
        * Spotlight => 【取消勾选】显示 Finder 搜索窗口
* 触控板
    * 全部勾选
    * 更多手势 => 【取消勾选】在页面之间轻扫
* 声音
    * 【勾选】在菜单栏中显示音量
* iCloud
    * 【勾选】除「照片」与「回到我的 Mac」外的其他项
* App Store
    * 【取消勾选】在后台下载新的可用更新
    * 免费下载【存储密码】
* 网络
    * 除「Wi-Fi」外，【停用】其他的连接方式（默认还有「蓝牙 PAN」和「Thunderbolt 网桥」）
* 扩展
    * 【取消勾选】无用的项，特别是「共享菜单」中的项
* 共享
    * 修改【电脑名称】
* 用户与群组
    * 【停用】客人用户
    * 登录项 =>【删除】无用的登录项目
* Siri
    * 【取消勾选】在菜单栏中显示 Siri
* 日期与时间
    * 时钟
        * 【勾选】显示星期几
        * 【勾选】显示日期
* 辅助功能
    * 鼠标与触控板
        * 触控板选项
            * 【勾选】启用拖移【三指拖移】

### Finder 编好设置

* 通用
    * 【勾选】以下项目
        * 外置磁盘
        * CD、DVD 和 iPod
    * 开启新 Finder 窗口时打开【<家目录>】
* 边栏
    * 【勾选】以下项目，其他全部取消勾选
        * 个人收藏 
            * iCloud Drive
            * AirDrop
            * 桌面
            * 文稿
            * 下载
            * <家目录>
        * 设备
            * 硬盘
* 高级
    * 【勾选】显示所有文件的扩展名

### 系统右侧通知栏

* 保留：今天、计算器、提醒事项、日历、明天

### Terminal

* 【待补充】

## 安装应用

安装应用后，对应的要针对每个应用做配置。

### App Store

* WeChat
* iWorks
    * Pages
    * Numbers
    * Keynote
* Xcode
* Dr. Cleaner Pro
* Dr. Unarchiver
* Evernote
* MWeb

### 下载

可以将下载的应用安装在自己的家目录下，此时需要在家目录下创建 `Applications` 文件夹（注意是复数形式），如果要让它显示中文名，在文件夹中创建 `.localized` 文件。

* 输入法
    * [Baidu Input](http://srf.baidu.com/input/mac.html)
* 沟通
    * [QQ](http://im.qq.com/macqq/)
    * [Dingtalk](https://www.dingtalk.com)
    * [Wangwang](http://wangwang.taobao.com)
* 工具
    * [Chrome](https://www.google.com/chrome/)
        * 【勾选】退出前提示
    * [Mubu](https://mubu.com)
    * [XMind](http://www.xmind.net/)
    * [Baidu Netdisk](http://pan.baidu.com)
    * [Thunder](http://xunlei.com)
* 多媒体
    * [Netease Music](http://music.163.com)
    * [MplayerX](https://github.com/niltsh/MPlayerX-Deploy/releases)
* 开发
    * [iTerm](http://www.iterm2.com)
    * [MacVim](https://github.com/macvim-dev/macvim/releases/tag/snapshot-133)
    * [Atom](https://github.com/atom/atom/releases)
    * [JDK](http://www.oracle.com/technetwork/java/javase/downloads/index.html)
    * [Charles Proxy](http://www.charlesproxy.com/)
    * Adobe Photoshop
    * iHosts

### 命令行安装

建议不使用 cask 安装应用，会导致安装目录比较乱，可以通过 cask 查找要安装应用的下载地址后自主下载安装。

* [brew](http://brew.sh/)
    * nvm
        * node
        * cnpm/tnpm
    * autojump
* [oh-my-zsh](https://github.com/robbyrussell/oh-my-zsh)

### 配置开发环境

* 复制 [my-mac-env](https://github.com/mingelz/my-mac-env) 相关的文件
* MacVim
    * 复制 `my-mac-env/~/.vimrc` 文件
    * 配置 MacVim 可在命令行中执行：`ln -s ~/Applications/MacVim.app/Contents/bin/mvim /usr/local/bin/mvim`
    * 安装 [Vundle](https://github.com/VundleVim/Vundle.vim)
    * 通过 Vundle 安装插件：`:PluginsInstall`，插件已经在 `~/.vimrc` 中定义
* Atom
    * 配置 Atom 可在命令行中执行：打开应用点击 【Install Shell Commands】
    * 复制 `my-mac-env/~/.atom` 目录
    * 使用 `apm` 命令安装插件
        * atom-language-xtpl
        * editorconfig
        * file-icons
        * language-babel
        * language-vue
        * platformio-ide-terminal
        * vim-mode-plus
        * vim-mode-plus-ex-mode
        * vim-mode-plus-keymaps-for-surround
        * ~~wakatime~~
* SSH
    * 复制 `my-mac-env/~/.ssh` 目录
    * 使用 `ssh-keygen` 生成针对每个站点的 SSH key
    * 编辑 `~/.ssh/config` 文件分别指向刚才生成的密钥
* Git
    * 重新编辑 `~/.gitconfig` 中的用户信息
* Nginx
    * 复制 `my-mac-env/usr/local/etc/nginx` 目录
    * 根据实际需要编辑 `nginx.conf` 文件，其中有较详细的注释
    * 如需要支持 https，使用 `gen-ssl-csr.sh` 生成证书
