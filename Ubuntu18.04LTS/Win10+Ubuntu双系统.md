# Win10+Ubuntu18.04LTS双系统
## 1 进入Ubuntu18.04LTS试用模式
1. 制作Ubuntu18.04LTSU盘启动盘
2. 从U盘启动
3. try Ubuntu
## 2 安装grub
1. 输入以下代码：
```shell
sudo fdisk -l               // 找到你Linux安装的分区，我这里是sda2
sudo mount /dev/sda2 /mnt   // 将分区挂在到mnt下
sudo grub-install --root-directory=/mnt /dev/sda
sudo update-grub
```
2. 执行完后，重启电脑。进入BIOS，启动菜单，选择第一项（即你安装Linux的硬盘，视情况而定）
## 3 完成上述步骤后，通常可以正常引导系统启动了
1. 如果还是不行，执行步骤1，进入Ubuntu试用模式，通过手机**共享网络**，执行以下代码：
```shell
sudo add-apt-repository ppa:yannubuntu/boot-repair
sudo apt-get update
sudo apt-get install -y boot-repair && (boot-repair &)
```
2. 此时会打开应用，点击推荐修复，然后等待。在这个步骤完成后，重启机器，你就可以正常引导系统启动了。
