#我对git的理解
##下载/安装
官网上有
##如何使用git
###在github创建一个账号
###在gitbash配置用户和邮箱
>git config --global user.name "zhuishao",
>git config --global user.email "540105385@qq.com"

###进入项目,启动git
>在gitbash中进入项目目录 cd d:/Vue/ant，git init
###查看目录状态
>git status

###把项目添加进预存区
>git add index.html

###提交修改变成版本
>git commit -m "ant-v-1.0.0"

###查看修改记录
>git log
###版本回退
>回退一个版本git reset --hard HEAD^
###查看命令历史
>git reflog

###回到从前的命令
>get reset -hard e2f3
###删除文件
>在目录下创建一个文件比如test.txt 再commit
git rm test.txt
git commit -m "remve test.txt"

###克隆一个项目
git clone http://10.43.200.81:18080/opf/opf-ui.git
###查看分支
git branch -a
###删除分支
git branch -d dialy/1.0.0
###切换分支
git checkout dialy/1.0.0
###没有add的文件回到修改前
git checkout -- src/
###已经add的文件取消add
git reset Head 文件名
###windows与linux，windows git 设置
git config --global core.autocrlf true