# 不同页面之间传输数据

## 方法-：

```js
浏览器支持localStorage可以放缓存里面用到sessionStorage也可以放在sessionStorage里面
存储:
localStorage.setItem(""temp""JSON.stringify({id:""001""name:""aaa""}));

获取:localStorage.getItem(""temp"");
var json = JSON.parse(localStorage.getItem(""temp""));
```

## 多个页面之间共享对象

1.COOKIE不能放对象，但是可以存放对象序列化之后的值，使用的是再反序列化
2.使用indexedDB