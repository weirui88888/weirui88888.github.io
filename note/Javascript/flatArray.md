# 拍平数组

** 如何拍平一个数组，类似于 es6 提供的 flat 方法 **

```javascript
const util = require('./utils')

module.exports = arr => {
  // 封装的用于自定义抛出错误的方法
  util.throwExceptionIf(arr, util.not(util.isArray(arr)), 'expect get an arr')
  let res = Array.of()
  // 这里曾尝试使用匿名函数自执行，仿佛arguments.callee就会失效
  return (function acc(inarr) {
    for (let i = 0, length = inarr.length; i < length; i++) {
      const cur = inarr[i]
      if (Array.isArray(cur)) {
        arguments.callee(cur) // arguments.callee一般用在递归方法中，用来和当前函数进行解耦
      } else {
        res = [...res, cur]
      }
    }
    return res
  })(arr)
}
```
