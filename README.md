# GIT
## 本地仓库
### git init
> 初始化git

### git add <文件名>
> 添加文件到git中 (实际上就是把文件修改添加到暂存区)

### git commit -m ""
> git 提交文件 (实际上就是把暂存区的所有内容提交到当前分支)
> * git commit命令，-m后面输入的是本次提交的说明，可以输入任意内容，当然最好是有意义的，这样你就能从历史记录里方便地找到改动记录。

### git statue
> 查看仓库当前的状态

### git diff 可选（HEAD）
> 查看修改内容

### git reset --hard 版本号
> 版本回退
> * Git必须知道当前版本是哪个版本，在Git中，用HEAD表示当前版本，也就是最新的提交1094adb...，上一个版本就是HEAD^，上上一个版本就是HEAD^^，当然往上100个版本写100个^比较容易数不过来，所以写成HEAD~100。

### git reflog
> 查看记录版本

### git checkout -- file
> 撤销修改(用版本库里的版本替换工作区的版本)
> > * 场景1：当你改乱了工作区某个文件的内容，想直接丢弃工作区的修改时，用命令git checkout -- file。
> > * 场景2：当你不但改乱了工作区某个文件的内容，还添加到了暂存区时，想丢弃修改，分两步，第一步用命令git reset HEAD <file>，就回到了场景1，第二步按场景1操作。
> > * 场景3：已经提交了不合适的修改到版本库时，想要撤销本次提交，参考版本回退一节，不过前提是没有推送到远程库。

> git checkout -b
> > * git checkout命令加上-b参数表示创建并切换，相当于以下两条命令：
> > > git branch dev <br>
> > > git checkout dev

### git branch
> 查看分支
> > git branch -d <分支名> 删除分支

### git merge
> 合并指定分支到当前分支

### git rm <文件名>
> 删除文件

## 远程仓库

### 创建SSH Key
> 在用户主目录下，看看有没有.ssh目录，如果有，再看看这个目录下有没有id_rsa和id_rsa.pub这两个文件，如果已经有了，可直接跳到下一步。如果没有，打开Shell（Windows下打开Git Bash），创建SSH Key：
> ssh-keygen -t rsa -C "你的github账号"

### git remote add origin "你的仓库地址"
> 关联远程仓库

### git push
> 把本地库的内容推送到远程库上
> * git push origin master
>>把本地库的当前分支所有内容推送到远程库上
> * git push -u origin master
>>加上了-u参数，Git不但会把本地的master分支内容推送的远程新的master分支，还会把本地的master分支和远程的master分支关联起来，在以后的推送或者拉取时就可以简化命令。

### git clone
> 克隆远程仓库
> * git clone git@github.com:*/*.git

## git 分支
>查看分支：git branch
>
>创建分支：git branch <name>
>
>切换分支：git checkout <name>
>
>创建+切换分支：git checkout -b <name>
>
>合并某分支到当前分支：git merge <name>
>
>删除分支：git branch -d <name>