#html5定时器requestAnimationFrame
## 启用
let t = requestAnimationFrame( function(){});
## 关闭
cancelAnimationFrame(t);
## 兼容
if(!window.requestAnimationFrame){
    var lastTime = 0;
    window.requestAnimationFrame = function(callback){
        var currTime = new Date().getTime();
        var timeToCall = Math.max(0,16.7-(currTime - lastTime));
        var id  = window.setTimeout(function(){
            callback(currTime + timeToCall);
        },timeToCall);
        lastTime = currTime + timeToCall;
        return id;
    }
}
if (!window.cancelAnimationFrame) {
    window.cancelAnimationFrame = function(id) {
        clearTimeout(id);
    };
}