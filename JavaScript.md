#JavaScript
##递归
let factorial =(function f(num){
	if(num<=1){
		return 1;
	}else{
		return num*f(num-1);
	}
})