# 入门Git

[Git-Cheatsheet.pdf](https://github.com/JasperMei/-Git/blob/master/Git-Cheatsheet.pdf)

Git是目前世界上最先进的分布式**版本控制**系统
- 版本控制：自动记录每次对文本的修改，并支持多人协作。OneDrive也有这类的功能。
- 分布式：与集中式相对应，不需要中央服务器，也是一种去中心化。

## Git使用者信息查看修改
查看
:   `git config user.email` `git config user.name`

修改
:   `git config --global user.email "xxx@xxx.com"` `git config --global user.name "xxx"`

## 建立本地库
1. 在计算机本地任意位置新建文件夹，在文件夹内右键菜单选择Git Bash Here。
2. `pwd`命令用于显示当前目录
3. `mkdir learngit`在Git Bash所在位置建立名为learngit的文件夹
4. `cd learngit`进入learngit文件夹
5. `git init`前目录下初始化Git本地库
[git——创建本地版本库](https://blog.csdn.net/u012031408/article/details/54407002)

## 在本地库中创建、修改、添加、提交文档
1. 将需要进行版本控制的文档创建在刚才初始化的库中
2. `git add Readme.txt`告诉Git，把文件添加到stage（add每添加一个文件需要执行一次这句命令）
3. `git commit -m "wrote a readme file"`告诉Git，把文件提交到分支（commit可以一次提交多个文件，在多次add之后用一个commit提交之前添加的文件就可以了）
4. `git status`查看当前Git的状态
5. `git diff`查看工作区与index之间的不同
6. `git log`查看commit日志（显示当前所在版本以及之前的版本，无法显示当前版本之后的版本）

## 版本切换
1. `git reset --hard HEAD^`退回前一个版本
2. `git reflog`用来记录你的每一次命令(`git reflog --relative-date`带时间的)
通过commit ID可以在任何版本间切换`git reset --hard ID`

## 工作区&版本库
`learngit`文件夹中能够看到的目录就是一个工作区，隐藏的`.git`不属于工作区而是Git的版本库
![工作区和版本库示意图](https://www.liaoxuefeng.com/files/attachments/919020037470528/0)

工作区中的内容首先被`git add`到stage（暂存区），然后再被`git commit`到master分支

## 删除文件
1. `git rm`在工作区删除文件
2. `git checkout-- <file>...`丢弃工作区修改，将版本库中的版本替换工作区的版本

## 远程库
1. `cd ~/.ssh`检测有没有SSH Key
2. `ssh-keygen -t rsa -C "youremail@xxx.com"`创建SSH Key可以按三个回车从而不设置密码
3. .ssh目录，里面有id_rsa和id_rsa.pub两个文件，这两个就是SSH Key的秘钥对，id_rsa是私钥，不能泄露出去，id_rsa.pub是公钥，可以公开
4. 登录GitHub将公钥添加进GitHub，一个账户可以有多个key,从而实现在不同电脑上想GitHub推送
[Git SSH Key 生成步骤](https://blog.csdn.net/hustpzb/article/details/8230454)
[Git SSH秘钥的删除和创建（Git ssh 忘记密码怎么办？）](https://blog.csdn.net/qq_34902522/article/details/78498664)

## Reference
[廖雪峰Git教程](https://www.liaoxuefeng.com/wiki/896043488029600)
[Git cheat sheet](https://www.atlassian.com/git/tutorials/atlassian-git-cheatsheet)


写在最后：
由于本人水平有限，难免挂一漏万，存在错误讹说，还盼望读者批评指正。