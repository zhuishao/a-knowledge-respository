#对ant-design的理解
##导航菜单
###key
>key是每个<a-menu>下级菜单里的必有属性，用以确认你点击的是哪个option，在<a-menu>的@click="handleClick"，handleClick函数用来获取你对option的点击。

###defaultSelctedKeys
>在<a-menu>中的属性，:defaultSelectedKeys="['2']",里面的2表示的是key的值，用来表明菜单第一次显示的时候，显示的是值为2的option
###openKeys(.sync)
>在<a-menu>中的属性，:openKeys.sync="openKeys"，openkeys是data中的数据，openksys中是一个数组，openKeys: ['sub1'],表明key为'sub1'的菜单被展开了。
###mode
>在<a-menu>中的属性，表明该菜单类型mode="",vertical vertical-right horizontal inline,分别是垂直、水平、和内嵌模式
###theme
>主题颜色 theme="" light,dark
###titleClick
>SubMenu事件，点击子菜单标题
##表格
主体是一个<a-table></a-table>
###columns-表格列的配置描述，多个columns组成一个columns
>const columns=[{},{}]
>{title:'Name',//列名
>dataIndex:'name',//数据项中的名字
>sorter:true,//是否排序，也可以为一个排序函数
>width：20%,//列宽度
>scopedSlots:{customRender:'name'},//暂时未知,customRender是复杂数据的渲染函数@return可以设置表格行/列合并
>filters:[｛text:'Male',value:'male'｝，{text:'Female',value:'female'}],//表头筛选菜单栏object[]
>}
###mounted中的操作
mounted(){
this.fetch();
}
###data中应该保存的数据
data(){
return {
data:[],
pagination:{},
loading:false,
columns//就是上面定义的columns
}
}
###rowkey
##分页

##布局
###flex
