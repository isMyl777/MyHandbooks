# virtualenv
```virtualenv可用于创建独立的 Python 环境，它会创建一个包含项目所必须要的执行文件。```

# 安装 virtualenv
```
$ pip install virtualenv
配置 pip 安装第三方库的镜像源地址
我们都知道，国内连接国外的服务器都会比较慢，有时候设置下载经常出现超时的情况。这时可以尝试使用国内优秀的豆瓣源镜像来安装。
```
# 使用豆瓣源安装 virtualenv
```
pip install -i https://pypi.douban.com/simple virtualenv
```
# virtualenv使用方法
```
如下命令表示在当前目录下创建一个名叫 env 的目录（虚拟环境），该目录下包含了独立的 Python 运行程序,以及 pip副本用于安装其他的 packge

virtualenv env
当然在创建 env 的时候可以选择 Python 解释器，例如：

virtualenv -p /usr/local/bin/python3 venv
默认情况下，虚拟环境会依赖系统环境中的 site packages，就是说系统中已经安装好的第三方 package 也会安装在虚拟环境中，如果不想依赖这些 package，那么可以加上参数 --no-site-packages 建立虚拟环境

virtualenv --no-site-packages [虚拟环境名称]
```
# 启动虚拟环境
```
cd ENV
source ./bin/activate
注意此时命令行会多一个(ENV)，ENV为虚拟环境名称，接下来所有模块都只会安装到这个虚拟的环境中去。
```
# 退出虚拟环境
```
deactivate
```
# 删除虚拟环境
```
如果想删除虚拟环境，那么直接运行rm -rf venv/命令即可。
```
# 安装（确保virtualenv已经安装）
```
pip install virtualenvwrapper
或者使用豆瓣源

pip install -i https://pypi.douban.com/simple virtualenvwrapper-win
注：安装需要在非虚拟环境下进行
```
# 创建虚拟机
```
mkvirtualenv env
创建虚拟环境完成后，会自动切换到创建的虚拟环境中

当然也可以指定虚拟机的 python 版本

mkvirtualenv env -p C:\python27\python.exe
```
# 列出虚拟环境列表
```
workon 或者 lsvirtualenv
```
# 启动/切换虚拟环境
```
使用 workon [virtual-name] 即可切换到对应的虚拟环境

workon [虚拟环境名称]
```
# 删除虚拟环境
```
rmvirtualenv [虚拟环境名称]
```
# 离开虚拟环境
```
和 virutalenv 一样的命令
deactivate
```
