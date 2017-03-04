# Learn webpack

### webpack 编译css 

> css-loader 是将css模块打包，style-loader是将打包后的css添加到html的head


```
webpack hello.js hello.bundle.js --module-bind 'css=style-loader!css-loader' 
```

### webpack 监听更新  制动打包 

```
webpack hello.js hello.bundle.js --module-bind 'css=style-loader!css-loader' --watch
```

### npm包管理文件(package.json)配置webpack参数

> webpack --config webpack.config.js指定webpack配置文件(默认为webpack.config.js)

> --progress 显示打包进程 百分比

> --display-modules 显示模块

> --colors 彩色显示

> --display-reason 显示打包该模块的原因

```
"webpack":"webpack --config webpack.config.js --progress --display-modules --colors --display-reason"
```

### 多入口文件

> [name]对应entry中key(本例中是main,a)，hash是本次打包的hash值

```
	module.exports = {
    entry:{
        main:"./src/script/main.js",
        a:"./src/script/a.js"
    },
    output:{
        path:"./dist/js",
        filename:"[name]-[hash].js"
    }
}

```
> 运行结果

![](img/res1.jpg)