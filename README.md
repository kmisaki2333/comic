# 前端解决跨域问题的方案
对于端口和协议的不同，只能通过后台解决。
1.document.domain+iframe(只有主域相同时才能使用)
1) 在www.a.com/a.html中：

document.domain = 'a.com';
var ifr = document.createElement('iframe');
ifr.src = 'http://www.script.a.com/b.html';
ifr.display = none;
document.body.appendChild(ifr);
ifr.onload = function(){
    var doc = ifr.contentDocument || ifr.contentWindow.document;
    //在这里操作doc，也就是b.html
    ifr.onload = null;
};
2) 在www.script.a.com/b.html中：

document.domain = 'a.com';

2.动态创建<script>
3.location.hash+iframe
4.window.name+iframe
5.postMessage
6.JSONP
7.WEBSOCKET
8.CORS
