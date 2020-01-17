## axios 配置

### 不同环境请求头配置

> 需求描述：公司的有正式环境和特使环境对应不同的服务器，所以需要在请求的时候添加对应的请求头，具体配置可以参考如下代码：
package.json配置：
```javascript
  "scripts": {
    "dev": "cross-env NODE_ENV=development PORT=3333 nuxt",
    /** 本地环境：这里给环境变量NODE_ENV指定了对应的development的值和指定了运行端口 **/
    "build": "cross-env NODE_ENV=online nuxt build",
    /** 打包：指定了环境变量的值为online **/
    "start": "HOST=0.0.0.0 PORT=3333 nuxt start",
    /** 打包：指定了环境变量的值为online 端口为3333 HOST为0.0.0.0 百度了一下，
    0.0.0.0代表本机的所有ip地址,即同网段其他机器也可以访问的，
    默认的127.0.0.1由于和本地ip绑定了，所以只有绑定到本机地址的服务能被同网段其他机器访问**/
    "generate": "nuxt generate",
    "lint": "eslint --ext .js,.vue --ignore-path .gitignore .",
    "precommit": "npm run lint"
  },
```

> __axios.js配置：__

```javascript
    /** 自定义请求base_url  **/
if (process.env.NODE_ENV === 'test') {
  axios.defaults.baseURL = 'http://test'
} else if(process.env.NODE_ENV === 'online') {
  axios.defaults.baseURL = 'http://online'
} else {
   axios.defaults.baseURL = 'http://127.0.0.1'
}
```

> 这里使用的NODE_ENV由于在nuxt.js默认就存在，所以不需要定义这个变量，如果需要声明一个不存在的环境变量，需要在nuxt.config.js里面添加如下配置

```javascript
/** 下面声明了一个PATH_TYPE变量，其余的不需要改变，只需要将对应的NODE_ENV改成PATH_TYPE即可 **/
env: {
    PATH_TYPE: process.env.PATH_TYPE
}
```

> 一定要看备注：要运行上面的示例，你需要运行npm install --save-dev cross-env 安装 cross-env。如果你在非Windows环境下开发，你可以不用安装cross-env，这时需要把 start 脚本中的cross-env去掉。

