#Git简明教程  
***  
#1. git四大域  
***  
git四大域：工作目录，暂存区，仓库，远程仓库。  
git对文件的操作都是在四大域上进行的，文件可以在四大域内与四大域间进行各种操作。（有一个例外，进行“git stash”系列操作时，文件可能被保存到四大域外的堆栈中）
![](http://i.imgur.com/UB94Upo.png)  

#2. git常用命令  
***  
![](http://i.imgur.com/jqW1Odo.png)  
##1. 设置  
***  
###1. `config`命令   
***  
- `git config --global user.name lavor`：配置全局用户名，若不要“--global”或者将“global”改为“local”则表示配置局部用户名  
- `git config --global user.email lavor@qq.com`：配置全局电子邮箱
- `git config --global alias.cm commit`:配置别名，为git命令配置别名，还可以配置复合操作，比如 `git config --global alias.pom 'push origin master'`注意复合操作中不可以带`-`与`""`  
- `git config --list`：显示所有配置信息 

###2. `help`命令  
***  
- `git help`：显示帮助信息，会显示一些常见git命令及其意义  

##2. 创建项目  
***  
###1. `init`命令  
***  
- `git init`：在本地初始化一个git仓库  

###2. `clone`命令  
***  
- `git clone git@github.com:lavor-zl/Github-Git.git`：从远程服务器克隆一个仓库到本地  

##3. 基本操作  
***  
###1. `add`命令  
***  
- `git add README`：添加工作目录的文件到暂存区  

###2. `status`命令  
***  
- `git status`：显示工作树的状态，一般有三种状态  
  - `Untracked files`：未被跟踪的文件，表示是工作目录新增加的文件  
  - `Changes not staged for commit`：工作目录中修改了文件，但是没有被添加到暂存区  
  - `Changes to be committed`:添加到暂存区的文件，等待提交  

###3. `commit`命令  
***  
- `git commit -m "提交消息"`：提交暂存区的文件，带有提交消息  
- `git commit -a -m "提交消息"`：跳过暂存区，直接提交工作目录中所有改变的文件，但是不能提交工作目录中新增的文件
- `git commit --author=lavor -m "提交消息"`：提交暂存区的文件，并重写提交作者  
- `git commit --date=06.13.2016T09:00:00 -m "提交消息"`：提交暂存区的文件，并重写提交日期  
- `git commit --amend -m "提交消息"`：通过创建一个新的提交，以替换当前分支的前端。所代表的含义就是在最新一次提交的基础上进行提交。比如我们完成了最新一次提交，并且这次提交完成后我们对工作目录进行了一些修改，但是我们发现某个文件忘了添加到暂存区并提交，我们可以先添加该文件到暂存区，然后利用该命令进行提交。  

###4. `reset`命令  
***  
- `git reset`：将暂存区的所有文件重置到当前分支的HEAD  
- `git reset <commit> files`：将暂存区的指定文件重置到指定的`<commit>`,`<commit>`既可以是commit的hash（或者hash前7位）也可以是`HEAD`及其祖先，`HEAD~1`表示`HEAD`的父亲，是`HEAD`的前一次提交，没有`<commit>`时默认是`HEAD`。  
- `git reset [--hard|soft|mixed|merge|keep] [<commit>]`：将当前的分支重设到指定的`<commit>`，并且根据`mode`有可能更新暂存区和工作目录。`mode`的取值可以是hard、soft、mixed、merged、keep。  
  - `hard`：重置暂存区与工作目录到指定提交，删除`<commit>`之后的所有提交并将`HEAD`指向该提交，此操作危险指数较大（应慎用）  
  - `soft`：暂存区与工作目录不会变化，仅仅删除`<commit>`之后的所有提交并将`HEAD`指向该提交  
  - `mixed`：默认的，重置暂存区到指定提交，删除`<commit>`之后的所有提交并将`HEAD`指向该提交  
  - `merge`与`keep`用的比较少，暂时不讨论  

**`HEAD`是指向当前分支引用的指针，该指针指向在该分支上的最后一个提交的指针。这意味着`HEAD`将是下一个创建的提交的父亲。一般来说，把你的`HEAD`作为你最后一次提交的快照，是最简单的。`HEAD~1`表示`HEAD`的前一次提交，`HEAD~2`表示`HEAD`的前两次提交，以此类推**  

###5. `rm`命令  
***  
- `git rm files`：删除工作目录的文件  
- `git rm -f files`：强制删除工作目录的文件，不做更新检查
- `git rm --cached files`：删除暂存区的文件  

###6. `mv`命令  
***  
- `git mv oldfile newfile`：为文件重命名
- `git mv files dir`：移动文件到指定目录  
- `git mv -f oldfile newfile`：强制为文件重命名，即使目标文件已存在  
- `git mv -f files dir`：强制移动文件到指定目录名，即使目标文件已存在

##4. 分支与合并    
***  
###1. `branch`命令   
***  
- `git branch`：查看所有分支  
- `git branch branchname`：创建分支  
- `git branch branchname <commit>`：以特定提交为基创建分支
- `git branch -d branchname`：删除分支  
- `git branch -D branchname`：强制删除分支  
- `git branch -m [oldbranchname] newbranchname`：移动或者删除分支  
- `git branch -M [oldbranchname] newbranchname`：强制移动或者删除分支 
- `git branch -r`：列出所有被跟踪的远程分支  
- `git branch -r -d branchname`：删除被跟踪的远程分支  
- `git branch -a`：列出所有本地分支与被跟踪的远程分支  

###2. `checkout`命令   
***  
- `git checkout`:检查本地仓库分支与远程仓库分支的差异  
- `git checkout branchname|tagname`：切换分支或切换到指定`tag`，同名时优先切换分支   
- `git checkout tags/tagname`：切换到指定`tag`  
- `git checkout -b branchname`：新建分支并切换到该分支上    
- `git checkout -B branchname`：强制新建分支并切换到该分支上  

###3. `merge`命令   
***  
- `git merge branchname`：将指定分支合并到当前分支上(默认附带提交操作)，在`merge`后面使用`-m <message>`表示提交消息
- `git merge <commit>`：将指定提交合并到当前分支上  
- `git merge oldbranchname newbranchname`：将`oldbranchname`分支合并到`newbranchname`分支上  
- `git merge --squash branchname`：将指定分支上所有修改放入当前分支工作目录与暂存区，不提交  
- `git merge no--squash branchname`：将指定分支上所有修改放入当前分支工作目录与暂存区，并提交  

###4. `mergetool`命令   
***   
- `git mergetool`：在“merge”命令执行之后出现冲突时执行该命令，用来解决合并的冲突，冲突解决完了不要忘了提交  

###5. `stash`命令  
***  
- `git stash`：储藏工作目录与暂存区的状态到堆栈中  
- `git stash pop [stash@{id}]`：恢复到指定储藏的状态（默认是最近一次储藏的状态），并从堆栈中移除该储藏  
- `git stash apply [stash@{id}]`：恢复到指定储藏的状态（默认是最近一次储藏的状态）  
- `git stash drop [stash@{id}]`:并从堆栈中移除指定储藏（默认是最近一次储藏）
- `git stash list`：显示所有储藏信息  

###6. `tag`命令  
***  
同大多数 VCS 一样，Git 也可以对某一时间点上的版本打上标签。  
- `git tag`：列出所有标签  
- `git tag -l 'v1.*'`：列出符合一定条件的标签  
- `git tag tagname`：新建标签  

##5. 分享与更新项目  
***  
###1. `fetch`命令  
***  
- `git fetch`：下载远程仓库“origin”到本地  
- `git fetch remoterepository`：下载指定远程仓库到本地  
- `git fetch remoterepository branchname`：下载指定远程仓库指定分支到本地  

###2. `pull`命令  
***  
- `git pull remoterepository branchname[:localbranch]`：拉取指定远程仓库指定分支到本地仓库指定分支（默认是当前分支）   

###3. `push`命令  
***  
- `git push remoterepository localbranch[:remotebranch] [--tags]`：推送本地仓库指定分支到远程仓库指定分支（默认是与本地分支同名的远程分支），默认是不推送标签到远程仓库的，加上`--tags`就会推送标签  

###4. `remote`命令  
***    
- `git remote`：查看所有与本地仓库关联的远程仓库  
- `git remote -v`：查看所有与本地仓库关联的远程仓库，并显示`url`  
- `git remote add remote-name remote-url`：添加与本地仓库关联的远程仓库  
- `git remote rename oldname newname`：为远程仓库重命名  
- `git remote remove remote-name`：移除远程仓库  

###5. `submodule`命令  
***   
- `git submodule add repository-url dir`：添加仓库到指定目录，使之成为本仓库的子模块  
- `git submodule init`：初始化子模块  
- `git submodule update`：更新子模块  

**子模块是本仓库依赖的另一个仓库，但是我们不会对所依赖的仓库（子模块）进行修改，只会在必要的时候进行更新操作。**  

##6. 考察与比较  
***   
###1. `show`命令  
***  
- `git show [-times]`：显示最近`times`次（默认是一次）提交的所有对象信息  

###2. `log`命令  
***  
- `git log`：查看提交记录  
- `git log --all`：查看所有提交记录   
- `git log  --oneline`：查看提交记录，以`oneline`形式显示，只显示一行，显示的内容时提交hash的前7位与提交消息  
- `git log -p -times`：表示查看最近`times`次提交改变的内容  
- `git log -stat [-times]`：查看最近`times`次（默认是所有）提交记录，并显示文件的差异分析  

###3. `diff`命令  
***   
- `git diff`：查看工作目录与暂存区的差异  
- `git diff --cached [<commit>]`：查看暂存区与指定提交（默认是HEAD）的差异  
- `git diff <commit>`：查看工作目录与指定提交的差异  
- `git diff <commit>`：查看工作目录与指定提交的差异  
- `git diff <commit> <commit>`：查看两次指定提交的差异
- `git diff branchname`：查看工作目录与指定分支的差异  
- `git diff branchname branchname`：查看两个指定分支间的差异  

上面的所有操作后面都可以加上`-- dir`表示查看该目录下面的差异，在后面加上`>patchname.patch`表示将差异生成补丁，`patchname`是补丁的名字。  

###4. `shortlog`命令  
***  
- `git shortlog`：显示总提交次数与每次提交的提交消息  

###5. `describe`命令  
***  
- `git describe [<commit>|<tag>]`：查看指定提交或者指定标签（默认是最近一次提交）的注解标签信息  
- `git desribe --tags [<commit>|<tag>]`：查看指定提交或者指定标签（默认是最近一次提交）的标签信息
- `git desribe --all [<commit>|<tag>]`：查看指定提交或者指定标签（默认是最近一次提交）的引用信息

###6. `reflog`命令  
***  
- `git reflog`：显示所有提交，下拉，推送，与切换分支操作  
- `git reflog --all`：显示所有提交，下拉，推送操作  

##7. 修补   
***　
###1. `apply`命令  
***  
- `git apply  [--index|--cached] patchname.patch`：在暂存区与工作目录或者暂存区（默认是工作目录）打补丁  
- `git apply  --reverse|-R  patchname.patch`：反向打补丁   
- `git apply --reject patchname.patch`：打补丁，将没有冲突的文件合并，将有冲突的文件标记出来，并生成对应的`.rej`文件

###2. `cherry-pick`命令  
***  
- `git cherry-pick <commit>`：将另一个分支上面的指定提交应用到当前分支上  
- `git cherry-pick banchname`：将指定分支上面的最后一次提交应用到当前分支上  

###3. `rebase`命令  
***  
- `git rebase branchname`：将指定分支上所有修改应用到当前分支上  
- `git rebase branchname branchname`：将第一个指定分支上所有修改应用到第二个分支上  

在`rebase`加上`-i`会提供交互式的变基操作，在交互式操作中常用命令：  
![](http://i.imgur.com/zD7PgjP.png)  

###4. `revert`命令  
***  
- `git revert <commit>`：恢复一个指定提交  

##8. 调试  
***  
###1. `bisect`命令  
***  
使用二分查找，找到引入bug的提交  
- `git bisect start`：开始二分查找  
- `git bisect bad [<commit>]`：设置指定提交（默认是当前分支）为bad  
- `git bisect good [<commit>]`：设置指定提交（默认是当前分支）为good  

输入了上面三个命令后就会自动开始二分查找，我们之后只需要标记当前提交时bad还是good就行了，如果当前找的的提交时bad就输入`git bisect bad`，否则输入`git bisect good`直到找到有bug的提交。  

###2. `blame`命令  
***  
显示修改和作者最后修改的文件的每一行，这就是一个“问责”的命令，如果哪里有问题，我们可以很快地找到该问题是谁导致的。   
- `git blame filename`：查看指定文件所有的操作者，看看是谁错误地修改了该文件  

###3. `grep`命令  
***  
- `git grep keys`：在工作目录中所有文件中搜索`keys`  
- `git grep --cached keys`：在暂存区中所有文件中搜索`keys`  



