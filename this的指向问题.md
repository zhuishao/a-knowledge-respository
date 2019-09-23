#this指向问题
在方法中，this 表示该方法所属的对象。  
如果单独使用，this 表示全局对象。  
在函数中，this 表示全局对象。
在函数中，在严格模式下，this 是未定义的(undefined)。  
在事件中，this 表示接收事件的元素。  
类似 call() 和 apply() 方法可以将 this 引用到任何对象。  
##分辨方法和函数
	mouted(){
	}//函数
	methods:{
		getE(){
		}//方法
	}
##函数需要调用self，方法指向的是定义他本身的环境