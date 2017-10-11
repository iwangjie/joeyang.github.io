# 不同页面之间传输数据

## 方法-：

浏览器支持localStorage可以放缓存里面用到sessionStorage也可以放在sessionStorage里面
存储:localStorage.setItem(""temp""JSON.stringify({id:""001""name:""aaa""}));
获取:localStorage.getItem(""temp"");
var json = JSON.parse(localStorage.getItem(""temp""));