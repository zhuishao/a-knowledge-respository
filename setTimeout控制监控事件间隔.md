#setTimeout控制监控事件间隔
##需要参数
var `timer_is_on=0`
##需要一个监控事件
function watch() {
        drawing.onmousemove=function (ev) {
            console.log(ev);
            context.clearRect(0,0,2000,2000);
            context.fillRect(ev.clientX,ev.clientY,10,10);
        }
    }
##需要一个开始事件
function startWatch() {
        if (!timer_is_on){
            timer_is_on=1;
            watch();
            setTimeout(stopWatch,5000);

        }
    }
##需要一个结束事件
 function stopWatch() {
        if(timer_is_on){
            timer_is_on=0;
            drawing.onmousemove=null;
            setTimeout(startWatch,200);
        }
    }
##具体思路
开始监控后再5000毫秒后执行结束监控，结束监控后在200毫秒后执行开始监控