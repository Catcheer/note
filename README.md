
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
 
 
 ### form表单  enctype属性
 
 上传文件的表单中<form>要加属性enctype="multipart/form-data",

 其实form表单在你不写enctype属性时，也默认为其添加了enctype属性值，默认值是enctype="application/x- www-form-urlencoded".

 这个属性管理的是表单的MIME编码，共有三个值可选：

　　①application/x-www-form-urlencoded (默认值)

　　②multipart/form-data

　　③text/plain

　　其中①application/x-www-form-urlencoded是默认值，大家可能在AJAX里见过这 个：xmlHttp.setRequestHeader("Content-Type","application/x-www-form- urlencoded"); 这两个要做的是同一件事情，就是设置表单传输的编码。在AJAX里不写有可能会报错，但是在HTML的form表单里是可以不写 enctype="application/x-www-form-urlencoded"的，因为默认HTML表单就是这种传输编码类型。



②multipart-form-data是用来指定传输数据的特殊类型的，主要就是我们上传的非文本的内容，比如图片或者mp3等等。



③text/plain是纯文本传输的意思，在发送邮件时要设置这种编码类型，否则会出现接收时编码混乱的问题，网络上经常拿text/plain和 text/html做比较，其实这两个很好区分，前者用来传输纯文本文件，后者则是传递html代码的编码类型，



在发送头文件时才用得上。①和③都不能用 于上传文件，只有multipart/form-data才能完整的传递文件数据。

### process

你可以通过 process 这个全局对象来获取命令行中的参数。process 对象
  拥有一个名为 argv
  的属性，该属性是一个数组，数组中包含了整条命令的所有部分。
  
  命令行输入
  ```
  node program.js 1,2,3,4
  ```
会打得到
```
[ 'd:\\Program Files\\nodejs\\node.exe',
  'E:\\mySelfTest\\node\\program.js',
  '1,2,3,4' ]
```


### splice   slice

arr.slice(start,end)
+ arr中复制一份从start到end，不包括end
+ 返回值是复制出来的新的数组
+ 不改变源数组(arr)
+ 如果start，end只要其中一个为负数，则返回空数组

arr.splice(start,deleteCount,item1,item2,...)
+ arr从start开始删除deleteCount个元素，然后将item1,item2,...从start开始插入。
+ 返回值是一个包含删除的元素的数组
+ 原数组arr得到修改
+ 如果item1,item2,...不存在，则只删除，不添加新元素
+ 如果start为负数则转换为start+arr.length
+ deleteCount如果为负数，则将转化为0

### gulp-livereload实现文件修改时浏览器自动刷新

```
 var gulp = require('gulp'),
    less = require('gulp-less'),
    livereload = require('gulp-livereload');

gulp.task('less', function () {
    gulp.src("less/**/*.less")
        .pipe(less())
        .pipe(gulp.dest('css/'))
        .pipe(livereload());
});

gulp.task('watch', function () {
    livereload.listen();
    gulp.watch('less/**/*.less', ['less']);
});

gulp.task('default',['watch'])
```
serve建立本地服务器，并且浏览器安装livereload插件，安装livereload插件，安装livereload插件

### window 创建.gitignore文件

使用cmd，如

1，输入：copy con .gitignore 回车
2，输入 文件内容
3，ctrl + z 回车

如果文件没有内容直接跳过步骤 2 即可。



### 使用正则表达式的方法
方法	描述
exec	一个在字符串中执行查找匹配的RegExp方法，它返回一个数组（未匹配到则返回null）。
test	一个在字符串中测试是否匹配的RegExp方法，它返回true或false。
match	一个在字符串中执行查找匹配的String方法，它返回一个数组或者在未匹配到时返回null。
search	一个在字符串中测试匹配的String方法，它返回匹配到的位置索引，或者在失败时返回-1。
replace	一个在字符串中执行查找匹配的String方法，并且使用替换字符串替换掉匹配到的子字符串。
split	一个使用正则表达式或者一个固定字符串分隔一个字符串，并将分隔后的子字符串存储到数组中的String方法。

