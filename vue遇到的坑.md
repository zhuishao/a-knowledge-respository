#vue遇到的坑
1.在用v-for 的时候如果遇到需要两个属性，则使用（item，index）而不是｛item,index｝,并且要添加：key=“index”
##mouted里不能给data赋值
在mouted中
const self=this;
##字符串拼接
`${info.file.name} file uploaded successfully.`
##页面需要使用对象，对象会有赋值操作时要进行初始化定义
##路由跳转
