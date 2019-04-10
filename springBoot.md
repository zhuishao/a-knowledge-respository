#如何构建一个完整的spring boot项目
##创建
spring Initializr  
sql->mybatis,mysql
##过程
1. 在pom.xml添加依赖
2. 在application.properties配置
3. 在java/com....文件夹下创建bean，Controller,mapper,service
4. 在resources下创建mappers
5. bean中的文件是实体类
6. java/mapper中的文件是操作数据的接口，需要添加注解mapper
7. resources/mappers中的文件是数据库操作实现，后面带xml，需要与java/mapper关联起来
8. service中的文件是业务代码，相当于Dao
9. Controller中的文件是请求接口
10. 在mapper接口上要加上@Mapper