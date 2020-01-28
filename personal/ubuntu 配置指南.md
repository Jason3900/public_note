# Ubuntu简易配置指南
## 命令行实用工具
### vim8.2
apt源的vim是8.0版，没有python等语言支持，因此需要卸载后自己从源码编译新版，添加相应的功能。
- vim编译指南：[https://github.com/ycm-core/YouCompleteMe/wiki/Building-Vim-from-source](https://github.com/ycm-core/YouCompleteMe/wiki/Building-Vim-from-source)
- vim配置指南：[https://www.bilibili.com/video/av55498503?from=search&seid=3054640709418884277](https://www.bilibili.com/video/av55498503?from=search&seid=3054640709418884277)
### tlp
linux电源管理、硬件监控
```
sudo add-apt-repository ppa:linrunner/tlp
sudo apt update
sudo apt install tlp -y
```
- 官方配置指南：[https://linrunner.de/en/tlp/docs/tlp-configuration.html](https://linrunner.de/en/tlp/docs/tlp-configuration.html)
### unar
命令行解压工具，用以解决zip解压后可能造成的文件名乱码等问题
```
sudo  apt install unar
```
### zsh & oh-my-zsh
比默认的bash更好用的shell
```
sudo apt install zsh -y
sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
chsh -s /usr/bin/zsh # 修改默认shell为zsh
```
- zsh常用插件：[https://github.com/zsh-users](https://github.com/zsh-users)
    - zsh-autosuggestions
    - zsh-syntax-highlighting
### youtube-dl
网络视频下载
```
sudo apt install python3-pip
pip3 install youtube-dl
```
### v2ray
访问google、youtube等
```
sudo -i # 进入超级管理员模式
bash <(curl -L -s https://install.direct/go.sh) # 下载并安装一键安装脚本
vim /etc/v2ray/config.json # 修改v2ray配置
service v2ray start # 启动v2ray服务
service v2ray status # 查看v2ray是否成功启用
```
- v2ray配置指南：[https://toutyrater.github.io/](https://toutyrater.github.io/)

## GUI界面常用工具
### albert
类似mac下的spotlight，搜索用
```
sudo add-apt-repository ppa:noobslab/macbuntu
sudo apt update
sudo apt install albert -y
```
### insync
跨平台云盘同步工具，支持onedrive与google drive
- 下载地址：[https://www.insynchq.com/](https://www.insynchq.com/)

### crossover/deepin-wine
基于wine的类虚拟机软件，可以用来安装MS office、印象笔记、qq、微信、迅雷等
- crossover下载地址：[https://www.crossoverchina.com/xiazai.html](https://www.crossoverchina.com/xiazai.html)
- deepin-wine安装：
```
echo "deb [trusted=yes] http://mirrors.aliyun.com/deepin stable main contrib non-free" | sudo tee /etc/apt/sources.list.d/deepin.list
sudo apt update
sudo apt install -t bionic deepin.com.wechat deepin.com.qq.office -fy #此处根据自己需求更改即可
sudo rm -f /etc/apt/sources.list.d/deepin.list
sudo apt update

```
### Gnome-tweak-tool
桌面优化、小工具添加
```
sudo apt install gnome-tweak-tool
```
- 实用桌面工具安装：[https://extensions.gnome.org/](https://extensions.gnome.org/)
    - System-monitor：任务栏显示实时网速，cpu、gpu、内存占用等
    - Toplcons plus：任务栏显示程序小图标（可解决deepin-wine微信托盘不显示的问题）
    - Gsconnect：Ubuntu连接手机（Android系统），共享通知、文件，幻灯片播放控制等
### goldendict
linux下强大的查词、翻译软件，定制性高
```
sudo apt install goldendict -y
```
- 配置指南：[http://einverne.github.io/post/2018/08/goldendict.html](http://einverne.github.io/post/2018/08/goldendict.html)

### foxit PDF reader
PDF阅读器
- 下载地址：[https://www.foxitsoftware.com/pdf-reader/](https://www.foxitsoftware.com/pdf-reader/)



