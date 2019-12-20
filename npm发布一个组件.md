# npm发布一个组件（vue）
## 流程
1. 将src改为examples
2. 在根目录下创建vue.config.js文件（为了能查看当前组件的情况）  
>	vue  
```	
module.exports = {  
	    pages: {  
	        index: {  
	            entry: 'examples/main.js',  
	            template: 'public/index.html',  
	            filename: 'index.html'  
	        }  
	    }  
	}  
```  

## 创建一个packages文件夹用于存放文件
> 创建一个组件的文件夹例如z-input
>>z-input中创建index.js和z-input.vue  
### index.js中的内容  
import ZInput from './z-input.vue'

ZInput.install = function (Vue) {  
    Vue.component(ZInput.name,ZInput)  
}  
export default ZInput 
## 在packages文件夹下创建一个组件用于发布多个组件
### packages文件夹下index.js
import ZInput from './z-input/index'

const components = [
	ZInput,
]

const install = function(Vue) {
	components.map(component => {
		Vue.component(component.name,component)  
	})  
}  

if (typeof window !== 'undefined' && window.Vue){
	install(window.Vue)
}

export default {
	install,
	...components,
}
## 查看是否能用
1. 在main.js中导入  
import ZDesign from './packages'  
Vue.use(ZDesign)

## 打包
### npm init
"main": "lib/z-ui-component.umd.min.js",  
"license": "MIT"  
 "private": false,  
### build主要有四个参数
1. target:  默认为构建应用，改为 lib 即可启用构建库模式
2. name: 输出文件名
3. dest：输出目录，默认为dist这里改为lib
4. entry: 入口文件路径，默认为src/App.vue 这里改为packages/index.js
### 在package.json里添加此命令
"scripts":{
	"lib":"vue-cli-service build --target lib --name z-ui-component --dest lib --entry packages/index.js"
}
## 发布
### 如果设置了淘宝镜像
npm config set registry http://registry.npmjs.org 
### 登录
npm login  
### 发布
npm publish
### 使用
####下载 npm install z-ui-component
####引入 main.js中
import Zui from 'z-ui-component'
import 'z-ui-component/lib/z-ui-component.css'
Vue.use(Zui)
