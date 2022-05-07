# Windows ssh认证
```git
ssh-keygen -t rsa -C "mayonglong07@gmail.com"
git config --global user.name "自定义用户名" 
git config --global user.email "邮箱"

```
# Ubuntu ssh认证
```text
cd .ssh
ssh-keygen -t rsa -C "mayonglong07@gmail.com"
cat .ssh/rsa.pub
git config --global user.name "mayonglong"
git config --global user.email "mayonglong07@gmail.com"
git config --global core.editor vim
git config --list
```
# ssh 免密
```text
一、环境说明
目前有两台Ubuntu 服务器

server 1：47.105.146.74
server 2：39.108.250.186
二、目标
server 1 登录 server 2 不需要输入密码；server 2 登录 server 1也不需要密码

三、实现server 1 登录 server 2 不需要输入密码
操作server 1

3.1 生成公钥
#最后是量个单引号，表示不设置密码，-t：指定要创建的密钥类型
ssh-keygen -t rsa -P '' 
按回车继续，即可生成公钥文件

3.2 分发公钥到目标机器（server 2）
ssh-copy-id -i ~/.ssh/id_rsa.pub root@39.108.250.186
输入server 2的root访问密码

3、测试
ssh 39.108.250.186
从server 1登录到server 2了

四、实现server 2 登录 server 1 不需要输入密码
操作步骤和server 1 登录 server 2 不需要输入密码一样
```
# 解决远程连接ssh的问题方案
```text
windows机器上装了个putty来连ssh，winscp来copy文件到jetson
```
