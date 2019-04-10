#我对Vuex的理解
##安装
>在vue create 项目名称后选择下一项，选中vuex
##如何使用
>在src文件夹下新建store文件夹，在里面加入index.js,mutations.js,actions.js,getters.js,rootState.js

>修改src下的入口文件main.js
>import store from './store/index';

###修改index.js
>import Vue from 'vue';
import Vuex from 'vuex';
import * as actions from './actions';  
 // * 表示将 './actions'模块中的所有接口挂载到actions对象上  as 表示别名的意思
import * as mutations from './mutations';
import * as getters from './getters';
import state from './rootState';
Vue.use(Vuex)
const store = new Vuex.Store({
  state,
  getters,
  actions,
  mutations
})
export default store;
###修改rootState.js
>const state = {
  msg: '我是原始数据',
}
export default state;
###修改mutations.js
>export const mutationsMsg = (state, payload) => {
  state.msg = payload.msg;
}
###修改actions.js
>export const changeMsg = ({commit}) => {
  commit({
    type: 'mutationsMsg',     //对应mutation.js中的mutationsMsg方法
    msg: '我是修改后的数据~~~'
  });
};
###修改getters.js
>export const gettersMsg = state => state.msg;
###修改Hello.vue,Hello1.vue,route.js
>见newtest项目
##思路
###如何获得一个原始属性
1. 在src文件中创建store，在store中创建index.js,index.js里对各种模块的应用。
2. 在main.js中导入import store from './store/index',在new Vue()中导入模块store
3. 在rootState.js中定义原始数据
4. 在getters中定义返回函数
5. 在需要原始数据的模块中script下导入import {mapGetters} from 'vues',在computed属性下...mapGetters(['gettersMsg']),并在页面中使用{{gettersMsg}}
###如何获得原始数组属性
>修改rootState，把原始属性修改成数组
###如何获得多个原始属性
>修改rootState，在state中添加属性，获取属性一般在computed中，更改属性一般在methods中
###如何修改一个原始属性
1. 在页面中添加一个修改按钮，绑定事件@click="changeMsg"
2. 导入import {mapActions} from 'vuex'
3. 在method中匹配：...mapActions(['changeMsg'])
4. changeMsg是actions中的changeMsg,它的具体写法为
>export const changeMsg=({commit])=>{
>commit({
>type:'mutationsMsg',
>Message:'修改了'
>})
>}

5. 在mutations中更改state属性
>export const mutationsMsg=(state,payload)=>{
>state.Message=payload.Message;
>}
