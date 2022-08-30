## Very代码熟悉

手头任务

- 熟悉当前VERY 项目代码库，总结自己视角发现的一些问题，输出一份文档
- 熟悉Vue3相关API

### 疑问

- Very项目

  - 包含什么？

- quasar

  - 是什么？
  - 包含什么？
  - 能做什么？

- 代码规范

  - 用什么保证代码格式一致？我一保存文件就会变更

  - 要装哪些vscode插件？

    [1] [分享 6 个 Vue3 开发必备的 VSCode 插件](https://segmentfault.com/a/1190000042293785)

- css

  - css样式书写最佳实践

    - tailwindcss

    - quasar-ui

    - css变量

      a_b

      嵌套<4

  - 覆盖quasar-ui的最佳方式？

  - 主题实现原理

    css变量

  - 定义变量在哪里？

    src/css

  - 命名规范

  - 目前有手机端适配需求吗？怎么适配？

  - v-bind是将js变量绑定到css吗

    ![image-20220829150757381](https://cdn.gincool.com/imgimage-20220829150757381.png)

  - 除了搜索外，如何快速定位该类样式的代码？

    ![image-20220829151612689](https://cdn.gincool.com/imgimage-20220829151612689.png)

- 钱包

  - 支持哪些钱包？
  - walletConnect？

- 国际化

  - 国际化命名规范？

- 状态管理

  - pinia特点
  - pinia最佳实践

- ssr

  - 怎么分辨是ssr

### 重点问题

- quasar
- css样式书写最佳实践
- 状态管理pinia
- 统一代码风格
- 图表（echart）highchart

## Quasar

Quasar (pronounced `/ˈkweɪ.zɑɹ/`) is an MIT licensed open-source **Vue.js** based framework, which allows you as a web developer to quickly create responsive++ websites/apps in many flavours

[1] [Quasar](https://quasar.dev/introduction-to-quasar)

## Pinia

[1] [Vue3 + vite + Ts + pinia + 实战 + 源码 +全栈](https://www.bilibili.com/video/BV1dS4y1y7vd?p=58&spm_id_from=pageDriver&vd_source=4065bea3d3139c3fda8b128a6a3a90a7)

```sh
yarn add pinia
```

![image-20220829223128251](https://cdn.gincool.com/img/image-20220829223128251.png)

### 修改state

一般有5种修改state方法

![image-20220829224501808](https://cdn.gincool.com/img/image-20220829224501808.png)

### 解构

pinia解构**不**具有响应式，但可以通过 `storeToRefs` 包裹解决，跟 `toRefs` 类似

![image-20220829225013455](https://cdn.gincool.com/img/image-20220829225013455.png)

### Actions和Getters

Pinia的Actions支持同步和异步方法，在Pinia中不存在mutations的概念

Getters与computed类似

### 一些API

| API        | 描述          |
| ---------- | ------------- |
| $reset     | 重置store的值 |
| $subscribe | 订阅变化      |
| $onAction  | 监听Action    |

### 插件

```ts
// 注册插件
store.use(plugin)
```

一个持久化的插件示例

![image-20220829230732371](https://cdn.gincool.com/img/image-20220829230732371.png)
