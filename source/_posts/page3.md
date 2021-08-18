---
layout: post
category: 前端
title: Vue基础 + 开发规范
date: 2021-06-08 17:36:05
tags: 前端设计规范
---

## vue基础+开发规范
### vue 业务组件创建详解
#### Vue组件构建
#### 业务编写，Vue写法详解
#### 代码结构及创建组件

> 说明： 针对业务需求我们可以选定了是使用单页应用开发还是多页应用开发，对于多页应用的项目，仅仅是不使用路由，其他的开发模式跟单页应用开发模式是一样的。
> 原则上： 组件的规模尽量颗粒化，即一个页面可由多个小组件拼凑而成，同时抽离公共组件部分，如：一个页面由头部组件、尾部组件、列表组件、按钮组件、loading组件再加上业务代码拼凑而 成，下面举个例子来说明如何创建组件。

#### 创建项目步骤
第一步： 创建文件，组件的命名尽量与业务相关，如我需要创建一个银行选择器组件，那么命名可以为bankSelect.vue; 组件命名使用驼峰命名法；

第二步： 添加路由，找到index文件夹下的router文件夹，对router下的index.js进行路由添加，此配置在多页应用中可忽略
``` javascript
import Hello from '../components/hello.vue' // （头部先引入组件）
routes: [	//（在路由配置中新增路由）
  {
    path: '/hello',
    name: 'Hello',
    component: Hello
  }
]
```

第三步： 对hello.vue文件添加html（结构）、css（样式）、js（功能）
``` javascript
<template>
    <a class="button">{{ text }}</a>
</template>
<style>
    .button {
        color: red;
    }
</style>
<script>
    export default {
        data () {
            return {
                text: 'hello world'
            }
        }
    }
</script>
```

### Vue业务开发语法详解

#### Vue生命周期

#### 生命周期： Vue实例在被创建时需要经过一系列的初始化过程，同时也会运行一些叫做生命周期的钩子函数

#### 生命周期的作用： 主要为开发者提供编写自定义代码的机会，如：数据的请求、数据的预处理等。

#### 生命周期的内容：
