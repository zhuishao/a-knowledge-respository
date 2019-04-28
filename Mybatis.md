#Mybatis坑
##若数据库找到空值
在实体类中加
@JsonIgnoreProperties(value = { "hibernateLazyInitializer", "handler" })
##TooManyResultsException
想获取一条记录但获取两条，mapper没加List
##UnsatisfiedDependencyException
把jdbcType写成javaType