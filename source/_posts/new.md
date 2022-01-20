# 部署环境
* 安装[Git](https://gitforwindows.org/)
* 安装[Node.js](https://nodejs.org/en/download/)
* 使用npm安装Hexo
********
新建站点文件夹blog,在文件夹目录下运行命令`npm install -g hexo-cli`，使用`hexo -v`查看版本检验是否安装成功。
运行 `hexo init`初始化hexo。
********
目录结构：
* node_modules: 依赖包
* public：存放生成的页面
* scaffolds：生成文章的一些模板
* source：用来存放文章
* themes：主题
* _config.yml: 博客的配置文件
********
启动hexo服务
`hexo s`

浏览器输入`localhost:4000`查看博客
********
在GitHub创建个人仓库

创建一个和用户名相同的仓库，后面加.github.io
********
生成ssh添加到GitHub

打开git bash运行
```
git config --global user.name "yourname"
git config --global user.email "youremail"
```
将其中的yourname和youremail更改为自己的github用户名和邮箱
********
使用
```
git config user.name
git config user.email
```
检查用户名和邮箱是否输入正确
********
创建SSH

运行(连续按多次回车)
```
ssh-keygen -t rsa -C "youremail"
```

在安装git的同级目录下找到.ssh文件夹
* `id_rsa` ：私人密钥
* `id_rsa.pub` ：公共秘钥

将公钥放置到GitHub中
> setting -> New SSH key
把id_rsa.pub里面的信息复制到Key里

在git bash中，查看是否成功
`ssh -T git@github.com`

## 将hexo部署到GitHub
打开站点配置文件 _config.yml
```
deploy:
  type: git
  repo: https://github.com/YourgithubName/YourgithubName.github.io.git
  branch: master
```
安装deploy-git，也就是部署的命令，这样才能用命令部署到GitHub
`npm install hexo-deployer-git --save`

> `hexo c` 清理  
> `hexo g` 生成  
> `hexo s` 启动本地服务  
> `hexo d` 部署到远端（可能需要登录）  
*****

浏览器输入`http://yourname.github.io`查看是否成功
