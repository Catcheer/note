
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


目前，在GitHub上的这个learngit仓库还是空的，GitHub告诉我们，可以从这个仓库克隆出新的仓库，也可以把一个已有的本地仓库与之关联，然后，把本地仓库的内容推送到GitHub仓库。

现在，我们根据GitHub的提示，在本地的learngit仓库下运行命令：
```
$ git remote add origin git@github.com:Catcheer/myNotes.git
```
移除关联
```
$ git remote rm origin
```

请千万注意，把上面的michaelliao替换成你自己的GitHub账户名，否则，你在本地关联的就是我的远程库，关联没有问题，但是你以后推送是推不上去的，因为你的SSH Key公钥不在我的账户列表中。

添加后，远程库的名字就是origin，这是Git默认的叫法，也可以改成别的，但是origin这个名字一看就知道是远程库。

下一步，就可以把本地库的所有内容推送到远程库上：




### chrome 中调试node

npm install -g devtool

devtool name --watch

### Charles抓https包 设置 
 
 抓https包时需安装证书(http包不用安装)
 
 help>ssl proxying>....
 
 安装证书后 iphone手机上开启证书信任（通用>关于本机>证书信任设置） 否则无法抓取
 
 ### 树状型显示github项目工具 Octotree（chrome 扩展工具)





