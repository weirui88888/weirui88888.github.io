# 埋点监控日志

## 核心概念

从主关注点中分离出横切关注点是面向侧面的程序设计的核心概念。

## 场景

譬如在业务逻辑代码中，需要加入一些埋点日志信息。如果将这些逻辑也放在业务代码中的话，就会有强依赖耦合。借鉴 aop 设计模式，可以将这些操作从主业务逻辑代码中抽离开来。

在这个场景中：

| 主关注点 | 侧关注点 |
| :------: | :------: |
| 业务代码 | 埋点日志 |

## 优点

## 缺点

## 过程

- 选择一个合适的包名，后期发布 npm
- 修改 package.json 文件
- npm install babel-cli babel-preset-env babel-preset-stage-2 --save-dev 安装 babel 模块
- 配置.babelrc 文件
- babel --watch lib --out-dir dist --source-maps 生成 source-map 可调试
-

## 参考

- [在Javascript中进行面向切面编程](https://zhuanlan.zhihu.com/p/63917897)

- [es6 中的装饰器](https://github.com/ruanyf/es6tutorial/blob/gh-pages/docs/decorator.md)
