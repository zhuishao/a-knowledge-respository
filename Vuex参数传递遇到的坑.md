#vuex参数传递遇到的坑
###在页面中如何传递
在methods中...mapAction(['actions中映射的函数'])，
调用时：this.函数（参数）

在actions中
export const 函数名 = （｛commit｝，state//传过来的参数）=>{
commit({
	type:'mutationNodes'//mutations中的函数
	nodes:state//把参数传入payload中
});
};

在mutations中
export const mutationsMsg = (state,payload) => {
	state.nodes=payload.nodes
};

在rootState中
const state={
	nodes:['AL']
};
export default state;
###修改store中数据
1. 定义actions中内容 setUser({commit},){ commit({type:'setUser',state})}
2. 在mutations:{
		setUser(state,payload){
			
		}

	}

###获得数据并在页面使用
1. 现在store.js中定义user:{username:'sdf',passowrd:'ddd'}
2. 在computed中映射 ...mapState(['user'])
3. 使用{{user.username}}