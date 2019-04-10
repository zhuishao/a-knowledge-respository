#json序列化和解析
##把一个JavaScript对象序列化成json
let book = {
	title:"ss",
	authors:["ssss"]
};
let jsonbook=JSON.stringfy(book);
##把一个json解析为javaScript值
let bookcopy=JSON.parse(jsonbook);