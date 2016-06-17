#Github征途  
***  
我们是如何操作github仓库的呢。让我们踏上github的征途看看吧。  
此篇文章主要讲解github上面一些常见的操作。    

#1. 在本地修改从github上clone的仓库后上传到github  
***  
从github上clone一个自己的仓库到本地： 
 
    git clone 自己的github仓库（https或者SSH仓库）  
修改本地仓库中的文件，将所有修改的文件添加到暂存区中  

    git add .
提交修改  

    git commit -m "提交说明"  
将本地仓库修改的文件都上传到github仓库  

    git push origin master  

#2. fork别人的github仓库后，clone到本地，修改后上传到github，然后提交Pull Request请求  
***  
在github上fork一个别人的仓库到自己的github中，clone自己的该仓库到本地：

    git clone 自己的github仓库（https或者SSH仓库）  
修改本地仓库中的文件，将所有修改的文件添加到暂存区中  

    git add .
提交修改  

    git commit -m "提交说明"  
将本地仓库修改的文件都上传到github仓库  

    git push origin master  
到自己github的该仓库页面来进行pull request请求  
![](http://i.imgur.com/ojIatJT.png)  
![](http://i.imgur.com/QnExVRV.png)
![](http://i.imgur.com/y2woZcB.png)  
![](http://i.imgur.com/OThZRo5.png)  

#3. 处理别人提交到自己仓库的pull request  
***  
![](http://i.imgur.com/WC9rB9E.png)  
![](http://i.imgur.com/Ot8ZiGe.png)  
![](http://i.imgur.com/RxFUl2o.png)
![](http://i.imgur.com/9d2b7Fg.png)  
![](http://i.imgur.com/nCEEkHX.png)  

#4. 使用别人的项目发现bug或者遇到问题，可以去别人的仓库提问  
***  
![](http://i.imgur.com/Av2DBHt.png)  
![](http://i.imgur.com/0mvwQK6.png)  
![](http://i.imgur.com/wK86cmM.png)  

#5. 处理别人在自己仓库的提问  
***  
![](http://i.imgur.com/K2BawC8.png)  
![](http://i.imgur.com/f2XSda3.png)  

#6. 为自己的仓库创建Wiki  
***  
![](http://i.imgur.com/lCx8rng.png)  
![](http://i.imgur.com/dtlNQ8V.png)  
![](http://i.imgur.com/PhVNrHr.png)  

#7. 分支管理   
***  
![](http://i.imgur.com/1lmhvjA.png)  
![](http://i.imgur.com/JDJjUuL.png)  

#8. 发布管理  
***  
![](http://i.imgur.com/72t4Sz5.png)  
![](http://i.imgur.com/XyZZTEd.png)  
![](http://i.imgur.com/YPdLT7y.png)  
![](http://i.imgur.com/Z1XcThh.png)  
![](http://i.imgur.com/VllpU46.png)  

标记和发布是共存的。  
我们如何在使用git来添加标记并上传到github。  
- 为当前提交添加标记  
```
git tag "v1.1"  
```  
- 添加修改当暂存区  
```  
git add .  
```  
- 提交修改  
```  
git commit -m "添加标记"  
```  
- 推送提交到远程仓库。并且顺带推送标记  
```
git push --tags origin master
```  

#9. Gist管理  
***  
gist是用来即时分享代码，注释，和片段代码的。  
![](http://i.imgur.com/i1cPnDq.png)  
![](http://i.imgur.com/OKZNLSM.png)  
![](http://i.imgur.com/MOAx6rl.png)  

#10. 重要文件说明  
***  
github仓库的根目录一般有3个重要文件：  
- `README.md`：显示在仓库下面的说明文档，是由Markdown编写  
- `LICENSE`：代表本仓库所遵循的开源协议  
- `.gitignore`：代表git忽略的文件  

Markdown语法：[Mastering Markdown](https://guides.github.com/features/mastering-markdown/)  

`.gitignore`文件中每一行代表一个忽略文件，支持`*`通配符：  
- 忽略某个文件（比如忽略“.gradle”文件）  
```  
.gradle  
```  
- 忽略某个目录（比如忽略"build"目录）  
```  
/build  
```  
- 忽略某类文件（比如忽略“.iml”后缀的文件）  
```  
*.iml  
```  
- 不忽略某个文件（比如“.iml”后缀的文件被忽略了，但是我们不希望“my.iml”这个文件被忽略）  
```  
!my.iml  
```  




