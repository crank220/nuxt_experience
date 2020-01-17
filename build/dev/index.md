## dev 属性配置

__dev 属性的值会被 nuxt 命令 覆盖：__

+ 当使用 nuxt 命令时，dev 会被强制设置成 true
+ 当使用 nuxt build， nuxt start 或 nuxt generate 命令时，dev 会被强制设置成 false

__nuxt.config.js：__
```javascript
module.exports = {
  dev: (process.env.NODE_ENV !== 'production')
}
```

__server.js__
```javascript
const { Nuxt, Builder } = require('nuxt')
const app = require('express')()
const port = process.env.PORT || 3000

// 传入配置初始化 Nuxt.js 实例
const config = require('./nuxt.config.js')
const nuxt = new Nuxt(config)
app.use(nuxt.render)

// 在开发模式下进行编译
if (config.dev) {
  new Builder(nuxt).build()
}

// 监听指定端口
app.listen(port, '0.0.0.0')
console.log('服务器运行于 localhost:' + port)
```

__package.json__
```javascript
{
  "scripts": {
    "dev": "node server.js",
    "build": "nuxt build",
    "start": "NODE_ENV=production node server.js"
  }
}
```

> 注意: 要运行上面的示例，你需要运行 npm install --save-dev cross-env 安装 cross-env。 如果你在非 Windows 环境下开发，你可以不用安装 cross-env，这时需要把 start 脚本中的 cross-env 去掉并直接设置NODE_ENV即可。

[官网](https://zh.nuxtjs.org/api/configuration-dev/)