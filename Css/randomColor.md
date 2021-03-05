# css 设置随机色

**如何使用 scss 变量，循环快速实现随即色**

```scss
$colors: red, orange, yellow, green, blue, purple;

@for $i from 1 through length($colors) {
  .swiper-slide:nth-child(#{length($colors)}n + #{$i}) {
    background: lighten(nth($colors, $i), 20%);
  }
}
```
