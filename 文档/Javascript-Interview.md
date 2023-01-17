

- WebView和Native的通信机制
- JSBridge
- 响应式编程
- 函数式编程
- 设计模式
- MMVM、MVC、Sington
- 二维码如何识别的，三方库？
- 如何mock数据，如果服务器返回的数据突然改变key值怎么半，怎么做json转model
- https流程
- 对称加密，非对称加密



null和undefined的区别

JS：settimeout 函数可以准确执行么？为什么？

setinterval是干什么用的？有缺陷吗？

```
async function async1() {
	console.log('async1 start');
	await async2();
	console.log('asnyc1 end');
}
async function async2() {
	console.log('async2');
}
console.log('script start');
setTimeout(() => {
	console.log('setTimeOut');
}, 0);
async1();
new Promise(function (reslove) {
	console.log('promise1');
	reslove();
}).then(function () {
	console.log('promise2');
})
console.log('script end');

answer：

script start
async1 start
async2
promise1
script end
asnyc1 end
promise2
setTimeOut
```



原型链

原型链可以做什么用



JS中怎么实现枚举



箭头函数有什么好处



let var有什么区别



柯里化有了解过么？有什么好处



闭包有了解过么，有什么作用？



单例模式了解么？怎么实现，要注意什么？



了解过防抖和节流么？



js 的加载、解析和执行会阻塞页面的渲染过程，因此我们希望 js 脚本能够尽可能的延迟加载，提高页面的渲染速度。

我了解到的几种方式是：

1. 将 js 脚本放在文档的底部，来使 js 脚本尽可能的在最后来加载执行。
2. 给 js 脚本添加 defer属性，这个属性会让脚本的加载与文档的解析同步解析，然后在文档解析完成后再执行这个脚本文件，这样的话就能使页面的渲染不被阻塞。多个设置了 defer 属性的脚本按规范来说最后是顺序执行的，但是在一些浏览器中可能不是这样。
3. 给 js 脚本添加 async属性，这个属性会使脚本异步加载，不会阻塞页面的解析过程，但是当脚本加载完成后立即执行 js脚本，这个时候如果文档没有解析完成的话同样会阻塞。多个 async 属性的脚本的执行顺序是不可预测的，一般不会按照代码的顺序依次执行。
4. 动态创建 DOM 标签的方式，我们可以对文档的加载事件进行监听，当文档加载完成后再动态的创建 script 标签来引入 js 脚本。
