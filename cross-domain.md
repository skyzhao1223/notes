# Cross Domain 跨域

## 什么是域？
域名示例：https://www.a.com:8080/path/a.js

协议 :// 三级域名 . 二级域名 . 顶级域名 : 端口 [ / 路径 ] [ / 文件 ]

## 什么是跨域？
协议、域名、端口中任意一者不同即形成跨域。
```
URL 说明 是否允许通讯

http://www.a.com/a.js
http://www.a.com/b.js 同域名 允许

http://www.a.com/a.js
http://www.a.com/path/b.js 同域名不同路径 允许

http://www.a.com/a.js
https://www.a.com/path/b.js 同域名不同协议 不允许

http://www.a.com/a.js
http://www.a.com:8000/b.js 同域名不同端口 不允许

http://a.com/a.js
http://www.a.com/b.js
http://blog.a.com/b.js 顶级域名相同，子域不同 不允许（cookie也不能访问）

http://www.a.com/a.js
http://10.20.30.40/b.js 域名与域名对应IP 不允许
```

## # document.domain

父子页面同时设置相同的**document.domain**属性（只能设置成自身或更高一级的父域，且主域必须相同）。

该方法只适用于不同子域的框架间交互。

## # location.hash

父 -> 子：直接修改iframe的hash，子页面中监听hash。

子 -> 父：在子页面中创建与父同域的iframe（c），并向其传递hash；在c中监听hash并向顶层传递。

缺点：
- 有些浏览器不支持onhashchange事件，需要轮询。
- 数据暴露在url，且容量、类型有限。

## # postMessage from HTML5
```js
// Page A
window.onload = function() {
    let iframe = document.getElementById('id')
    let targetOrigin = 'http://www.a.com' | '*'
    let data = String | Object //IE8、9不支持Object
    iframe.contentWindow.postMessage( data, targetOrigin )
}
```