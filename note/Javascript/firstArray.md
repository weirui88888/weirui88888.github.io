# 获取数组的前 N 项目

## 实现

```javascript
module.exports = (arr, index = 1) => {
  if (!Array.isArray(arr)) {
    return new TypeError('Expected Array, got ' + typeof arr)
  }
  if (arr.length === 0) {
    return null
  }

  return Array.from({ length: index > arr.length ? arr.length : index }).reduce(
    (acc, prev, index) => [...acc, arr[index]],
    []
  )
}
```

<!-- ![PNG](\images\spring.png) -->
