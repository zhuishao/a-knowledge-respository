#解决每次上传github都要输入账号密码问题
###查看git clone 方式
git remote -v
###一处原来的git源
git remote rm origin
###添加新的git源头
git remote add origin 地址