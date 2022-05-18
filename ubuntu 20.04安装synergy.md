synergy是一款局域网内，不同机器，共享同一套键盘鼠标的软件，非常小巧好用。在这里记录一下最新的ubuntu 20.04，安装过程中的一些错误。
synergy-v1.8.8.zip，是在网上下载的，具体在哪下载的，忘记了，里面的构成是：

synergy_1.8.8-stable+dfsg.1-1build1_amd64.deb
synergy-v1.8.8-stable-Windows-x64.msi
有ubuntu版本和windows版本
ubuntu的安装

xx@xx-Lenovo:~/tools/synergy/new-20200513$ sudo dpkg -i synergy_1.8.8-stable+dfsg.1-1build1_amd64.deb 
正在选中未选择的软件包 synergy。
(正在读取数据库 ... 系统当前共安装有 199732 个文件和目录。)
准备解压 synergy_1.8.8-stable+dfsg.1-1build1_amd64.deb  ...
正在解压 synergy (1.8.8-stable+dfsg.1-1build1) ...
dpkg: 依赖关系问题使得 synergy 的配置工作不能继续：
 synergy 依赖于 libqt4-network (>= 4:4.5.3)；然而：
  未安装软件包 libqt4-network。
 synergy 依赖于 libqtcore4 (>= 4:4.8.0)；然而：
  未安装软件包 libqtcore4:amd64。
 synergy 依赖于 libqtgui4 (>= 4:4.8.0)；然而：
  未安装软件包 libqtgui4。

dpkg: 处理软件包 synergy (--install)时出错：
 依赖关系问题 - 仍未被配置
正在处理用于 gnome-menus (3.36.0-1ubuntu1) 的触发器 ...
正在处理用于 desktop-file-utils (0.24-1ubuntu2) 的触发器 ...
正在处理用于 mime-support (3.64ubuntu1) 的触发器 ...
正在处理用于 man-db (2.9.1-1) 的触发器 ...
在处理时有错误发生：
 synergy
提示没有安装依赖，下面安装依赖

xx@xx-Lenovo:~/tools/synergy/new-20200513$ sudo apt install  libqt4-dbus libqtcore4 libqtgui4  libqt4-network  libqt4-opengl libqtcore4 libqtgui4
正在读取软件包列表... 完成
正在分析软件包的依赖关系树       
正在读取状态信息... 完成       
没有可用的软件包 libqtcore4，但是它被其它的软件包引用了。
这可能意味着这个缺失的软件包可能已被废弃，
或者只能在其他发布源中找到
然而下列软件包会取代它：
  qtcore4-l10n qtchooser:i386 libqt5core5a:i386 qtchooser libqt5core5a

没有可用的软件包 libqtgui4，但是它被其它的软件包引用了。
这可能意味着这个缺失的软件包可能已被废弃，
或者只能在其他发布源中找到

没有可用的软件包 libqt4-dbus，但是它被其它的软件包引用了。
这可能意味着这个缺失的软件包可能已被废弃，
或者只能在其他发布源中找到

没有可用的软件包 libqt4-network，但是它被其它的软件包引用了。
这可能意味着这个缺失的软件包可能已被废弃，
或者只能在其他发布源中找到

E: 软件包 libqt4-dbus 没有可安装候选
E: 软件包 libqtcore4 没有可安装候选
E: 软件包 libqtgui4 没有可安装候选
E: 软件包 libqt4-network 没有可安装候选
E: 无法定位软件包 libqt4-opengl
E: 软件包 libqtcore4 没有可安装候选
E: 软件包 libqtgui4 没有可安装候选
提示没有可安装候选，修改ubuntu的软件源
备份/etc/apt/sources.list，然后把里面的内容修改成aliyun的软件源

deb http://mirrors.aliyun.com/ubuntu/ bionic main restricted universe multiverse
deb http://mirrors.aliyun.com/ubuntu/ bionic-security main restricted universe multiverse
deb http://mirrors.aliyun.com/ubuntu/ bionic-updates main restricted universe multiverse
deb http://mirrors.aliyun.com/ubuntu/ bionic-proposed main restricted universe multiverse
deb http://mirrors.aliyun.com/ubuntu/ bionic-backports main restricted universe multiverse
deb-src http://mirrors.aliyun.com/ubuntu/ bionic main restricted universe multiverse
deb-src http://mirrors.aliyun.com/ubuntu/ bionic-security main restricted universe multiverse
deb-src http://mirrors.aliyun.com/ubuntu/ bionic-updates main restricted universe
接着

sudo apt update
sudo apt upgrade
更新一下
然后，重新安装上面的依赖就好了
再次执行

sudo dpkg -i synergy_1.8.8-stable+dfsg.1-1build1_amd64.deb
至此，ubuntu下安装synergy，就安装完毕了，至于，怎么使用，大家可以自行搜索一下

作者：程空万里
链接：https://www.jianshu.com/p/a706d2ece694
来源：简书
著作权归作者所有。商业转载请联系作者获得授权，非商业转载请注明出处。
