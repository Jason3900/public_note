# 开发环境配置及常用软件之Linux篇

> 作者：方雪至 jasonfang3900@gmail.com
>
> 时间：2020.2.23
>
> 发行版本：Ubuntu 18.04.3 LTS
>
> 内核版本：5.3.0-40-generic


## 1. 开发环境

### 1.1  Python

- Anaconda

  - 简介

    Anaconda是一个免费开源的Python和R语言的发行版，默认包含Python和pip（一种软件包管理系统），默认使用Conda进行软件包管理，并可创建虚拟环境管理不同使用场景下的软件包。

  - 下载地址

    - 官网：https://www.anaconda.com/distribution/#download-section
    - 清华镜像（国内推荐）：https://mirrors.tuna.tsinghua.edu.cn/anaconda/archive/Anaconda3-2019.10-Linux-x86_64.sh

  - 配置环境变量

    - 安装结束后脚本会提示是否将环境变量添加到用户环境配置文件中，确认即可。但对于zsh等其他shell用户，可将~/.bashrc 中生成的配置信息复制到~/.zshrc中，并修改第一行中的shell.bash为shell.zsh即可

  - 换源

    - Anaconda清华源：https://mirror.tuna.tsinghua.edu.cn/help/anaconda/
    - Pip清华源：https://mirror.tuna.tsinghua.edu.cn/help/pypi/
  
- PyCharm

  - 简介

    PyCharm是一个用于计算机编程的集成开发环境（IDE），主要用于Python语言开发，提供代码分析、图形化调试器，集成测试器、集成版本控制系统，并支持使用Django进行网页开发。 

    <img src="ubuntu%20%E9%85%8D%E7%BD%AE%E6%8C%87%E5%8D%97.assets/image-20200223181347974.png" alt="image-20200223181347974" style="zoom: 40%;" />

  - 下载地址

    - 官网：https://www.jetbrains.com/pycharm/

    > 学生可用教育邮箱注册，获得教育版使用权限
    
  - 安装运行
  
    - 解压下载的软件包，执行bin/pycharm.sh脚本即可运行
  
    - 可通过主界面中的Tools里的Create Desktop Entry 及Create Command-line Launcher添加至应用程序菜单及命令行。

### 1.2 C++

- CLion

  - 简介

    跨平台的C/C++ IDE 开发工具，支持C++11 、C++14、libc++以及Boost。

  - 下载地址

    - 官网：https://www.jetbrains.com/clion/download/#section=linux

    > 学生可用教育邮箱注册，获得教育版使用权限
    
  - 安装运行
  
    - 解压下载的软件包，执行bin/clion.sh脚本即可运行
  
    - 可通过主界面中的Tools里的Create Desktop Entry 及Create Command-line Launcher添加至应用程序菜单及命令行。
  
      <img src="ubuntu%20%E9%85%8D%E7%BD%AE%E6%8C%87%E5%8D%97.assets/cLion.png" alt="cLion" style="zoom:50%;" />

### 1.3  文本编辑器

- VS Code

  - 简介

    Visual Studio Code（简称VS Code）是一个由微软开发，同时支持Windows 、 Linux和macOS等操作系统且开放源代码的代码编辑器，它支持测试，并内置了Git 版本控制功能，同时也具有开发环境功能，例如代码补全、代码片段和代码重构等，是最受欢迎的开发环境之一。

  - 下载地址

    - 官网：https://code.visualstudio.com/

  - 推荐插件

    - Python

      代码补全、语法高亮等

    - Remote-SSH

      服务器远程连接

    - Rainbow-CSV

      CSV格式高亮

    - Markdown All in One

      Markdown相关功能支持

