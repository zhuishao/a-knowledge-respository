#插件store.js的使用
##首先下载该插件
npm install store
##引用
在main.js中
import storee from 'store';
Vue.prototype.$storee=storee;
##使用方式
###设置属性
在组件页面中  
设置属性
this.$storee.set('user',{username:'zhuishao'})  
获取属性
this.$storee.get('user').username  
移除属性
this.$storee.remove('user')  
移除所有属性
this.$storee.clearAll()  
遍历所有键值
this.$storee.each(function (value, key)
	{
		console.log(key,'==',value);
	}
)