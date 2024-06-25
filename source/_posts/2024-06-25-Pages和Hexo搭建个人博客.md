---

title: 使用GitHub Pages和Hexo搭建个人博客
date: 2024-06-25 20:14:00
tags: 
- 博客
- GitHub Pages
- Hexo
- Vscode
categories:
- 教程

---

使用GitHub Pages与Hexo搭建个人博客
===========
看了许多利用GitHub Pages建立个人博客的例子，使用的比较多的就是**jkeyll**和**Hexo**，最终选择了使用**Hexo**搭建我的博客  

参考[Hexo官方网站](https://hexo.io/zh-cn/)，需要先安装以下应用程序  
- **[Node.js](https://nodejs.org)**  
- **[Git](https://git-scm.com)**  

安装Git
-----
不同的操作系统拥有不同的安装程序  
- Windows一般使用[安装包](https://git-scm.com/download/win)  
- Mac系统可以寻找Homebrew或者对应安装程序
- Linux则可以通过apt/yum包管理器来进行安装  
在控制台中键入  
`sudo apt-get install git-core`  
或者  
`sudo yum install git-core`  

安装Node.js
------  
直接访问[Node.js官方提供的下载网址](https://nodejs.org/zh-cn/download/)  
选择你自己的操作系统和版本，按提示操作即可  
这里建议Windows和Mac使用安装程序安装  
Linux使用nvm进行包管理（安装完记得source ~/.bashrc）

安装Hexo并建立项目
---
直接使用npm安装Hexo  

    npm install -g hexo-cli  

然后新建一个空目录，用于Hexo的初始化  

    mkdir main
    hexo init main
    cd main
    npm install

这样你的Hexo项目就建立好了，各文件的作用请参考[文档](https://hexo.io/zh-cn/docs/setup)  
随后就可以为你的Blog选一个主题了，官方提供了一个[主题列表](https://hexo.io/themes/)，你可以在里面挑选自己喜欢的样式  
当然也可以直接Google或者Github搜索，有一些主题应该是没有被收录的  
随后进入主题的网站按照教程来即可，一般导入主题方法如下  
本次采用[Fluid主题](https://github.com/fluid-dev/hexo-theme-fluid)  

**1. 下载解压**  
下载主题文件并解压到themes目录下，将解压出的文件夹命名为主题名  
**2. 修改内容**  
修改Hexo目录中的_config.yml  

    theme：主题名  
    language: zh-CN
**3.其他事项**  
有些主题需要自己创建部分内容，例如Fluid主题就需要自己创建About页面

尝试本地运行
---------
在项目目录，例如main下输入  

    hexo g
    或者
    hexo generate
该命令会生成对应的静态文件在public中  
控制台中输入  

    hexo s
    或者
    hexo server
即可启动服务  
在浏览器中打开对应网址<http://localhost:4000>即可预览博客  
每次修改博客内容或者配置想要预览的时候，请先使用`hexo clean`清除本地文件，然后重新生成并启动服务
