---
title: setTimeout、Promise、Async/Await 的区别

tags:
  - Tag
categories:
  - Cate
cover: https://p1-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/c6790cb5f8b54a348c72a5ad0d269734~tplv-k3u1fbpfcp-zoom-in-crop-mark:1512:0:0:0.awebp?

---
1. setTimeout
console.log('script start')//1. 打印 script startsetTimeout(function(){console.log('settimeout')// 4. 打印 settimeout})// 2. 调用 setTimeout 函数，并定义其完成后执行的回调函数console.log('script end')//3. 打印 script start// 输出顺序：script start->script end->settimeout
2. Promise
Promise本身是同步的立即执行函数， 当在executor中执行resolve或者reject的时候, 此时是异步操作， 会先执行then/catch等，当主栈完成后，才会去调用resolve/reject中存放的方法执行，打印p的时候，是打印的返回结果，一个Promise实例。
console.log('script start')letpromise1=newPromise(function(resolve){console.log('promise1')resolve()console.log('promise1 end')}).then(function(){console.log('promise2')})setTimeout(function(){console.log('settimeout')})console.log('script end')// 输出顺序: script start->promise1->promise1 end->script end->promise2->settimeout
当JS主线程执行到Promise对象时，
- promise1.then() 的回调就是一个 task
- promise1 是 resolved或rejected: 那这个 task 就会放入当前事件循环回合的 microtask queue
- promise1 是 pending: 这个 task 就会放入 事件循环的未来的某个(可能下一个)回合的 microtask queue 中
- setTimeout 的回调也是个 task ，它会被放入 macrotask queue 即使是 0ms 的情况
3. async/await
asyncfunctionasync1(){console.log('async1 start');awaitasync2();console.log('async1 end')}asyncfunctionasync2(){console.log('async2')}console.log('script start');async1();console.log('script end')// 输出顺序：script start->async1 start->async2->script end->async1 end
async 函数返回一个 Promise 对象，当函数执行的时候，一旦遇到 await 就会先返回，等到触发的异步操作完成，再执行函数体内后面的语句。可以理解为，是让出了线程，跳出了 async 函数体。
举个例子：
asyncfunctionfunc1(){return1}console.log(func1())

很显然，func1的运行结果其实就是一个Promise对象。因此我们也可以使用then来处理后续逻辑。
func1().then(res => {
    console.log(res);  // 30
})
