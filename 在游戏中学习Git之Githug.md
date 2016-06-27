#在游戏中学习Git之Githug（Windows版）  
***  
#1. githug安装  
- 首先，[下载Git](https://git-scm.com/download/)工具，并配置Git工具安装目下面的cmd目录到环境变量的PATH中，这样我们就可以在cmd下面使用git了。  
- 其次，githug是运行在ruby上的，所以我们还要安装ruby，[下载ruby](http://rubyinstaller.org/)，安装时勾选“Add Ruby executables to your PATH”，忘了勾选的要配置Ruby安装目录下面的bin目录到环境变量的PATH中。  
- 再次，安装githug，在安装githug先确认ruby好了吗，然后在安装githug  
  - 在cmd下面输入ruby --version查看ruby是否安装好了，若没有，则说明环境变量还没有生效，注销户用再登录  
  -  在cmd下面输入gem install githug安装githug  
  ![](http://i.imgur.com/lBnbPCg.png)

#2. githug相关说明  
***  
#1. githug是用来干什么的
githug是设计给你学习Git的实用方法。它有一系列的关卡，每一关都需要你用git命令得到一个正确的答案。  

#2. githug关卡说明  
githug一共有55关：
```  
#1: init
#2: config
#3: add
#4: commit
#5: clone
#6: clone_to_folder
#7: ignore
#8: include
#9: status
#10: number_of_files_committed
#11: rm
#12: rm_cached
#13: stash
#14: rename
#15: restructure
#16: log
#17: tag
#18: push_tags
#19: commit_amend
#20: commit_in_future
#21: reset
#22: reset_soft
#23: checkout_file
#24: remote
#25: remote_url
#26: pull
#27: remote_add
#28: push
#29: diff
#30: blame
#31: branch
#32: checkout
#33: checkout_tag
#34: checkout_tag_over_branch
#35: branch_at
#36: delete_branch
#37: push_branch
#38: merge
#39: fetch
#40: rebase
#41: repack
#42: cherry-pick
#43: grep
#44: rename_commit
#45: squash
#46: merge_squash
#47: reorder
#48: bisect
#49: stage_lines
#50: find_old_branch
#51: revert
#52: restore
#53: conflict
#54: submodule
#55: contribute  
```  

#3. githug常用命令  
***  
- `githug`： 开始闯关或进入下一关  
- `githug hint`： 过关提示  
- `githug levels`： 显示关卡列表  
- `githug reset [关卡名]`： 重启本关或者重启到指定关卡名的关卡  

#4. 开始闯关  
***  
##1. 第1关  
***  
- 关卡描述：  
```
有一个新的目录“git_hug”被创建了，在它里面初始化一个仓库  
```  
- 通关操作：  
```
git init  
```

![](http://i.imgur.com/HiRMs8a.png)  

##2. 第2关  
***  
- 关卡描述：  
```
设置你的有户名与电子邮箱，这很重要，只有这样你的提交才会被识别  
```  
- 通关操作：  
```  
git config --local user.name lavor  
git config --local user.email lavor@qq.com
```  

![](http://i.imgur.com/9nSxLBs.png)  

##3. 第3关  
***  
- 关卡描述：  
```
有一个名叫“README”的文件夹，你要将它加入到暂存区。  
注意：每一关都是一个新仓库，不要在前面的关卡找文件。
```  
- 通关操作：  
```  
git add README  
```  

![](http://i.imgur.com/Wwceqr4.png)  

##4. 第4关  
***  
- 关卡描述：  
```
“README”文件已经被加入到暂存区，现在提交它。  
```  
- 通关操作：  
```
git commit -m "add README"  
```

![](http://i.imgur.com/JYCn1Yq.png)

##5. 第5关  
***  
- 关卡描述：  
```
从“https://github.com/Gazler/cloneme”克隆仓库。
```  
- 通关操作：  
```  
git clone https://github.com/Gazler/cloneme  
```  

![](http://i.imgur.com/QPtHX8I.png)

##6. 第6关  
***  
- 关卡描述：  
```
从“https://github.com/Gazler/cloneme”克隆仓库到“my_cloned_repo”目录。
```  
- 通关操作：  
```  
git clone https://github.com/Gazler/cloneme  my_cloned_repo  
```  

![](http://i.imgur.com/TZrana4.png)  

##7. 第7关  
***  
- 关卡描述：  
```
文本编辑器“vim”为所有文件创建以“.swp”结尾的文件，这些文件当前都被打开了。我们不希望他们潜入到仓库。让仓库忽略“.swp”文件。  
```  
- 通关操作：  
```
//由于没有装vim，直接用记事本打开“.gitignore”文件，在文件末尾换行并加上“*.swp”。  
```

![](http://i.imgur.com/iARFHuo.png)

##8. 第8关  
***  
- 关卡描述：  
```
注意一些文件以“.a”为扩展名。我们希望忽略这些文件除了“lib.a”文件。    
```  
- 通关操作：  
```  
//由于没有装vim，直接用记事本打开“.gitignore”文件，在文件末尾换行并加上“*.a”，再换行，在文件末尾加上“!lib.a”。
```  

![](http://i.imgur.com/8UYR4Yb.png) 

##9. 第9关  
***  
- 关卡描述：  
```
仓库中有一些文件，其中一个没有被跟踪，它是哪个文件。
```  
- 通关操作：  
```  
git status    
```  

![](http://i.imgur.com/TfX5OCj.png) 

##10. 第10关  
***  
- 关卡描述：  
```
仓库中有一些文件。多少文件将要被提交。 
```  
- 通关操作：  
```
git status    
```

![](http://i.imgur.com/il7oo1b.png) 

##11. 第11关  
***  
- 关卡描述：  
```
一个文件从工作树上面移除了，但是没有从仓库中移除。找到这个文件并移除它。  
```  
- 通关操作：  
```  
git status  
git add deleteme.rb  
```  

![](http://i.imgur.com/gRalESo.png)  

##12. 第12关  
***  
- 关卡描述：  
```
一个文件以外地加入到你的暂存区，找出这个文件并将它从暂存区移除。  
*注意*：不要将它从文件系统中移除，仅仅将它git中移除。
```  
- 通关操作：  
```  
git status  
git rm --cached deleteme.rb    
```  

![](http://i.imgur.com/8fIvioI.png)  

##13. 第13关  
***  
- 关卡描述：  
```
你做了一些修改，并且向稍后再它们上面工作。你应该保存它们，但是不提交它们。    
```  
- 通关操作：  
```
git stash    
```

![](http://i.imgur.com/KF2d5uS.png)   

##14. 第14关  
***  
- 关卡描述：  
```
我们有一个名为“oldfile.txt”的文件。我们想要将它重命名为“newfile.txt”并保存该修改。    
```  
- 通关操作：  
```  
git mv oldfile.txt newfile.txt  
```  

![](http://i.imgur.com/fMMjSZB.png)  

##15. 第15关  
***  
- 关卡描述：  
```
你添加了一些文件到你的仓库，但现在知道你的项目需要进行调整。创建一个新的文件夹命名为“src”,使用git将所有的".html"文件到该文件夹中。
```  
- 通关操作：  
```  
git mv about.html contact.html index.html src    
```  

![](http://i.imgur.com/rvOANNO.png)  

##16. 第16关  
***  
- 关卡描述：  
```
你将要寻找最新提交的哈希，为此你将研究该仓库的日志。  
```  
- 通关操作：  
```
git log   
```

![](http://i.imgur.com/pGCDaCQ.png)  

##17. 第17关  
***  
- 关卡描述：  
```
我们有一个git仓库，并且我们想用“new_tags”来标记当前的提交。  
```  
- 通关操作：  
```  
git tag "new_tag"
```  

![](http://i.imgur.com/h1BtTz5.png)  

##18. 第18关  
***  
- 关卡描述：  
```
仓库中有一些标记没有被推送到远程仓库，现在推送它们。  
```  
- 通关操作：  
```  
git push --tags origin master    
```  

![](http://i.imgur.com/2TZoyw6.png)   

##19. 第19关  
***  
- 关卡描述：  
```
“README”文件被提交了，但是“forgotten_file.rb”文件好像忘了提交。添加这个文件，并改正上次提交使之包含该文件。
```  
- 通关操作：  
```
git add forgotten_file.rb   
git commit --amend -m "改正后提交"
```

![](http://i.imgur.com/GUNQHY7.png)    

##20. 第20关  
***  
- 关卡描述：  
```
用未来的时间日期（比如明天）来提交改变。 
```  
- 通关操作：  
```  
git commit --date=06.13.2016T09:00:00 -m "指定提交时间为2016年6月13日9点整"
```  

![](http://i.imgur.com/JSRrP4e.png)  

##21. 第21关  
***  
- 关卡描述：  
```
有两个文件要提交，目标是将每个文件添加为单独提交，但意外地两个文件都被添加到暂存区了。用“reset”命令将“to_commit_second.rb”文件从暂存区移除（不做提交操作）。  
```  
- 通关操作：  
```  
git reset HEAD to_commit_second.rb  
```  

![](http://i.imgur.com/NciByfl.png)  

##22. 第22关  
***  
- 关卡描述：  
```
你提交太快了。现在你要撤消最后一次提交，同时保持索引。 
```  
- 通关操作：  
```
git reset --soft HEAD~1  
```
![](http://i.imgur.com/Qp68cY3.png)   

##23. 第23关  
***  
- 关卡描述：  
```
文件已经被修改了，但是你不想保存该修改。从最后一次提交中检出“config.rb”文件。    
```  
- 通关操作：  
```  
git checkout config.rb  
```  

![](http://i.imgur.com/9nSxLBs.png)  

##24. 第24关  
***  
- 关卡描述：  
```
项目有一个远程仓库，找到它。  
```  
- 通关操作：  
```  
git remote -v    
```  

![](http://i.imgur.com/r6KPZEj.png)  

##25. 第25关  
***  
- 关卡描述：  
```
远程仓库有一个与之关联的url。输入远程仓库“remote_location” 的url。  
```  
- 通关操作：  
```
git remote -v    
```

![](http://i.imgur.com/m1flzff.png)   

##26. 第26关  
***  
- 关卡描述：  
```
你需要从“origin”仓库拉下改变到本地仓库。    
```  
- 通关操作：  
```  
git pull origin master  
```  

![](http://i.imgur.com/ohpUuQn.png)   

##27. 第27关  
***  
- 关卡描述：  
```
添加一个url为“https://github.com/githug/githug”的远程仓库，并为该远程仓库命名为“origin”。  
```  
- 通关操作：  
```  
git remote add origin https://github.com/githug/githug   
```  

![](http://i.imgur.com/gZ5f9J4.png)  

##28. 第28关  
***  
- 关卡描述：  
```
你的本地“master”分支与远程仓库“origin”的“master” 分支不一致，请用远程仓库“origin”的“master” 分支来改变你的提交，并将提交推送到远程仓库。  
```  
- 通关操作：  
```
git rebase origin/master  
git push origin master  
```

![](http://i.imgur.com/qfFutAV.png)   

##29. 第29关  
***  
- 关卡描述：  
```
自最后一次提交后，“app.rb”文件发生了一些改变。找出该文件那些行被改变了。  
```  
- 通关操作：  
```  
git diff  
```  

![](http://i.imgur.com/qZQHNtX.png)   

##30. 第30关  
***  
- 关卡描述：  
```
有人将密码放进了“config.rb”文件中，找出是谁。  
```  
- 通关操作：  
```  
git blame config.rb   
```  

![](http://i.imgur.com/bx1iMvs.png)  

##31. 第31关  
***  
- 关卡描述：  
```
有一个新的目录“git_hug”被创建了，在它里面初始化一个仓库  
```  
- 通关操作：  
```
git init  
```

![](http://i.imgur.com/HiRMs8a.png)  

##32. 第32关  
***  
- 关卡描述：  
```
你想在一段可能打破一些东西的代码上工作，创建一个“test_code”分支。    
```  
- 通关操作：  
```  
git branch test_code  
```  

![](http://i.imgur.com/bJAbHir.png)   

##33. 第33关  
***  
- 关卡描述：  
```
你需要在“1.2”版本的应用程序上修复一个bug。检出“v1.2”标记。  
```  
- 通关操作：  
```  
git checkout v1.2   
```  

![](http://i.imgur.com/ZAR6Pny.png)    

##34. 第34关  
***  
- 关卡描述：  
```
你需要在“1.2”版本的应用程序上修复一个bug。检出“v1.2”标记(注意：有一个名为“v1.2”的分支)。  
```  
- 通关操作：  
```
git checkout tags/v1.2  
```

![](http://i.imgur.com/TBptZgT.png) 

##35. 第35关  
***  
- 关卡描述：  
```
在前一个提交你忘了创建分支，并在该分支上进行提交操作。在最后一次提交前创建一个名为“test_branch”的分支。    
```  
- 通关操作：  
```  
git branch test_branch HEAD~1  
```  

![](http://i.imgur.com/YR9jqvA.png)  

##36. 第36关  
***  
- 关卡描述：  
```
在你的项目中创建了太多的分支。有一个旧的名为“delete_me”的分支，你应该删除它。  
```  
- 通关操作：  
```  
git branch -d delete_me    
```  

![](http://i.imgur.com/Wwceqr4.png)  
##37. 第37关  
***  
- 关卡描述：  
```
在本地分支上你做了一些改变，并且想共享它，但是不准备将它合并到“master”分支上。  
```  
- 通关操作：  
```
git push origin test_branch:test_branch  
```

![](http://i.imgur.com/OKo0yPY.png)   

##38. 第38关  
***  
- 关卡描述：  
```
在“feature”分支上有一个文件，让我们将它合并到“master”分支上。  
```  
- 通关操作：  
```  
git merge feature  
```  

![](http://i.imgur.com/z0MXl34.png)  

##39. 第39关  
***  
- 关卡描述：  
```
好像有一个新的分支被推送到了远程仓库。得到与本地仓库的改变，但是不合并它们。  
```  
- 通关操作：  
```  
git fetch origin   
```  

![](http://i.imgur.com/HeMaw4y.png)   

##40. 第40关  
***  
- 关卡描述：  
```
我们用“git rebase”工作流与“feature”分支准备进入“master”分支。将“feature”分支上的改变合并到“master”上。  
```  
- 通关操作：  
```
git rebase master feature     
```

![](http://i.imgur.com/tOt9cbV.png)  

##41. 第41关  
***  
- 关卡描述：  
```
优化你的仓库是如何包装的，确保多余的包被删除。
```  
- 通关操作：  
```  
git repack -d  
```  

![](http://i.imgur.com/5CTqMRY.png)    

##42. 第42关  
***  
- 关卡描述：  
```
你的新功能是不值得花时间的，你将要删除它。但是它有一个提交填充了“README”文件，你想要将这个提交同样应用到“master”分支上。  
```  
- 通关操作：  
```  
git log --all  
git cherry-pick ca32a6dac7b6f97975edbe19a4296c2ee7682f68    
```  

![](http://i.imgur.com/fVnKYrk.png)   
![](http://i.imgur.com/BNCgl4L.png)  

##43. 第43关  
***  
- 关卡描述：  
```
你项目的截止日期快到了，你想评估你的代码中还有多少“TODO”剩下。  
```  
- 通关操作：  
```
git grep TODO    
```

![](http://i.imgur.com/JWYUBEL.png)  

##44. 第44关  
***  
- 关卡描述：  
```
改正你第一次（非根）提交信息中的错误。    
```  
- 通关操作：  
```  
git log  
git rebase -i a3d1ecb  
```  

![](http://i.imgur.com/ECpJukR.png)   
![](http://i.imgur.com/NzIJuhk.png)  
![](http://i.imgur.com/1UEwY2p.png)  
![](http://i.imgur.com/JTiFTX1.png)  

##45. 第45关  
***  
- 关卡描述：  
```
你做了几次提交，但是想将这些修改都合并到一个提交中。  
```  
- 通关操作：  
```  
git log  
git rebase -i 9760312    
```  

![](http://i.imgur.com/CFK4PEX.png)  
![](http://i.imgur.com/bjbaGKz.png)  
![](http://i.imgur.com/fxIGeT6.png)  
![](http://i.imgur.com/Ofx0RL8.png)  

##46. 第46关  
***  
- 关卡描述：  
```
合并“long-feature-branch”分支中所有的提交到一个提交中。  
```  
- 通关操作：  
```
git merge --squash long-feature-branch  
git commit -m "merge squash"  
```

![](http://i.imgur.com/TH8Oof7.png)

##47. 第47关  
***  
- 关卡描述：  
```
你做了几次提交，但是顺序错了。请为你的提交重新排序。    
```  
- 通关操作：  
```  
git log  
git rebase -i b49d328  
git log  
```  

![](http://i.imgur.com/Z9uay8X.png)   
![](http://i.imgur.com/bGLDiAw.png)  
![](http://i.imgur.com/bMI4bMj.png)  

##48. 第48关  
***  
- 关卡描述：  
```
一个bug在某个地方被引进，你知道运行“ruby prog.rb 5”应该输出“15”。你同样可以运行“make test”。进入bug的提交的哈希的前7个字母是什么。  
```  
- 通关操作：  
```  
git log  
git bisect start master f608824  
git bisect run make test  
```  

**PS：虽然操作正确，也找到了错误的提交，但是却不能通过本关，应该是没有“make”命令的原因。直接利用“githug reset stage_lines”调到第49关，之后即使闯过了第49关进入下一关时还是会进入第48关，所以第49关及以后，都需要通过“githug reset 关卡名”来进入指定关卡。**

![](http://i.imgur.com/pg6K09E.png)   
![](http://i.imgur.com/QSDTLJ1.png)  

##49. 第49关  
***  
- 关卡描述：  
```
你在一个单独的文件里做了一些修改，这些修改属于两个功能。但是这些修改都没有被暂存，暂存属于第一个功能的修改。    
```  
- 通关操作：  
```
git status  
git add feature.rb -p  
e  
```

![](http://i.imgur.com/8eJ6xzj.png)  
![](http://i.imgur.com/F504W7V.png)  
![](http://i.imgur.com/HLANrOp.png)  

##50. 第50关  
***  
- 关卡描述：  
```
你一直在一个分支工作，被一个主要问题弄得心烦意乱，并且你忘了这个分支的名字。切换回那个分支。  
```  
- 通关操作：  
```  
git reflog  
git checkout solve_world_hunger  
```  

![](http://i.imgur.com/W9aKuRv.png)   
![](http://i.imgur.com/O65hkPl.png)  

##51. 第51关  
***  
- 关卡描述：  
```
你做了多次提交，但是想要撤销中间的提交。所有的提交已经被推送，你不能改变现存的历史。  
```  
- 通关操作：  
```  
git log  
git revert  59f058e  
git log  
```  

![](http://i.imgur.com/TCjh6WT.png)  
![](http://i.imgur.com/n1zhVxo.png)  
![](http://i.imgur.com/iN1TIgL.png)  

##52. 第52关  
***  
- 关卡描述：  
```
你决定通过运行“git reset --hard HEAD^”来删除最新的一次提交（这是不明智的）。
稍后你改变了想法，你想要回滚那次提交。重新存储被删除的提交。  
```  
- 通关操作：  
```
git reflog  
git checkout e185df9   
```

![](http://i.imgur.com/2FEklzx.png)  
![](http://i.imgur.com/kyqURlb.png)  

##53. 第53关  
***  
- 关卡描述：  
```
你需要合并“mybranch”分支到当前分支（“master”分支）。  
但是“mybranch”分支中可能有一些错误的改变，这可能引起冲突。  
解决合并中你遇到的冲突，并完成合并操作。    
```  
- 通关操作：  
```  
git merge mybranch    
vim poem.txt  
git add poem.txt  
git commit -m "add poem.txt"  
```  

![](http://i.imgur.com/qLMibv8.png)  
![](http://i.imgur.com/I6XMnyC.png)  
![](http://i.imgur.com/vOYu69b.png)  

##54. 第54关  
***  
- 关卡描述：  
```
你想要将“https://github.com/jackmaney/githug-include-me”仓库的文件放进“./githug-include-me”目录。  
这样做，不通过克隆仓库或者复制远程仓库文件到本地仓库。  
```  
- 通关操作：  
```  
git submodule add https://github.com/jackmaney/githug-include-me githug-include-me   
```  

![](http://i.imgur.com/XKniJa9.png)   

##55. 第55关  
***  
- 关卡描述：  
```
这是最后一关，目标是通过在Github上发出一个pull request请求来为该仓库做贡献。  
注意这一关是被设计用来鼓励你为Githug做有效的贡献，而不是用来测试你创建 pull request请求的能力。  
可以被接受的贡献有关卡，bug修复，文档改进。   
```  

![](http://i.imgur.com/mb0VRSZ.png)  
