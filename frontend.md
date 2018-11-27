# frontend

## 继承

### 显式原型 prototype

### 隐式原型 __proto__

## 类型判断

### typeof

引用类型存储值会出现问题，无论引用的是什么类型的对象，它都返回"object"。

### instanceof

[JavaScript instanceof 运算符深入剖析](https://www.ibm.com/developerworks/cn/web/1306_jiangjj_jsinstanceof/index.html)

## 模块化

> 参考：[前端模块化：CommonJS,AMD,CMD,ES6](https://juejin.im/post/5aaa37c8f265da23945f365c)、
> [歡迎來到大分叉時代 - AMD 與 CommonJS 的發展](https://ithelp.ithome.com.tw/articles/10191574)、[前端模块化开发那点历史](https://github.com/seajs/seajs/issues/588)、[阮一峰 - Module 的加载实现](http://es6.ruanyifeng.com/#docs/module-loader)

### CommonJS - Node.js

原ServerJS。同步加载模块，适用于服务端。输出值拷贝。

### AMD - require.js

依赖前置、提前执行。

### CMD - sea.js

依赖就近、延迟执行。

### ES6 Module

在语言标准的层面上，实现的模块功能。输出值引用。

### AMD、CMD转换为CommonJS（同步模块）

AMD 要转换为同步模块，除了去掉define函数的包裹外，只需要在头部使用require把依赖声明好。

而 CMD 只需要去掉define函数的包裹即可。

## Virtual Dom 虚拟Dom
- [virtual-dom原理与简单实现](https://juejin.im/post/5a21621af265da4304066c8d)

## Cross-Domain 跨域
- [【原创】说说JSON和JSONP，也许你会豁然开朗，含jQuery用例](https://www.cnblogs.com/dowinning/archive/2012/04/19/json-jsonp-jquery.html)

[instanceof typeof](https://juejin.im/post/5b0b9b9051882515773ae714)

[new 步骤]()

[去重](https://juejin.im/post/5949d85f61ff4b006c0de98b)

[深拷贝](http://www.alloyteam.com/2017/08/12978)
Object.assign（可枚举）、属性赋值、JSON、$.extend(true,…)

[ECMAScript 6 入门](http://es6.ruanyifeng.com)
[Symbol](http://es6.ruanyifeng.com/#docs/symbol)
[Set 和 Map数据结构](http://es6.ruanyifeng.com/#docs/set-map)
[Proxy](http://es6.ruanyifeng.com/#docs/proxy)
[Reflect](http://es6.ruanyifeng.com/#docs/reflect)
[Generator](http://es6.ruanyifeng.com/#docs/generator)

[事件机制](https://www.jianshu.com/p/916230ad9229)

[调用栈Call Stack](https://segmentfault.com/a/1190000010360316)
[调用栈、尾递归和手动优化](https://www.jianshu.com/p/3182429e26b5)

[React Redux](https://juejin.im/entry/58cf445cb123db3f6b43adcc)

[前端安全](https://juejin.im/entry/598d6eb46fb9a03c3a25d2c1)
[前端安全-美团](https://tech.meituan.com/fe_security.html)
[安全](http://imweb.io/topic/56f895bf14ea0f7263803d5b)
[XSS](https://segmentfault.com/a/1190000013315450)

[PWA](https://juejin.im/post/5a6c86e451882573505174e7)

> App Manifest - manifest.json \
> Service Worker - \
> Web Push

[节流]()

[可枚举]()

[获取元素位置]()

[工程化](https://juejin.im/post/5ac9c6f451882555677ed301)

[圣杯布局](https://segmentfault.com/a/1190000004524159)

[同构直出](https://www.jianshu.com/p/d4d2abff93da)

[toLocalString](https://juejin.im/post/5ac7079f5188255c637b3233)

## document.ready && window.onload

- 标准浏览器
    - 监听DOMContentLoaded事件，该事件会在DOM解析完成以后触发。
- 非标准浏览器
    - （webkit）如果浏览器存在document.onreadystatechange事件，该事件触发时，如果document.readyState=complete，可视为DOM加载完毕。
    - （ie）循环调用document.documentElement.doScroll，执行成功时可视为DOM加载完毕。[→hack来源](http://javascript.nwbox.com/IEContentLoaded/)
    - （ie only）添加有defer（延迟执行）属性的script标签，通过监听它的readyState为ready/complete判断DOM加载完毕。(缺点：当页面中有iframe的时候，会等iframe里所有资源加载完才触发)
> 参考：[DOM ready原理](https://www.jianshu.com/p/0fa2a4b1d752)


## 常用工具

[caniuse](caniuse.com)


<!-- ![img](https://img-blog.csdn.net/20170919170357124?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvY3J5c3RhbDY5MTg=/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast) -->