- Vim 8.2

  - 简介

    Vim是从vi发展出来的一个文本编辑器。其代码补全、编译及错误跳转等方便编程的功能特别丰富，在程序员中被广泛使用。

  <img src="ubuntu%20%E9%85%8D%E7%BD%AE%E6%8C%87%E5%8D%97.assets/image-20200223141928805.png" alt="image-20200223141928805" style="zoom: 42%;" />

  - 安装 & 配置
    - apt源的vim是8.0版，没有python等语言支持，因此需要卸载后自己从源码编译新版，添加相应的功能。
      - vim编译指南：[https://github.com/ycm-core/YouCompleteMe/wiki/Building-Vim-from-source](https://github.com/ycm-core/YouCompleteMe/wiki/Building-Vim-from-source)

      - vim配置指南：https://www.bilibili.com/video/av55498503

### 1.4 Git

- GitKraken

  图形化界面Git管理工具

  <img src="ubuntu%20%E9%85%8D%E7%BD%AE%E6%8C%87%E5%8D%97.assets/gitkraken.png" alt="gitkraken" style="zoom:50%;" />

```bash
wget -c https://release.gitkraken.com/linux/gitkraken-amd64.deb # 下载deb安装包
sudo apt install ./gitkraken-amd64.deb -y # 安装
sudo rm -f ./gitkraken-amd64.deb # 删除安装包
```



## 2. 命令行实用工具

### 2.1 Shell 配置

- zsh & oh-my-zsh

  比默认的bash更好用的shell

  - 安装 & 配置

    - ```bash
      sudo apt install zsh -y
      sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
      chsh -s /usr/bin/zsh # 修改默认shell为zsh
      vim ~/.zshrc # 修改zsh配置
      exec zsh # 使配置生效
      ```

  - zsh常用插件：[https://github.com/zsh-users](https://github.com/zsh-users)

    - zsh-autosuggestions
    - zsh-syntax-highlighting

### 2.2 压缩、解压

- unar

  命令行解压工具，用以解决zip解压后可能造成的文件名乱码等问题

```bash
sudo  apt install unar -y
```

### 2.3 下载

- Aria2

  ​	命令行下载工具，不会限速

  - linux命令行下载工具对比：[https://www.linuxidc.com/Linux/2019-03/157681.htm](https://www.linuxidc.com/Linux/2019-03/157681.htm)

```bash
sudo apt-get install aria2 -y
```

- youtube-dl

  youtube、lynda等网站视频下载工具

```bash
sudo apt install python3-pip
pip3 install youtube-dl
```

### 2.4 代理

- V2ray

  配合vps愉快地访问google学术等

  - ```bash
    sudo -i # 进入超级管理员模式
    bash <(curl -L -s https://install.direct/go.sh) # 下载并安装一键安装脚本
    vim /etc/v2ray/config.json # 修改v2ray配置
    service v2ray start # 启动v2ray服务
    service v2ray status # 查看v2ray是否成功启用
    ```

  - v2ray配置指南：[https://toutyrater.github.io/](https://link.zhihu.com/?target=https%3A//toutyrater.github.io/)

  - v2ray的ss配置参考：
    - ```json
      {
        "log": {
          "error": "",
          "loglevel": "warning",
          "access": ""
        },
        "inbounds": [
          {
            "listen": "127.0.0.1",
            "protocol": "socks", // 入口协议1
            "settings": {
              "ip": "",
              "userLevel": 0,
              "timeout": 360,json
              "udp": true,
              "auth": "noauth"
            },
            "port": "12333" // 监听端口，自己设置就好，不要用常用端口
          },
          {
            "listen": "127.0.0.1",
            "protocol": "http", // 入口协议2，可以只用http不用socks，根据个人需求修改即可
            "settings": {
              "timeout": 360
            },
            "port": "12334" // 监听端口，同上
          }
        ],
        "outbounds": [
          {
            "protocol": "shadowsocks",
            "streamSettings": {
              "tcpSettings": {
                "header": {
                  "type": "none"
                }
              },
              "tlsSettings": {
                "allowInsecure": true
              },
              "security": "none",
              "network": "tcp"
            },
            "tag": "agentout",
            "settings": {
              "servers": [
                {
                  "port": 56850,
                  "method": "此处填写加密方式",
                  "password": "此处填写密码",
                  "address": "此处填写服务器地址",
                  "level": 0,
                  "email": "",
                  "ota": false
                }
              ]
            }          ],
                "domain": [
                  "geosite:cn",
                  "geosite:speedtest"
                ]
              }
            ]
          }
        },
        "transport": {}
      }
          },
          {
            "tag": "direct",
            "protocol": "freedom",
            "settings": {
              "domainStrategy": "AsIs",{
        "log": {
          "error": "",
          "loglevel": "warning",
          "access": ""
        },
              "redirect": "",
              "userLevel": 0
            }
          },
          {
            "tag": "blockout",
            "protocol": "blackhole",
            "settings": {
              "response": {
                "type": "none"
              }
            }
          }
        ],
        "dns": {json
          "servers": [
            "8.8.8.8"
          ]
        },
        "routing": {
          "strate          ],
                "domain": [
                  "geosite:cn",
                  "geosite:speedtest"
                ]
              }
            ]
          }
        },
        "transport": {}
      }gy": "rules",
          "settings": {
            "domainStrategy": "IPIfNonMatch",
            "rules": [
              {
                "outboundTag": "direct",
                "type": "field",
                "ip": [
                  "geoip:cn",
                  "geoip:private"
                ],
                "domain": [
                  "geosite:cn",
                  "geosite:speedtest"
                ]
              }
            ]
          }
        },
        "transport": {}
      }
      ```

### 2.5 软件包管理

- snap

  linux软件包管理工具

```bash
sudo apt install snap
```

### 2.6 电源管理

- tlp

  linux电源管理、硬件状态监控

  - 安装

    - ```bash
      sudo add-apt-repository ppa:linrunner/tlp
      sudo apt update
      sudo apt install tlp -y
      ```

  - 官方配置指南：[https://linrunner.de/en/tlp/docs/tlp-configuration.html](https://linrunner.de/en/tlp/docs/tlp-configuration.html)



## 3. GUI界面常用软件

### 3.1 高效检索

- albert

  类似mac下的spotlight，搜索用

  <img src="ubuntu%20%E9%85%8D%E7%BD%AE%E6%8C%87%E5%8D%97.assets/albert.png" alt="albert" style="zoom: 50%;" />

```bash
sudo add-apt-repository ppa:noobslab/macbuntu
sudo apt update
sudo apt install albert -y
```

### 3.2 文件下载

- XDM

  Linux图形界面下高速下载工具，可配合官方插件嗅探下载链接

  <img src="ubuntu%20%E9%85%8D%E7%BD%AE%E6%8C%87%E5%8D%97.assets/image-20200223204723736.png" alt="image-20200223204723736" style="zoom: 55%;" />

  - 下载地址
    - 官网：http://xdman.sourceforge.net/#downloads

### 3.3 文献/电子书阅读、管理

- Zotero

  跨平台的文献管理软件，支持中英文文献信息导入、自动下载相应的pdf、网页快照等。可配合同步盘（google drive等）跨平台同步文献数据

  <img src="ubuntu%20%E9%85%8D%E7%BD%AE%E6%8C%87%E5%8D%97.assets/image-20200223204120127.png" alt="image-20200223204120127" style="zoom: 50%;" />

  - 下载地址

    - 官网：https://www.zotero.org/download/

  - 添加到应用程序菜单

    - ```bash
      sudo ln -s <ZOTERO_PATH>/zotero.desktop /usr/share/applications/zotero.desktop
      ```

- Foxit PDF reader

  跨平台PDF阅读器

  <img src="ubuntu%20%E9%85%8D%E7%BD%AE%E6%8C%87%E5%8D%97.assets/image-20200223210102300.png" alt="image-20200223210102300" style="zoom: 44%;" />

  - 下载地址：[https://www.foxitsoftware.com/pdf-reader/](https://www.foxitsoftware.com/pdf-reader/)

- Calibre

  跨平台电子书阅读、管理软件，甚至可以抓取新闻

  <img src="ubuntu%20%E9%85%8D%E7%BD%AE%E6%8C%87%E5%8D%97.assets/calibre.png" alt="calibre" style="zoom:50%;" />

  - Tip：不建议apt 直接安装，版本特别旧。建议按照官方推荐的方式安装，过程如下：

```bash
sudo -i # 进入超级用户模式
# port这里填写自己代理的端口，如8080等。Calibre安装不走代理的话可能要下几个小时
export http_proxy=http://127.0.0.1:port && export https_proxy=http://127.0.0.1:port
wget -nv -O- https://download.calibre-ebook.com/linux-installer.sh | sh /dev/stdin
exit # 退出超级用户模式
```

### 3.4 Markdown编辑器

- Typora

  markdown编辑器，功能强大，界面友好，支持多种数学公式，支持HTML语法，本文是用Typora写成的。

  <img src="ubuntu%20%E9%85%8D%E7%BD%AE%E6%8C%87%E5%8D%97.assets/typora.png" alt="typora" style="zoom:50%;" />

```bash
wget -qO - https://typora.io/linux/public-key.asc | sudo apt-key add -
sudo add-apt-repository 'deb https://typora.io/linux ./'
sudo apt-get update
sudo apt-get install typora -y
```

- markdown数学公式指南：https://katex.org/docs/supported.html

### 3.5 音视频播放

- Spotify

  跨平台音乐软件，界面简洁，无广告及其他干扰

  <img src="ubuntu%20%E9%85%8D%E7%BD%AE%E6%8C%87%E5%8D%97.assets/spotify.png" alt="spotify" style="zoom:42%;" />

  - Tip：不太建议安装snap的版本，貌似启动时反应会很慢。建议按照以下方式添加官方源后安装：

```bash
curl -sS https://download.spotify.com/debian/pubkey.gpg | sudo apt-key add - 
echo "deb http://repository.spotify.com stable non-free" | sudo tee /etc/apt/sources.list.d/spotify.list
sudo apt-get update && sudo apt-get install spotify-client -y # 最好也是按之前的方式走代理下载安装，否则也很慢
```

- VLC

全平台视频播放软件，界面简洁无广告，功能强大，支持格式全面

<img src="ubuntu%20%E9%85%8D%E7%BD%AE%E6%8C%87%E5%8D%97.assets/vlc.png" alt="vlc" style="zoom:39%;" />

```bash
sudo apt install vlc -y
```

### 3.6 虚拟打印

- Boomaga

  Linux 下的虚拟打印机，可以将caj等格式文档转存为pdf

```bash
sudo add-apt-repository ppa:boomaga
sudo apt update
sudo apt install boomaga
```

### 3.7 多媒体编辑

- Audacity/Ardour

  Linux 下开源的音频剪辑工具，前者简单易用、功能齐全，后者可以满足专业需求

  <img src="ubuntu%20%E9%85%8D%E7%BD%AE%E6%8C%87%E5%8D%97.assets/ardour.png" alt="ardour" style="zoom:44%;" />

  - Tip：Audacity 可以直接通过sudo apt install audacity安装，但版本比较旧，下面提供最新版的安装方式

    - ```bash
      sudo add-apt-repository ppa:ubuntuhandbook1/audacity
      sudo apt-get update
      sudo apt-cache madison audacity # 查看一下该软件有几个可用版本，复制最新的版本号。（不要安装2.3.0，官方说该版本有问题）
      sudo apt install audacity=刚才复制的版本号 -y # 如2.3.3-0build1~ubuntu18.04
      ```

  - Ardour 安装指南：[https://www.cnblogs.com/milton/p/9708428.html](https://www.cnblogs.com/milton/p/9708428.html)

- Shotcut

  Linux 视频剪辑软件，支持4k，功能较全

  <img src="ubuntu%20%E9%85%8D%E7%BD%AE%E6%8C%87%E5%8D%97.assets/shotcut.png" alt="shotcut" style="zoom: 44%;" />

```bash
sudo snap install shotcut --classic
```

### 3.8 云盘同步

- Insync

  跨平台云盘同步工具，支持One drive与Google drive

  <img src="ubuntu%20%E9%85%8D%E7%BD%AE%E6%8C%87%E5%8D%97.assets/insync-1582466380130.png" alt="insync" style="zoom:46%;" />

  - 下载地址：[https://www.insynchq.com/](https://www.insynchq.com/)

### 3.9 Wine

- Crossover/Deepin-wine

  基于wine的类虚拟机软件，可以用来安装MS office、印象笔记、qq、微信、迅雷等

  <img src="ubuntu%20%E9%85%8D%E7%BD%AE%E6%8C%87%E5%8D%97.assets/evernote.png" alt="evernote" style="zoom: 33%;" />

  - Crossover下载地址：[https://www.crossoverchina.com/xiazai.html](https://www.crossoverchina.com/xiazai.html)

  - Deepin-wine安装

    - ```bash
      echo "deb [trusted=yes] http://mirrors.aliyun.com/deepin stable main contrib non-free" | sudo tee /etc/apt/sources.list.d/deepin.list
      sudo apt update
      sudo apt install -t bionic deepin.com.wechat deepin.com.qq.office -fy #此处根据自己需求更改即可
      sudo rm -f /etc/apt/sources.list.d/deepin.list
      sudo apt update
      ```

### 3.10 语言学习

- Goldendict

  Linux下强大的查词、翻译软件，定制性高

  <img src="ubuntu%20%E9%85%8D%E7%BD%AE%E6%8C%87%E5%8D%97.assets/goldendict.png" alt="goldendict" style="zoom:50%;" />

  - 安装

    - ```bash
      sudo apt install goldendict -y
      ```

  - 配置指南：[http://einverne.github.io/post/2018/08/goldendict.html](http://einverne.github.io/post/2018/08/goldendict.html)

- Anki

  知名的记忆辅助软件，定制性高、资源丰富

  <img src="ubuntu%20%E9%85%8D%E7%BD%AE%E6%8C%87%E5%8D%97.assets/image-20200223214051335.png" alt="image-20200223214051335" style="zoom: 50%;" />

  - 下载地址
    - 官网：https://apps.ankiweb.net/

### 3.11 界面美化、桌面工具 

- Gnome-tweak-tool

  桌面优化、小工具添加

```bash
sudo apt install gnome-tweak-tool -y
```
- 实用桌面工具安装：[https://extensions.gnome.org/](https://extensions.gnome.org/)
    - System-monitor：任务栏显示实时网速，cpu、gpu、内存占用等
    - Toplcons plus：任务栏显示程序小图标（可解决deepin-wine微信托盘不显示的问题）
    - Gsconnect：Ubuntu连接手机（Android系统），共享通知、文件，幻灯片播放控制等
