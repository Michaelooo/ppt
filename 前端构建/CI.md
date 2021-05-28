---
marp: true
theme: default
title: 前端构建那些事儿
description: 前端构建那些事儿
paginate: true
_paginate: false
---

<!-- Global style -->
<style>
section {
  /* font-size: 36px; */
  background-size: 100% 100%;
}

h1 {
  color: rgba(255,134,72,.96);
}

img[src*="#width-full"] {
 width: 80%;
 height: 80%;
}

</style>


前端构建那些事儿
==
大前端 程鹏飞

---
# 为什么聊这个话题？

* 前端工程化?
* CI/CD ？
* 前端构建 = webpack ?

---
# 今天分享的小目标

帮助**新人前端**或**非前端同学**了解到有关前端资源打包的历史化进程

---
# 我要讲什么？

1. 简单聊一下前端的作业流
2. 回忆一下前端打包的发展历史
3. 认识多多的前端构建
4. 了解未来的前端构建工具

---
# 1.前端的标准作业流

## 你所关注的一切都其实是资源

打包资源 => 发布资源 => 访问资源

---
# 资源是怎么出来的

```js
(function build(业务逻辑代码,第三方代码) {
  资源分析();
  代码编译();
  资源打包();
})();
```

```bash
# 以大数据平台工程为例:data-blood-website
du -sh ./node_modules
# 第三方代码 566M

du -sh ./src
# 业务逻辑代码 2.2M

du -sh ./dist
# 构建最终的静态代码 12M

du -sh ./.fdd
# 构建最终的node代码 5.8M + diskUseage(node_modules/) M
```

---
# 第三方包管理工具的进化之路

## [Requirejs](https://requirejs.org/) => [Bower](https://bower.io/) => [Npm](https://www.npmjs.com/) => [ESM(CDN)](https://www.jsdelivr.com/esm)?

---
![image w:1200 h:600](https://oss-public.fangdd.com/prod/static/Fo9bjfbEqT0lK93Miu5ei2E79gmo.jpg)

> 数据来源：http://www.modulecounts.com/

---
# 2.回忆一下前端打包的发展历史

---
# 前端的构建工具发展历史

1. Npm Script
2. Grunt/Glup 
3. Webpack/Rollup/Browserify 
4. Webpack next/Snowpack/Vite

---
# Npm script

```json
{
  // ...
  "scripts": {
    "build": "node build.js"
  }
}

```


---
# Glup

```js
const { src, dest, parallel } = require('gulp');
const pug = require('gulp-pug');
const less = require('gulp-less');
const minifyCSS = require('gulp-csso');
const concat = require('gulp-concat');

function html() {
  return src('client/templates/*.pug')
    .pipe(pug())
    .pipe(dest('build/html'))
}

function css() {
  return src('client/templates/*.less')
    .pipe(less())
    .pipe(minifyCSS())
    .pipe(dest('build/css'))
}

function js() {
  return src('client/javascript/*.js', { sourcemaps: true })
    .pipe(concat('app.min.js'))
    .pipe(dest('build/js', { sourcemaps: true }))
}

exports.js = js;
exports.css = css;
exports.html = html;
exports.default = parallel(html, css, js);

```

---
# webpack

Webpack 是一个打包模块化的JavaScript的工具，在Webpack里一切文件皆模块，通过 loader 转换文件，通过Plugin 注入钩子，最后输出由多个模块组合成的文件。Webpack 专注于构建模块化项目。

---
![bg 95%](https://yuguo.site/images/BuildTools/pack.png)

---

<!-- Scoped style -->
<style scoped>
h1 {
  text-align: center;
}
</style>
# next ? 
---
# 3.房多多的构建怎么玩？

## 一个成熟的前端应用应该 学会主动测试、自己打包、自己构建、自己运行、快速下线

1. 多多的前端工程结构
2. 发布系统

---
# 多多的前端工程结构

## 基于自研种子工程打造的支持多特性的前后端分离项目

* 在 node 端使用 babel 转义 es next代码
* 在客户端使用 webpack 打包静态资源
* 所有的静态资源都通过 CDN 访问
* 内部组件通过私库访问

---
# web 端 Webpack 的优化

## 完全集成种子项目，无感知开发

* 开发模式下的热更新
* Postcss + css 预编译 支持
* 自动的 polyfill 支持
* 动态链接库 DLL
* 基于 webpack v4 的 treeshaking， code split 
* 基于 webpack v5 的 缓存模式， lazy complie 

---
# 你知道吗 ?

> 程序错误中，80% 是语法错误，16% 是简单的逻辑错误，0.8% 才是困难的问题。

## 构建时的异常，80% 是语法错误，16% 是环境差异，0.8% 才是灵异报错。

---
# 发布系统的构建流程

语法校验 => 代码入库 => 触发构建（打包静态资源）=> 静态资源上传 CDN => 构建资源镜像 => 启动容器（分配资源） 

---
# 4.目前新流行的几款前端构建工具

如果一个新技术不能用于生产，那就永远只能是个玩具

1. esbuild
2. snowpack
3. vite

---
# esbuild (很快啊，但是还不能用于生产)

![](https://camo.githubusercontent.com/aefd7a399642431d15a1511834bac0a7e76c303088df271918a582ba8123dc79/68747470733a2f2f696d672e616c6963646e2e636f6d2f696d6765787472612f69312f4f31434e3031687a48754450314a5875427652675837785f2121363030303030303030313033392d322d7470732d3830302d3137302e706e67)

* **可以把我理解为： Babel**
* 我是 Go 写的，我很快
* 我提供了转译(bundler)和代码压缩(minifier),我很快
* 我生态还不够完善，毕竟我还抢不过 Babel 的饭碗

---
# snowpack

* 我完美利用浏览器 ESM import 能力，我也很快
* 我提倡不打包 node_modules，我是 bundleless的

---
# vite

* 我可用于生产环境
* 使用 rollup 打包,也利用了 ESM import ,我是 bundleless的
* 我配套设施很完善，css、多包、服务端渲染等
* 我是尤大开发维护
---
# 多多未来可以做什么？

* 提升代码构建速度，发布系统 CI 流程?
* 尝试下 vite ?

---
# 对前端的一些思考

> 某鸡汤：前端不是因为做交互界面，而是因为站在业务的最前端

---
# 给 3 年+ 的前端一个建议

## 前端要比其他技术同学，更加深入业务
---
<!-- Scoped style -->
<style scoped>
h1 {
  text-align: center;
}
</style>

# 因为相信 所以看见