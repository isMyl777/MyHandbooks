# 学习网站
<https://linux.ftqq.com/c/ps.html>

# Linux命令
```text
查看Linux命令帮助信息-关键词：help whatis info which whereis man 
Linux文件目录管理-关键词：cd ls pwd mkdir rmdir tree touch ln rename stat file chmod chown locate find cp mv rm
Linux文件内容查看命令-关键词：cat head tail more less sed vi vim grep
```
#linux目录结构
```text
/bin  bin是二进制文件的缩写，这个目录存放在最经常使用的命令
/boot 存放启动linux时使用的核心文件，包括一些连接文件以及镜像文件
/dev 存放linux的外部设备，在linux中访问设备的方式和访问文件的方式是相同的
/etc 存放所有的系统管理所需要的配置文件和子目录
/home  用户的主目录
/lib 存放着系统最基本的动态连接共享库，作用DLL文件。几乎所有的应用程序都需要用到这些共享库
/root 该目录为系统管理员，也称作超级权限者的用户主目录
/sbin super user的意思，存放的是系统管理员使用的系统管理程序
/usr/bin 系统用户使用的应用程序
/tmp 存放临时文件
/src  该目录存放一些服务启动之后需要提取的数据
/usr/src 内核源代码默认的放置目录
/var 存放日志文件

```
# 移动文件和重命名
```text
mv oldname newname
mv filename newpath
```
# linux tree命令
```text
Linux tree命令用于以树状图列出目录的内容
执行tree指令，它会列出指定目录下的所有文件，包括子目录里的文件
```
~~删除线~~
#
```text
cat task_config.json |head -n 1024 > 1.json
读取task config 1024行之前的内容生成新文件1.json
cat tail.json >> 1.json
tail.json 内容添加到1.json文件后面
find . -name "*.onnx" | xargs -i cp {} ./tmp
拷贝当前目录下所有onnx文件到上级文件夹tmp下面
sed -i s/"app05"/"cdjyc"/g task_config.json

```
# ubuntu防火墙
```shell
1、Alt+T打开终端，输入sudo ufw status回车，查看防火墙状态，inactive是关闭，active是开启。
2、使用sudo ufw enable开启防火墙。
3、使用sudo ufw disable关闭防火墙。
```
# ffmpeg 安装
```shell
sudo apt install ffmpeg  
ffmpeg -rtsp_transport tcp -i rtsp://admin:gx123456@172.36.91.169:554/Streaming/Channels/101?transportmode=unicast -t 1200 -vcodec copy v1.avi
```
# 打开终端
```
打开终端 ctrl+ alt + t
ls 显示文件夹目录
pwd 显示当前路径
tree 树形展开目录 示例 tree Desktop
清除终端内容 clear
cd 目录 切换到指定目录
cd ~ 切换到当前用户的主目录
cd .. 切换到上一级目录
cd . 切换到当前目录
cd - 切换到上一次目录
自动补全 按一次Tab是在自动补全，按2次是查看当前目录下有哪些子目录
touch 文件名 创建指定文件
mkdir 目录名 创建文件夹
rm 文件名 删除指定文件或者目录
rmdir 删除空目录
cp 拷贝文件、拷贝目录
mv 移动文件、移动目录、重命名
查看命令帮助 
--help 使用说明 命令 --help
man 使用说明： man 命令

```
