# Aop 面向切面编程

## 特性

从主关注点中分离出横切关注点是面向侧面的程序设计的核心概念。分离关注点使得解决特定领域问题的代码从业务逻辑中独立出来.

业务逻辑的代码中不再含有针对特定领域问题代码的调用，业务逻辑同特定领域问题的关系通过侧面来封装、维护.

这样原本分散在在整个应用程序中的变动就可以很好的管理起来。

## 代码

```javascript
Function.prototype.after = function (action) {
  var func = this
  return function () {
    var result = func.apply(this, arguments)
    action.apply(this, arguments)
    return result
  }
}
Function.prototype.before = function (action) {
  var func = this
  return function () {
    action.apply(this, arguments)
    return func.apply(this, arguments)
  }
}

const doSomething = a => {
  console.log(a)
}
let clickHandler = a => {
  // n行代码
  doSomething(a)
  //n 行代码
}
clickHandler = clickHandler
  .before(a => {
    console.log(a)
  })
  .after(a => {
    console.log(a)
  })
clickHandler('person') // 执行结果和预期一致
```

## 参考资料

- [解读面向切面编程(AOP)](https://juejin.cn/post/6844903700368982029)
- [aop-monitor 实现埋点分离代码](https://github.com/mini-peanut/aop-monitor)
