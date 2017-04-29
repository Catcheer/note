### 常用命令行

ls   列出目录下文件

mkdir [name]创建文件夹  

mkdir -p [name] 创建不存在的文件夹

cd  切换目录

Ios 系统下 Data.parese() bug  Ios 系统Data.parse日期中间的- 需替换为/  否则无法解析

win系统 node版本管理 nvm

```
windows系统安装nvm https://github.com/coreybutler/nvm-windows
```

git config

```
$ git config --global user.name "Your Name"
$ git config --global user.email "email@example.com"
```

### git ssh

在继续阅读后续内容前，请自行注册GitHub账号。由于你的本地Git仓库和GitHub仓库之间的传输是通过SSH加密的，所以，需要一点设置：

第1步：创建SSH Key。在用户主目录下，看看有没有.ssh目录，如果有，再看看这个目录下有没有id_rsa和id_rsa.pub这两个文件，如果已经有了，可直接跳到下一步。如果没有，打开Shell（Windows下打开Git Bash），创建SSH Key：

$ ssh-keygen -t rsa -C "youremail@example.com"
你需要把邮件地址换成你自己的邮件地址，然后一路回车，使用默认值即可，由于这个Key也不是用于军事目的，所以也无需设置密码。

如果一切顺利的话，可以在用户主目录里找到.ssh目录，里面有id_rsa和id_rsa.pub两个文件，这两个就是SSH Key的秘钥对，id_rsa是私钥，不能泄露出去，id_rsa.pub是公钥，可以放心地告诉任何人。

第2步：登陆GitHub，打开“Account settings”，“SSH Keys”页面：

然后，点“Add SSH Key”，填上任意Title，在Key文本框里粘贴id_rsa.pub文件的内容：
