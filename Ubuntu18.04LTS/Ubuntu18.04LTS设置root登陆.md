# 1 Ubuntu18.04LTS设置root登陆

## 1 首先获得临时的root权限
```
sudo -s
```

## 2 先创建root账户
```
sudo passwd root
```

## 3 修改配置文件
文件路径/usr/share/lightdm/lightdm.conf.d/50-unity-greeter.conf
```
gedit /usr/share/lightdm/lightdm.conf.d/50-unity-greeter.conf
```
打开后，在文档末尾输入
```
1. greeter-show-manual-login=true
2. all-guest=false
```

## 4 去除gdm登陆用户名检测
修改/etc/pam.d/gdm-autologin文件
```
gedit /etc/pam.d/gdm-autologin
```
删除或注释掉以下语句
```
auth required pam_succeed_if.so user!=root quiet_success
```
修改/etc/pam.d/gdm-password文件
```
gedit /etc/pam.d/gdm-password
```
同样删除或注释掉上面的语句
## 5 修改/root/.profile文件
```
gedit /root/.profile
```
文档最后一行mesg n || true 前面添加tty -s && 即 tty -s && mesg n || true

## 6 重启系统
终端输入命令
```
reboot
```
重启完成后，登陆界面选择“未列出”，之后用户名输入root进行登陆即可

# 2 Ubuntu18.04LTS无WIFI适配器

## 1 打开软件可更新
单击一个九宫个样式的图标，在弹出的界面中可以找到软件和更新应用

## 2 Broadcom Limited: BCM43142 802.11b/g/n
切换到附加驱动选项卡，将Broadcom Limited: BCM43142 802.11b/g/n设置为使用Broadcom 802.11 Linux STA w无线驱动源码 来自bcmwl-kernel-source(专有)

# 3 创建QtCreator桌面快捷方式
## 1 创建QtCreator.desktop文件
进入/usr/share/applications目录编辑一desktop文档
```
sudo vim /usr/share/applications/QtCreator.desktop
```
在QtCreator.desktop文件中添加如下内容
```
1 [Desktop Entry]
2 Type=Application
3 Version=0.9.4
4 Name=QtCreator
5 Comment=Run Qt Creator #鼠标放上去时的文字提示
6 Icon=/home/yan/qtsdk-2009.03/share/pixmaps/qtcreator_logo_48.png #要显示的图标绝对路径
7 Exec=/home/yan/qtsdk-2009.03/bin/qtcreator #启动程序
8 Path=/home/yan/qtsdk-2009.03/bin
9 Terminal=false
10 Categories=GNOME;GTK;System; #应用程序在菜单项中的分类，在我的系统中在 应用程序-》系统工具下
```