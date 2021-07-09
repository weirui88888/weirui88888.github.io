# 介绍

## 用于记录一些工作和学习中遇到的问题，方便回顾和总结。

### 使用方式

- npm run dev 启动本地服务
- 创建 md 文件，配置 SUMMARY.md 目录
- 写完后执行 npm run tree 生成 gitbook 目录
- 替换 README.md 中的目录结构
- git add . 提交文件
- git commit （执行该命令后会执行 hooks 自动触发 deploy 命令，会自动部署到 gh-pages 分支，无需手动部署）

### 目录结构

```
├── Blog
│   └── blog.md
├── Code
├── Css
│   ├── randomColor.md
│   └── 集合元素大于第N个.md
├── Javascript
│   ├── Aop.md
│   ├── Array
│   │   ├── firstArray.md
│   │   └── flatArray.md
│   ├── JS核心概念.md
│   ├── Promise
│   └── pretty-monitor-logger.md
├── Node
│   ├── generator.md
│   └── operation-log.md
├── README.md
├── React
│   └── 快捷键.md
├── Remark
│   └── alioss.md
├── SUMMARY.md
├── Web
│   └── readme.md
└── book.json
```
