# 背景

在使用 ant design 框架的分页组件时，由于后端没有返回分页 total 数量。导致前端需要通过一些变通手段去定义分页逻辑。跟产品沟通后，可以将当前 active 分页后面的分页给隐藏，只能通过 css 实现。

以往使用 css 选择器时，没有印象有选择集合元素的第 N 个之后的所有元素，经过查询可以使用 **～** 选择器实现

# 实现

```css
.ant-pagination-item.ant-pagination-item-active ~ .ant-pagination-item {
  display: none !important;
}
```
