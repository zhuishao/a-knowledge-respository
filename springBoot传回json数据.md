#springBoot传回json格式
在pom.xml中添加  
 <dependency>
    <groupId>com.alibaba</groupId>
    <artifactId>fastjson</artifactId>
 	<version>1.2.35</version>
 </dependency>

<build>
	<finalName>springboot-json</finalName>
    <plugins>
    	<plugin>
        	<groupId>org.springframework.boot</groupId>
            <artifactId>spring-boot-maven-plugin</artifactId>
            <configuration>
            	<fork>true</fork>
            </configuration>
        </plugin>
    </plugins>
</build>
在com.example.demo DemoApplication 中 


@SpringBootApplication
    public class DemoApplication extends WebMvcConfigurationSupport {

    public static void main(String[] args) {
        SpringApplication.run(DemoApplication.class, args);
    }
    @Override
    public void configureMessageConverters(List<HttpMessageConverter<?>> converters) {
        super.configureMessageConverters(converters); // 创建fastjson对象
        //创建convert消息转换对象
        FastJsonHttpMessageConverter converter = new FastJsonHttpMessageConverter();

        // 添加fastjosn配置信息，设置是否需要格式化
        FastJsonConfig confg = new FastJsonConfig();
        confg.setSerializerFeatures(SerializerFeature.PrettyFormat);
        //添加配置信息到消息对象
        converter.setFastJsonConfig(confg);

        converters.add(converter);
    }


}
#解决中文乱码
在application.properties中

spring.http.encoding.force=true
spring.http.encoding.charset=UTF-8
spring.http.encoding.enabled=true
server.tomcat.uri-encoding=UTF-8
