### 背景

由于我司后台管理系统目前由 vue 转 react，使用 antd 框架配合 ant design pro 实现，而业务代码中存在很多重复的逻辑，比如开发一个新页面时，需要创建、配置路由文件以及页面文件，同时这些业务代码中，大部分是一些公用的组件，比如 protable,一些 react 组件等。为了避免重复、机械的人为工作，可以采用 node 实现业务页面模版生成器。

### 实现思路

实现一个 npm 包，暴露出来 generator 脚本，该脚本可通过参数配置文件夹名和文件名称，以及文件位置。

### 实现

#### 1.创建一个 npm 包

```javascript
mkdir butter-react-page-generator // 创建npm包
cd butter-react-page-generator // 进入目录
npm init -y
code . // 在vscode中打开该包
```

#### 2.创建 bin 文件夹，里面配置 generate.js 文件（可执行脚本），该文件需要配置到 pageage.json 文件中，下次当我们的项目 install 该包时，会直接在项目的 node_modules/.bin 目录下链入该脚本

#### 3.通过 npm link 将 npm 模块链接到对应的运行项目中去，方便地对模块进行调试和测试

#### 4.读取模版文件后，根据输入生成目录（或者文件生成对应的代码）

#### 5.开发完成后，发布到私有 npm 或者官方 npm 上，在 react 项目中安装后，即可以执行该脚本快速生成模版文件，简化原有复制粘贴流程
