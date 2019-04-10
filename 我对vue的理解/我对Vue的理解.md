# 我对Vue的理解

## 创建项目

1. cmd打开Vue的项目空间，敲入命令 **vue init webpack 项目名称**
2. 操作
	project name:项目名称，
    install vue-router:是否需要vue-router 选Y，
    Use Eslint to lint you code:选n，
	Setup unit tests with Karama + Moch:选n，
	Setup e2e tests with Nightwatch:选n
3. cmd里进入创建的的项目下载依赖包：npm install,npm run dev
4. 加入蚂蚁ui：cmd进入项目，cnpm install ant-design-vue --save,cnpm install
5. webstrom导入项目，在webstorm里右击package.json选择show npm Scripts 点dev
6. 配置run：edit configurations=>npm=>dev
7. webstorm导入anti design：cmd进入项目 npm install ant-design-vue --save
8. 在main.js中：import Anted from 'ant-design-vue'，import 'ant-design-vue/dist/antd.css'，Vue.use(Anted)
## 项目文件
1. main.js是我们的入口文件，主要作用是初始化Vue实力并使用需要的插件
2. App.vue是我们的主组件，所有页面都是在App.vue下进行切换的。其实你可以理解为所有路由也是app.vue的子组件，所以我们将router标识为App.vue的子组件
3. router中的index.js文件可以存放所有的页面路径
##创建项目新的方式
>打开gitcmd到项目目录，输入vue create 项目名称

##vue 生命周期
文件内部包含

##vue 组件之间数据传递

