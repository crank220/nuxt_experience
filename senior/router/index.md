## 路由

### 自定义路由
[官方 自定义路由](https://zh.nuxtjs.org/guide/vuex-store/#nuxtserverinit-%E6%96%B9%E6%B3%95)

_您可能希望扩展Nuxt.js创建的路由。您可以通过extendRoutes选项执行此操作。_

+ *例如添加自定义路由:*
  > **nuxt.config.js**

  ```javascript
  export default {
    router: {
      extendRoutes (routes, resolve) {
        routes.push({
          name: 'custom',
          path: '*',
          component: resolve(__dirname, 'pages/404.vue')
        })
      }
    }
  }
  ```
+ 参考

  __[精品文章](https://segmentfault.com/a/1190000017468917)__