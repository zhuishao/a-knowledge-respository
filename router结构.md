#路由结构
router  
  |--about.js
  |--error.js
  |--foo.js
  |--home.js
  |--index.js
  |--job.js
  |--login.js
  |--sys.js
  |--system.js
  |--routers.js  
routers.js是总控它里面引入了home,foo,sys,job,production
system而这些文件里定义了路由，他们暴露出来的是一个数组，因此需要解构就是...语法  
首先在routers里定义路由  
const routers={{},{},{path:'*',redirect:'/s/404',hidden:true}}
再把路由暴露出来  
之后进行路由的配置
1. 引入Vue
2. 引入vue-router
3. 引入设置
4. 引入刚刚暴露出来的路由
5. 引入路由拦截器
6. 定义路由routerInstance
7. 注入拦截器routerInstance.beforeEach(routerBeforeEachFunc)和routerInstance.afterEach(routerAfterEachFunc)分别表示路由进入前，和路由进入后执行的函数