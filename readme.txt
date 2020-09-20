----------------git配置文件config用户名和邮箱的设置-----------
1.设置用户名
$ git config --global user.name "instance-Opnntq"
2.设置用户邮箱
$ git config --global user.email "1047740047@qq.com"
3.查看git设置列表信息
$ git config --list 
4.查看用户名
$ git config user.name 

------------------------创建版本库----------------------------
1.首先创建个空目录
$ mkdir learngit
$ cd learngit
$ pwd
2.将创建目录管理起来
$ git init

3.返回上一个目录
cd ..

------------------------添加文件------------------------------
1.添加文件
$ git add readme.txt
2.提交文件
$ git commit -m "wrote a readme file"

-----------------------查看文件状态---------------------------
1.查看仓库当前状态
$ git status
2.查看文件修改内容
$ git diff readme.txt 

------------------------版本退回------------------------------
1.查看提交日志
$ git log
2.查看行显示日志
$ git log --pretty=oneline
3.还原到上一个版本
$ git reset --hard HEAD^
4.还原指定版本
$ git reset --hard 1094a
5.查看操作记录
$ git reflog

-----------------------管理修改------------------------------
1.查看工作区和版本库里面最新版本的区别
git diff HEAD -- readme.txt
2.修改文件后提交步骤
第一次修改 -> git add -> 第二次修改 -> git add -> git commit

-----------------------撤销修改-----------------------------
1.场景1：当你改乱了工作区某个文件的内容，想直接丢弃工作区的修改时，用命令git checkout -- file
$ git checkout -- readme.txt
2.场景2：当你不但改乱了工作区某个文件的内容，还添加到了暂存区时，想丢弃修改，分两步，第一步用命令git reset HEAD <file>，就回到了场景1，第二步按场景1操作。
$ git reset HEAD readme.txt
3.场景3：已经提交了不合适的修改到版本库时，想要撤销本次提交，参考版本回退一节，不过前提是没有推送到远程库。

---------------------删除文件-------------------------------
1.一般情况下，你通常直接在文件管理器中把没用的文件删了，或者用rm命令删了
$ rm test.txt
2.另一种情况是删错了，因为版本库里还有呢，所以可以很轻松地把误删的文件恢复到最新版本
$ git checkout -- test.txt

---------------------远程仓库-------------------------------
1.创建SSH Key
$ ssh-keygen -t rsa -C "youremail@example.com"
2.登陆GitHub，打开“Account settings”，“SSH Keys”页面：然后，点“Add SSH Key”，填上任意Title，在Key文本框里粘贴id_rsa.pub文件的内容
3.把本地仓库的内容推送到GitHub仓库
$ git remote add origin git@github.com:meihao-bit/learngit.git

---------------------