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
