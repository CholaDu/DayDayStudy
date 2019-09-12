# git创建远程分支

现在我在master分支上，工作目标是干净的，也没有需要commit的：

$ git branch
* master
  release
 
$ git status
On branch master
Your branch is up-to-date with 'origin/master'.
nothing to commit, working directory clean
新建远程分支
新建一个本地分支：

$ git checkout -b dbg_lichen_star
查看一下现在的分支状态:

$ git branch
* dbg_lichen_star
  master
  release
星号(*)表示当前所在分支。现在的状态是成功创建的新的分支并且已经切换到新分支上。

把新建的本地分支push到远程服务器，远程分支与本地分支同名（当然可以随意起名）：

$ git push origin dbg_lichen_star:dbg_lichen_star
使用git branch -a查看所有分支，会看到remotes/origin/dbg_lichen_star这个远程分支，说明新建远程分支成功。

删除远程分支
我比较喜欢的简单方式，推送一个空分支到远程分支，其实就相当于删除远程分支：

$ git push origin :dbg_lichen_star
也可以使用：

$ git push origin --delete dbg_lichen_star
这两种方式都可以删除指定的远程分支
