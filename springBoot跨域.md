#SpringBoot跨域
##起因
浏览器只允许请求当前域的资源，而对其他域的资源表示不信任。
##怎样才算跨域
1. 请求协议http,https的不同
2. 域domain的不同
3. 端口port的不同
##运行过程
浏览器回车发起请求，按f12在network的getClass请求中有一个Response Headers,下面的属性有一个Access-Control-Allow-Origin,里面的值告诉你了只允许哪个域的请求。
##解決办法
在Java中进行跨域配置，特别是在springboot中

@Configuration
public class WebMvcConfiguration implements WebMvcConfigurer {

    @Bean
    public CorsFilter corsFilter() {
        final UrlBasedCorsConfigurationSource urlBasedCorsConfigurationSource = new UrlBasedCorsConfigurationSource();
        final CorsConfiguration corsConfiguration = new CorsConfiguration();
        /*是否允许请求带有验证信息*/
        corsConfiguration.setAllowCredentials(true);
        /*允许访问的客户端域名*/
        corsConfiguration.addAllowedOrigin("*");
        /*允许服务端访问的客户端请求头*/
        corsConfiguration.addAllowedHeader("*");
        /*允许访问的方法名,GET POST等*/
        corsConfiguration.addAllowedMethod("*");
        urlBasedCorsConfigurationSource.registerCorsConfiguration("/**", corsConfiguration);
        return new CorsFilter(urlBasedCorsConfigurationSource);
    }
}
