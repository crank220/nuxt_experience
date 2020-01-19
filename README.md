# nuxt_experience

## Technology stack
```
vue【nuxt【vue-router + vuex + vue-meta + axios + vue-loader + vue-server-renderer】 + iview 】+ ES6 + sass + jquery + node + webpack + babel
```
## 目录

1. primary：
    - [babel](./primary/babel/index.md)
    - [jQuery](./primary/jQuery/index.md)
    - [meta](./primary/meta/index.md)
    - [pm2](./primary/pm2/index.md)
    - [validate](./primary/validate/index.md)
2. senior：
    - [axios](./senior/axios/index.md)
    - [redis](./senior/redis/index.md)
    - [router](./senior/router/index.md)
    - [style](./senior/style/index.md)
    - [token](./senior/token/index.md)
    - [vuex](./senior/vuex/index.md)
3. build：
    - [dev](./build/dev/index.md)
    - [extractCSS](./build/extractCSS/index.md)
    - [optimization](./build/optimization/index.md)
    - [postcss](./build/postcss/index.md)

## merit
+ 从零开始搭建Vue项目
+ 服务端渲染
+ 前后端分离
+ seo
+ 资源解压
+ Git版本控制
+ Md组件
+ redis
+ 响应式解决方案
+ Ie兼容
+ 自动代码分层
+ 强大的路由功能，支持异步数据
+ 静态文件服务
+ ES6

## life cycle
  + asyncData(最重要的一个键, 支持 异步数据处理，另外该方法的第一个参数为当前页面组件的 上下文对象。)
    - 在组件（限于页面组件）每次加载之前被调用
    - 它可以在服务端或路由更新之前被调用
    - 在这个方法被调用的时候，第一个参数被设定为当前页面的上下文对象，你可以利用 asyncData方法来获取数据，Nuxt.js 会将 asyncData 返回的数据融合组件 data 方法返回的数据一并返回给当前组件。
  + fetch(在渲染页面前被调用，作用是填充状态树 (store) 数据，与 asyncData 方法类似，不同的是它不会设置组件的数据。)
  + nuxtServerInit(如果在状态树中指定了 nuxtServerInit 方法，Nuxt.js 调用它的时候会将页面的上下文对象作为第2个参数传给它（服务端调用时才会酱紫哟）。当我们想将服务端的一些数据传到客户端时，这个方法是灰常好用的。)
    - 这时context被赋予nuxtServerInit作为第二个参数，它与asyncData或fetch方法相同。  
      nuxtServerInit 方法接收的上下文对象和 fetch 的一样，但不包括 context.redirect() 和 context.error()
    - 注意：异步nuxtServerInit操作必须返回Promise来通知nuxt服务器等待它们  

[plugins demo、路由鉴权](https://segmentfault.com/a/1190000012280812)

[参考](https://github.com/wmui/essay)

[!!!](https://www.jianshu.com/p/840169ba92e6)