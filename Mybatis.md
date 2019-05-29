#Mybatis坑
##若数据库找到空值
在实体类中加
@JsonIgnoreProperties(value = { "hibernateLazyInitializer", "handler" })
##TooManyResultsException
想获取一条记录但获取两条，mapper没加List
##UnsatisfiedDependencyException
把jdbcType写成javaType
##BindingException: Parameter 'username' not found
这是在maper上绑定了多个参数的问题，解决办法  
在mapper参数前加上@Param
##ExecutorException
select中缺少了resultType或resultMap
##insert xml
在插入中看的是获取的bean的参数，不用设置resultMap和resultType
##xml中参数出现红色
要加上· ·
##DefaultHandlerExceptionResolver
用post没问题，用get有问题
是因为axios有请求头application-json
而get的请求头是map
建议用post
##400错误
前后台格式不匹配
前台结构
{
	id:23
}
...可能需要解构
##Resolved [org.springframework.web.HttpRequestMethodNotSupportedException: Request method 'GET' not supported]
value="少了/,名字写错没对上
##IllegalStateException
post用controller中用类吧