# samba简介
```text
samba，是一个基于GPL协议的自由软件。它重新实现了SMB/CIFS协议，可以在各个平台共享文件和打印机。

1991年，还是大学生的Andrew Tridgwell，有三台机器，分别是Microsoft的DOS系统、DEC的Digital Unix系统、以及Sun的Unix系统。当时的技术无法让三者共享文件。为此，他开发了samba并将其开源。

本来改名为smbserver，但是一家商业公司注册了SMBServer商标。他被告知不能使用。于是执行了grep -i '^s.*m.*b' /usr/share/dict/words，从中选择了samba这个词
```
# 安装
```
yum -y install samba samba-client samba-common
```
# 修改 samba 的配置文件
```
vim 在文件参数后面接 + 可以直接打开到文件末尾，相当于在命令行模式下按 G，然后直接按 o 可以在下一行插入下面内容。

sudo vim /etc/samba/smb.conf +
testparm # 测试smb.conf配置是否正确
testparm –v # 命令可以详细的列出smb.conf支持的配置参数
```
# 配置说明
```
[myshare] 
comment = My share 
path = /home/public                     # 共享路径 
browseable = Yes                        # 可以被浏览，就是在网络邻居中能看到共享名 
read only = No                          # 可读写 
guest ok = Yes                          # 允许匿名访问，这个也需要设置，否则匿名无法访问 
valid users = samba liuag guest         # 有效的用户和组 
invalid users = liuben                  # 无效用户和组    
read list = samba                       # 只读用户和组(如果read only = No，只读用户需要在此设置) 
write list = liuag                      # 可读写用户和组(如果read only = Yes，可读写用户需要在此设置) 
allow hosts = 192.168.100.236    # 允许访问主机列表，支持通配符 
deny hosts = 192.168.100.0/24    # 禁止访问主机列表，支持通配符 


security = user #这里指定samba的安全等级。关于安全等级有四种：
  # share：用户不需要账户及密码即可登录samba服务器
  # user：由提供服务的samba服务器负责检查账户及密码（默认）
  # server：检查账户及密码的工作由另一台windows或samba服务器负责
  # domain：指定windows域控制服务器来验证用户的账户及密码。
```

# 重启服务
```
systemctl restart smb
systemctl reload smb
systemctl status smb
```
# 查看安装状况
```
rpm -qa|grep samba
```
# 设置开机自启动
```
chkconfig --level 35 smb on             //在3、5级别上自动运行samba服务
```
# samba用户管理
```
pdbedit –a username：新建Samba账户。
pdbedit –x username：删除Samba账户。
pdbedit –L：列出Samba用户列表，读取passdb.tdb数据库文件。
pdbedit –Lv：列出Samba用户列表的详细信息。
pdbedit –c “[D]” –u username：暂停该Samba用户的账号。
pdbedit –c “[]” –u username：恢复该Samba用户的账号。


smbpasswd -a 增加用户（要增加的用户必须以是系统用户）   
smbpasswd -d 冻结用户，就是这个用户不能在登录了   
smbpasswd -e 恢复用户，解冻用户，让冻结的用户可以在使用   
smbpasswd -n 把用户的密码设置成空.   
             要在global中写入 null passwords -true   
smbpasswd -x  删除用户  
netstat -anlp | grep samba
```
# 关闭防火墙
```
systemctl stop firewalld        #关闭防火墙
systemctl disable firewalld        #开机禁用防火墙
如何让Finder不在远程连接时产生.DS_Store打开Mac的Terminal，输入

defaults write com.apple.desktopservices DSDontWriteNetworkStores true
然后重启Mac，再试试远程连接。
```
# 错误解决
```
增加samba用户提示Failed to add entry for user
[root@ubuntu ~]# smbpasswd -a wcj
New SMB password:
Retype new SMB password:
Failed to add entry for user wcj.

解决办法:

这是因为没有加相应的系统账号，所以会提示Failed to add entry for user的错误，只需增加相应的系统账号wcj就可以了:

sudo useradd wcj useradd -g test wcj 注：新建wcj用户并增加到test工作组

而且samba的登录密码可以和本机登录密码不一样。

sudo touch /etc/samba/smbpasswd
sudo smbpasswd -a wcj

smbclient -L \\192.168.0.104 -U username
smbclient //192.168.60.231/username #登录Samba服务器
```
# 我的配置
[global]
    workgroup = MYGROUP
    server string = Samba Server Version %v

    # log files split per-machine:
    log file = /var/log/samba/log.%m
    # maximum size of 50KB per log file, then rotate:
    max log size = 50

    security = user
    passdb backend = tdbsam

    load printers = yes
    cups options = raw

    printcap name = /dev/null
    ;printable = yes

    directory mask =0777
    force directorymode = 0777
    directorysecurity mask = 0777
    force directorysecurity mode = 0777
    create mask =0777
    force createmode = 0777
    security mask =0777
    force securitymode = 0777

[homes]
    comment = Home Directories
    browseable = no
    writable = yes
;   valid users = %S
;   valid users = MYDOMAIN\%S
[dev]
    path = /home/wangchuajiang/shared
    writeable = yes
    browseable = yes
    write list = wangchujiang
session setup failed
samba报错：session setup failed: NT_STATUS_LOGON_FAILURE 解决

# 错误三
Failed to retrieve printer list: NT_STATUS_UNSUCCESSFUL解决

printing = bsd
printcap name = /dev/null
错误四
security不再支持share
WARNING: Ignoring invalid value 'share' forparameter 'security'

# 错误五
请检查服务器名称或 IP 地址，然后再试一次。如果问题持续发生，请联系系统管理员。

解决办法：重启电脑

# 错误六
# 解決方法：於smb.conf中加入以下設定 
load printers = no 
printing = bsd 
printcap name = /dev/null 
disable spoolss = yes 
about:Unable to connect to CUPS server localhost:631 - Connection refused

# 错误六
STATUS=daemon 'smbd' finished starting up and ready to serve connections

# 参考
samba官网
Mac连接远程Linux管理文件（samba）
简单的配置 samba 共享
Ubuntu下配置samba服务器
linux6-samba服务器＆SSH工具
CentOS7安装配置SAMBA服务器
