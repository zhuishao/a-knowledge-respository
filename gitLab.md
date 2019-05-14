
#GitLab使用
###在gitlab上创建一个新项目
New Project
###在本地创建一个文件
###在该文件目录下
>git clone http://10.43.200.81:18080/zhuzhewei/newgit.git  
###在该文件下创建文件并add
touch README
git add README.md
git commit -m "add README.md"
###提交到gitlab
git push -u origin master
###查看本地分支
git branch
###查看远程分支
git branch -r
###创建一个新的分支
git checkout -b feature_x
###切换分支（自动创建本地分支）
git checkout master
###删去分支
git branch -d featrue_x，不在当前分支才能删
##本地分支上传到远程未开分支
git push --set-upstream origin dailytest
###提交分支到远程服务器
git push origin <branch>
###合并(合并到当前)
git merge <branch>
###远程分支删除
git push origin --delete feat
###更新本地分支
git pull origin daily/1.0.0
###更新远程地址
git remote add origin
###提交远程之前检查错误
npm run lint
###把远程分支合并
1. 先给主线创建一个分支
2. 提交分支到远程服务器
3. 修改本地文件
4. 提交到缓存并commit
5. 把本地修改的分支推送到远程 git push origin feat
6. 远程的feat要合并到master上
7. 进入本地master分支并合并feat
8. 推送master到远程
9. 删除远程feat 
10. 删除本地feat
11. 查看所有分支
###本地分支合并到远程主干
1. 远程拉主干
2. 本地主干创建分支
3. 修改本地分支
4. add并commit
5. 本地分支推送到远程主干 git push origin feat:master
###远程分支冲突解决
1. 本地创建文件夹并git clone
2. 本地创建分支并上传远程
3. 本地的另一个分支更新
4. 另一个分支上传到远程分支
5. 这一个分支git pull origin feat
6. 这一个分支上传到远程分支

###本地项目上传到gitLab上
1. 本地git init
2. 与github连接  ssh -T git@github.com（要确保以前连接过）
3. 本地 git add,commit
4. 上传  git push -u origin master





