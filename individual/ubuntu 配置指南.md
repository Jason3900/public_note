# Ubuntu 18 简易配置指南（1）
## 命令行实用工具

### vim8.2
apt源的vim是8.0版，没有python等语言支持，因此需要卸载后自己从源码编译新版，添加相应的功能。
- vim编译指南：[https://github.com/ycm-core/YouCompleteMe/wiki/Building-Vim-from-source](https://github.com/ycm-core/YouCompleteMe/wiki/Building-Vim-from-source)

- vim配置指南：[https://www.bilibili.com/video/av55498503?from=search&seid=3054640709418884277](https://www.bilibili.com/video/av55498503?from=search&seid=3054640709418884277)

### snap
linux软件包管理工具
```
sudo apt install snap
```

### Aria2
命令行下载工具，不会限速 - -
```bash
sudo apt-get install aria2 -y
```
- linux命令行下载工具对比：[https://www.linuxidc.com/Linux/2019-03/157681.htm](https://www.linuxidc.com/Linux/2019-03/157681.htm)


### tlp
linux电源管理、硬件监控
```bash
sudo add-apt-repository ppa:linrunner/tlp
sudo apt update
sudo apt install tlp -y
```
- 官方配置指南：[https://linrunner.de/en/tlp/docs/tlp-configuration.html](https://linrunner.de/en/tlp/docs/tlp-configuration.html)

### unar
命令行解压工具，用以解决zip解压后可能造成的文件名乱码等问题
```bash
sudo  apt install unar -y
```

### zsh & oh-my-zsh
比默认的bash更好用的shell
```bash
sudo apt install zsh -y
sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
chsh -s /usr/bin/zsh # 修改默认shell为zsh
vim ~/.zshrc # 修改zsh配置
exec zsh # 使配置生效
```
- zsh常用插件：[https://github.com/zsh-users](https://github.com/zsh-users)
    - zsh-autosuggestions
    - zsh-syntax-highlighting

### youtube-dl
youtube、lynda等网站视频下载工具
```bash
sudo apt install python3-pip
pip3 install youtube-dl
```

### v2ray
访问google、youtube等，你懂的
```bash
sudo -i # 进入超级管理员模式
bash <(curl -L -s https://install.direct/go.sh) # 下载并安装一键安装脚本
vim /etc/v2ray/config.json # 修改v2ray配置
service v2ray start # 启动v2ray服务
service v2ray status # 查看v2ray是否成功启用
```
- v2ray配置指南：[https://toutyrater.github.io/](https://toutyrater.github.io/)

## GUI界面常用软件

### VLC

全平台视频播放软件，界面简洁无广告，功能强大，支持格式全面

```bash
sudo apt install vlc -y
```

### albert
类似mac下的spotlight，搜索用
```bash
sudo add-apt-repository ppa:noobslab/macbuntu
sudo apt update
sudo apt install albert -y
```

### Typora
markdown编辑器

```bash
wget -qO - https://typora.io/linux/public-key.asc | sudo apt-key add -
sudo add-apt-repository 'deb https://typora.io/linux ./'
sudo apt-get update
sudo apt-get install typora -y
```

- markdown数学公式指南：https://katex.org/docs/supported.html

### Boomaga
linux 下的虚拟打印机，可以将文档转存为pdf
```bash
sudo add-apt-repository ppa:boomaga
sudo apt update
sudo apt install boomaga
```

### insync
跨平台云盘同步工具，支持onedrive与google drive
- 下载地址：[https://www.insynchq.com/](https://www.insynchq.com/)

### crossover/deepin-wine
基于wine的类虚拟机软件，可以用来安装MS office、印象笔记、qq、微信、迅雷等
- crossover下载地址：[https://www.crossoverchina.com/xiazai.html](https://www.crossoverchina.com/xiazai.html)
- deepin-wine安装：
```bash
echo "deb [trusted=yes] http://mirrors.aliyun.com/deepin stable main contrib non-free" | sudo tee /etc/apt/sources.list.d/deepin.list
sudo apt update
sudo apt install -t bionic deepin.com.wechat deepin.com.qq.office -fy #此处根据自己需求更改即可
sudo rm -f /etc/apt/sources.list.d/deepin.list
sudo apt update
```

### Gnome-tweak-tool
桌面优化、小工具添加
```bash
sudo apt install gnome-tweak-tool -y
```
- 实用桌面工具安装：[https://extensions.gnome.org/](https://extensions.gnome.org/)
    - System-monitor：任务栏显示实时网速，cpu、gpu、内存占用等
    - Toplcons plus：任务栏显示程序小图标（可解决deepin-wine微信托盘不显示的问题）
    - Gsconnect：Ubuntu连接手机（Android系统），共享通知、文件，幻灯片播放控制等

### goldendict
linux下强大的查词、翻译软件，定制性高
```bash
sudo apt install goldendict -y
```
- 配置指南：[http://einverne.github.io/post/2018/08/goldendict.html](http://einverne.github.io/post/2018/08/goldendict.html)

### foxit PDF reader
PDF阅读器
- 下载地址：[https://www.foxitsoftware.com/pdf-reader/](https://www.foxitsoftware.com/pdf-reader/)

### Calibre
跨平台电子书阅读、管理软件，甚至可以抓取新闻

- Tip：不建议apt 直接安装，版本特别旧。建议按照官方推荐的方式安装，过程如下：
```bash
sudo -i # 进入超级用户模式
# port这里填写自己代理的端口，如8080等。Calibre安装不走代理的话可能要下几个小时
export http_proxy=http://127.0.0.1:port && export https_proxy=http://127.0.0.1:port
wget -nv -O- https://download.calibre-ebook.com/linux-installer.sh | sh /dev/stdin
exit # 退出超级用户模式
```

### Spotify
跨平台音乐软件，界面简洁，无广告及其他干扰
- Tip：不太建议安装snap的版本，貌似启动时反应会很慢。建议按照以下方式添加官方源后安装：
```bash
curl -sS https://download.spotify.com/debian/pubkey.gpg | sudo apt-key add - 
echo "deb http://repository.spotify.com stable non-free" | sudo tee /etc/apt/sources.list.d/spotify.list
sudo apt-get update && sudo apt-get install spotify-client -y # 最好也是按之前的方式走代理下载安装，否则也很慢
```

### GitKraken
git 的图形化管理工具
```bash
wget -c https://release.gitkraken.com/linux/gitkraken-amd64.deb # 下载deb安装包
sudo apt install ./gitkraken-amd64.deb -y # 安装
sudo rm -f ./gitkraken-amd64.deb # 删除安装包
```

### Audacity/Ardour
linux 下开源的音频剪辑工具，前者简单易用、功能齐全，后者可以满足专业需求
- Tip：Audacity 可以直接通过sudo apt install audacity安装，但版本比较旧，下面提供最新版的安装方式：
```bash
sudo add-apt-repository ppa:ubuntuhandbook1/audacity
sudo apt-get update
sudo apt-cache madison audacity # 查看一下该软件有几个可用版本，复制最新的版本号。（不要安装2.3.0，官方说该版本有问题）
sudo apt install audacity=刚才复制的版本号 -y # 如2.3.3-0build1~ubuntu18.04
```
- Ardour 安装指南：[https://www.cnblogs.com/milton/p/9708428.html](https://www.cnblogs.com/milton/p/9708428.html)

### Shotcut

linux 视频剪辑软件，支持4k，功能较全

```bash
sudo snap install shotcut --classic
```