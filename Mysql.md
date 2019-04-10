#Mysql
##进入
mysql -u root -p 
##查看数据库
show databases
##创建数据库
CREATE DATABASE 数据库名
##切换当前数据库
use 数据库名
##创建一个表
create table if not exists class(
name varchar(10),
root varchar(10)
) charset UTF8;
##查看一个表
show tables;
##查看表中的结构
desc tablename;
describe tablename;