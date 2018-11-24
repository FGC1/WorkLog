# Linux开机进入initramfs无法开机
# 1 原因
通常是因为磁盘文件受损
# 2 进入Ubuntu试用模式
```shell
sudo fdisk -l       // 指令找到要修复的磁盘，这里假设为sda1
umount /dev/sda1    // 卸载sda1
fsck -t ext4 /dev/sda1  // 检查、修复，其中ext4根据自己的文件系统而异（ext3或ext4），对于提示，一路y下去就行
```
完事后一般重启就可以了