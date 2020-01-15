## autoprefixer

### browserslist 浏览器

> require vue-loader/postcss/autoprefixer

+ 浏览器兼容 browserslist
```javascript
postcss: {
  preset: {
    autoprefixer: {
      overrideBrowserslist: ['last 2 versions']
    }
  }
},
```

```javascript
const autoprefixer=require("autoprefixer")
postcss:[require('autoprefixer')({ browsers: ['last 10 Chrome versions', 'last 5 Firefox versions', 'Safari >= 6', 'ie> 8'] })]
```

| 例子       |  说明                   |
|         :-|                      :-|
| 1%        |	全球超过1%人使用的浏览器   |
| 5% in US  |	指定国家使用率覆盖
| last 2 versions |	所有浏览器兼容到最后两个版本根据CanIUse.com追踪的版本 |
| Firefox ESR |	火狐最新版本 |
| Firefox > 20 |	指定浏览器的版本范围 |
| not ie <=8 |	方向排除部分版本  |
| Firefox 12.1 |	指定浏览器的兼容到指定版本 |
| unreleased versions |	所有浏览器的beta测试版本 |
| unreleased Chrome versions |	指定浏览器的测试版本 |
| since 2013 |	2013年之后发布的所有版本 |

> 筛选后查询,验证：npx browserslist 打印出所有浏览器版本支出情况

*************
[参考1](https://www.jianshu.com/p/bd9cb7861b85)

  + webpack2

  ```javascript
  var autoprefixer = require('autoprefixer');
  rules: [{
      test: /\.vue$/,
      loader: 'vue-loader',
      options: {
          // vue-loader options go here
          postcss: [require('autoprefixer')({ browsers: ['last 10 Chrome versions', 'last 5 Firefox versions', 'Safari >= 6', 'ie > 8'] })]
      }
  }
  ```