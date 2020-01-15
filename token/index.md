## 服务端获取vuex token

<p>刷新的时候 实际上 store的值是清空的， 你可以 console.log一下， 有时候插件是无法实时更新的， 你看下 nuxt官网的 路由鉴权 https://zh.nuxtjs.org/example... 要将要保存的用户信息存到session里面的， 然后通过 nuxtServerInit 周期 写入到前端层， 当然 官网这里还有一些问题， 这里中间层用到的 session模块 是只能在开发模式下， 生成模式是无法运行的， 要用 redis</p>

## 使用express-session、node/express
[官方](https://zh.nuxtjs.org/examples/auth-routes/#%E4%BD%BF%E7%94%A8-express-%E5%92%8C-sessions)

[demo](https://codesandbox.io/s/github/nuxt/nuxt.js/tree/dev/examples/auth-routes?from-embed)

## 解决
[redis](../redis/index.md)