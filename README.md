# xiange-linux
Xiange Linux distribution (LiveUSB)

(Chines)
弦歌Linux 工具盘 2020.10

可以直接USB启动, UEFI模式或legacy模式均可，但要关闭安全启动。(用户名: xiange  密码: xiange 超级用户密码: xiange)

弦歌Linux是一个完全基于Wayland/Sway的Linux发行版，内涵500多个开源软件包，占U盘空间2.5G.

包管理器: 	gpkg, 基于源码的精简安全高效的元包管理器，可以记录每个安装包每个文件的md5sum, 并提供校验功能，同时记录软件编译过程中的信息，以便查看。
窗口管理:   wlroots/sway+waybar, lavalauncher
文档处理:	libreoffice, 自由开放的文档/表格/展示/图框编辑系统。
文件管理:   精简且全能的pcmanfm
音视播放:   支持wayland的mpv, 支持多种视频格式。
音视处理: 	 全能的瑞士军刀ffmpeg.
浏览器:	 支持wayland的firefox.
图形库:	支持wayland的gtk3, qt5, sdl2
pdf查看:	evince
光盘刻录:	 Brasero
3D测试:	 glmark2-wayland
文本编辑:    vim (带youcompleteme插件，verilog语法插件)
邮件系统:	 支持wayland的claws-mail
中文输入: 	  支持wayland的fcitx5(尚无候选字窗口)
支持的文件系统:  ext, ntfs, fat, exfat, squashfs
VNC客户端:  vinagre
系统查看器:  lspci,lsusb,dmidecode
网络工具:  	   网路嗅探 nmap, 
	   网路分析 wireshark, 
	   文件下载 filezilla, transmission, wget
游戏工具:	   支持wayland的街机模拟器 mame
	   支持wayland的超任模拟器 snex9x
	   Open GL ES和vulkan
虚拟机: 	qemu, 可以虚拟安装windows

安装运行说明:

1. 下载xiange-liveusb文件(Xiange-liveUSB-XXX.tar.gz)

2. 解压，生成image文件(tar, 或windows解压工具)

3. 用dd写入U盘 (4G即可, 实际占用3.5G)
	dd if=xiange-liveusb-XXXX.img of=/dev/sdX 
	如sdb, sdc等

  如果有pv工具，可以用pv显示进度: 
	pv xiange-liveusb-XXX.img | dd of=/dev/sdX

  在Windows系统下，需要U盘写入工具， 以下是一个例子:
	https://sourceforge.net/projects/win32diskimager/

  请注意一定要先解压再写入。

4. BIOS设置里取消安全启动，允许启动U盘

4. 从U盘启动




快捷键说明:

Win+q 		退出当前程序（重要!! sway窗口没有关闭按钮，请记住这个快捷键)
Win+数字键[0-9]	切换工作区0-9
Win+Shift+数字键	移动当前窗口到工作区
Win+Enter	启动终端
Win+f		启动firefox
Win+Shift+f 	切换全屏
Win+v		纵向切分窗口
Win+b		横向切分窗口
Win+w		切换窗口布局:标签
Win+s		切换窗口布局:堆叠
Win+e		切换窗口布局:平铺
Win+方向键	切换窗口焦点
Ctrl+Space 	启动输入法fcitx5
左Shift		切换输入法
Win+Shift+c	换桌面（从/usr/share/wallpapers随机取一张)
PrScrn		整个屏幕抓图，图片放在~/目录
Win+PrScrn	选择矩形框抓图，图片放在~/目录


包管理器gpkg说明:

gpkg -I		显示所有安装的软件包, 可以配合 sort -n 和 nl使用， 如 gpkg -I | sort -n | nl 按时间排序并计数
gpkg -s name	搜索并显示软件包信息
gpkg -l name 	列出软件包的所有文件
gpkg -c name 	校验软件包，看看已安装的文件是不是被修改
gpkg -i name	安装软件包
gpkg -D name	删除软件包
gpkg -p name	查看软件包的依赖项
gpkg -ib name.xgp	安装二进制包
gpkg -ub name.xgp	升级二进制包
gpkg new type/name-version  添加新的编译脚本


软件的编译脚本在/var/xiange/xglibs，照模板写即可。

配置文件说明:

1. lavalauncher: ~/.config/lavalauncher 可以添加删除启动栏的程序。
2. waybar: /etc/xdg/warbar/config
3. sway:   /etc/sway/config
4. 桌面全局环境变量设置: /usr/bin/sway-run

下载地址:
1. SourceForge
	https://sourceforge.net/projects/xiangelinux/files/latest/download
	
2. baiduNetDisk:

链接:https://pan.baidu.com/s/1LVHKgi9W0JrELBmMuOxJOg 提取码:eyn4
从里面找最新的发行版即可。


