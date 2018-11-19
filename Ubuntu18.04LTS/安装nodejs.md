# 安装Node.js

## 1 下载Node.js安装包
从https://nodejs.org/en/download/下载对应版本的Node.js安装包

下载后得到node-v10.13.0-linux-x64.tar.xz

## 2 解压node-v10.13.0-linux-x64.tar.xz
终端进入到Node.js安装包所在文件夹，执行命令
```
sudo xz -d node-v10.13.0-linux-x64.tar.xz
```
得到node-v10.13.0-linux-x64.tar

## 3 解压node-v10.13.0-linux-x64.tar到/usr目录下
执行命令
```
tar xvf node-v10.13.0-linux-x64.tar -C /usr
``` 
## 4 将/usr/node-v10.13.0-linux-x64/bin下的node和npm创建软连接到usr/local/bin
执行命令
```
ln -s /usr/node-v10.13.0-linux-x64/bin/node /usr/local/bin/node
ln -s /usr/node-v10.13.0-linux-x64/bin/nmp /usr/local/bin/npm
```
