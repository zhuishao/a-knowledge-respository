#我对ES6语法糖的理解
##箭头函数
###语法
1.具有一个参数的简单函数
var singel= a=>a
single('hello,world')
2.没有参数的需要用在箭头上加上小括号
let getmsg = ()=> 'ddd'
3.多个参数
let add = (a,b)=> a+b
4.返回对象
let getobj = ()=>{return ({msg:1,dd:'ss'})}
5.排序
let arr=[2,3,4,1,5,2,6,2,4,2].sort((a,b)=>{if(a>b){return 1}else {return -1}})
##...
解构，获取子内容
比如  
let sigle=（）=> '2'  
let arr=[];  
arr.push(...sigle)

###const
const如果定义的是对象，指向对象的地址，对对象里的值不关心。  
const如果定义的是属性值，则属性值改变，输出的时候值不变。
