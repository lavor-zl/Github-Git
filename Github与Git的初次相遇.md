#Github与Git的初次相遇（Windows版）  
***  
Github是基于Git进行代码托管服务的，不会Git，就不能真正发挥Github强大的作用，无Git不Github。  

#1. 工具的准备  
***  
[Git工具下载](https://git-scm.com/download/),以默认方式进行安装。  

为了以后可以方便地在`cmd`下面使用git，我们可以配置一些环境变量，在系统变量中的“PATH”中加上`“E:\Program Files\Git\cmd”`，其中`“E:\Program Files\Git”`是我的git安装目录。  

#2. git上配置github环境  
***  
- 在任意目录下面右击鼠标，点击“Git Bash Here”进入Bash命令行  
![](http://i.imgur.com/qaZHeSx.png)  
![](http://i.imgur.com/NPPJHhJ.png)  

- 配置全局用户名：`git config –global user.name 你的用户名（一般是github用户名）`  
![](http://i.imgur.com/Lr0N0Fx.png)  

- 配置全局邮箱：`git config –global user.email 你的邮箱（一般是github认证邮箱）`  
![](http://i.imgur.com/atuZQy7.png)  

- 生成SSH秘钥及相关配置  
生成SSH秘钥：`ssh-keygen -t rsa -C 你的github认证邮箱`  
![](http://i.imgur.com/wOsY1ZF.png)  
之后一直按“Enter”就行了，秘钥会生成在默认目录（当前用户目录下面的.ssh目录下面）：  
比如我的秘钥生成在`C:\Users\shitian\.ssh`目录下面  
我们看到`.ssh`目录下面有三个文件，`id_rsa`，`id_rsa.pub`，`known_hosts`。    
打开我们的github，进入设置页面：  
![](http://i.imgur.com/cZ9lmtn.png)  
![](http://i.imgur.com/O5d2lgl.png)  
![](http://i.imgur.com/Zr1YGJ4.png)  
![](http://i.imgur.com/XO29xC8.png)  
![](http://i.imgur.com/z9QFmRn.png)  
至此，SSH秘钥就配置完成了，git上配置github环境也彻底完成了。  

#3. git对github的简单操作  
***  
##1. 从github上clone一个项目到本地   
***  
命令：`git clone 要clone的git仓库`  
![](http://i.imgur.com/L3k3cVc.png)  

##2. 在本地初始化一个git仓库   
***  
命令：`git init`  
![](http://i.imgur.com/t8oBR4P.png)  

##3. 添加与本地仓库联系的远程仓库  
***  
命令：`git remote add 给远程仓库起的别名  关联的远程仓库`  
![](http://i.imgur.com/VME0ZE5.png)  

##4. 添加本地仓库修改过的文件  
***  
- 添加指定修改后的文件（包括文件夹）到缓存  
  命令：`git add 文件名`  
  ![](http://i.imgur.com/tsow1fS.png)
- 添加所有修改后的文件到缓存  
  命令：`git add .`  
  ![](http://i.imgur.com/FnVzIcy.png)  

##5. 提交修改  
***  
命令：`git commit -m "你的提交说明"`  
![](http://i.imgur.com/3Zojk80.png)  

##6. 将修改后的内容上传到远程仓库  
***  
命令：`git push 远程仓库别名 所要上传到远程仓库的分支名`  
![](http://i.imgur.com/owwV7hx.png)  

##7. 从远程仓库下载最新内容到本地仓库  
***  
命令：`git pull 远程仓库别名 所要下载内容所在远程仓库的分支名`   
![](http://i.imgur.com/3sLrFhQ.png)    

##8. 删除本地仓库与远程仓库的关联  
***  
命令：`git remote rm 给远程仓库起的别名`   
![](http://i.imgur.com/9g9ayNk.png)  



