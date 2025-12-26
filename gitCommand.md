此文件用于记录和回顾git相关的命令


git学习网址：https://liaoxuefeng.com/books/git/install-git/index.html


```bash
####git安装和配置相关指令：

1.通过scoop包管理器安装git
        scoop install git
2.配置git
        git config --global user.name "用户名"
        git config --global user.email "用户邮件地址"


####本地git应用指令

1.创建版本库
        git init
2.提交文件到暂存区
        git add 文件名
3.将暂存区的文件提交到仓库并添加说明
        git commit -m "要添加的说明"
4.查询版本管理状态
        git status
5.查看文件差异
        git diff 文件名
6.查看版本提交日志
        git log
7.以一行的方式显示提交日志
        git log --pretty=oneline
8.回退到当前版本前的某一个版本
        git reset --hard HEAD^ （HEAD^^^^）
9.回退到指定版本
        git reset --hard 版本号的前几位
10.查看所有git命令记录
        git reflog
11.查看工作区和版本库最新版本的差别
        git diff HEAD -- 文件名
12.丢弃工作区的修改或还原工作区文件
        git restore 文件名
13.撤销暂存区的修改
        git reset HEAD 文件名
14.删除版本库中的文件并提交
        git rm 文件名
        git commit -m 说明


####远程git指令

1.在用户主目录创建ssh密钥
        ssh-keygen -t rsa -C "邮件地址"

2.关联远程仓库
        git remote add origin git@github.com:账户名/仓库名.git
3.把本地分支的所有内容推送到远程库
        git push -u origin 本地库分支   （-u推送并关联远程分支）
4.推送本地分支
        git push origin master
5.查看远程库信息
        git remote -v
6.删除远程库关联
        git remote rm origin
7.克隆远程库到本地
        git clone git@github.com:账号/仓库名.git


####git分支管理

1.创建分支
        git branch 分支名
2.切换分支
        git switch 分支名
3.创建并切换分支
        git switch -c 分支名
4.查看分支结构
        git branch
5.合并指定分支到当前分支
        git merge 分支名
6.删除分支
        git branch -d 分支名  （-D强行删除）
7.查看分支合并情况
        git log --graph --pretty=oneline --abbrev-commit
8.非快速合并指定分支
        git merge --no-ff -m "合并说明" 分支名
9.存储现场工作
        git stash
10.查看工作现场列表
        git stash list
11.恢复工作现场
        git stash apply stash@{列表序号}
12.删除工作现场
        git stash drop
13.恢复并删除工作现场
        git stash pop
14.复制其他分支的某一个提交提交到当前分支
        git cherry-pick 某个commit
15.在本地创建远程某个分支
        git switch -b 本地分支 origin/远程分支
16.从远程拉取某一个分支的最新提交到本地
        git pull origin 分支名
17.关联本地已有分支和远程分支
        git branch --set-upstream-to=origin/远程分支名 本地分支名
18.整理分叉的提交历史（会失去可信的本地提交记录）
        git rebase


####标签管理

1.当前位置创建标签
        git tag 标签
2.查询标签
        git tag
3.创建指定位置的标签
        git tag 标签 id号
4.查看标签的信息
        git show 标签
5.创建带有说明的标签
        git tag -a 标签 -m "说明" 
6.删除标签
        git tag -d 标签
7.推送标签到远程
        git push origin 标签
8.一次性推送全部标签
        git push origin --tags
9.删除远程标签
        git tag -d 标签
        git push origin :refs/tags/标签
```