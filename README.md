#Git 教程
feature-A
fix-B
feature-C


一、初始设置
1.1SSH KEY
$ ssh -keygen -t  -C "your_email@example.com"
  id_rsa文件是私有-rsa.pub是公开密匙
1.2添加公开密匙
$ cat ~/.ssh/id_rsa.pub
  ssh-rsa  your_email@example.com
查看网页ssh
添加成功之后，邮箱会收到提示“公共密匙添加完成”
1.3登陆
$  ssh -T git@github.com


二、基本操作
2.1初始化仓库
mkdir git-tutorial
cd git-tutorial
git init
2.2查看仓库状态
git status
2.3README.md文件
touch README.md
2.4箱暂存区中添加文件
git add README.md
git status
2.5将当前暂存区文件实际保存到仓库的历史记录中
git commit -m "First commit"    (First commit称作提交信息，是对提交的概述)
2.6查看日志
git log
git log 命令后加目录名只会显示该目录下的日志，若是文件名只会显示该文件相关的日志。例如 git log README.md
       如果想查看提交所带来的改动 git log -p README.md
2.7 查看更改前后的差别
$ git diff  
养成一个习惯：在执行git commit之前先执行git diff HEAD命令，查看本次提交和上次提交之间的差别，等确定完之后再进行提交。（这里的HEAD是指向当前分支中最新一次提交的指针）


三、推送至远程仓库
3.1添加远程仓库
git remote add orign git@github.com:swrdZWJ/git-tutorial.git  执行完之后，自动将该远程仓库的名称设置为origin（标识符）
3.2推送至远程仓库
git push -u origin master  这样执行完之后，当前分支的内容就会被推送到远程仓库origin的master分支
3.3推送至master以外的分支
$git checkout -b feature-D   (创建feature-D分支)
$git push -u origin feature-D  （推送是远程仓库中feature-D分支中）


四、从远程仓库中获取
在一个空白目录下
$git clone git@github.com:swrdZWJ/git-tutorial.git    执行完之后默认处于master分支之下
$cd git-tutorial
$git branch  查看分支信息  $git branch -a查看当前分支的相关信息
$git checkout -b feature-D origin/feature-D   -b参数后面是本地仓库中新建的分支和远程仓库分支命名相同














































