# autoprefixer

## 隶属 vue-loader/postcss

## browserslist 浏览器

``
const autoprefixer=require("autoprefixer")
postcss:[require('autoprefixer')({ browsers: ['last 10 Chrome versions', 'last 5 Firefox versions', 'Safari >= 6', 'ie> 8'] })]
``

### webpack2

``
var autoprefixer = require('autoprefixer');
rules: [{
    test: /\.vue$/,
    loader: 'vue-loader',
    options: {
        // vue-loader options go here
        postcss: [require('autoprefixer')({ browsers: ['last 10 Chrome versions', 'last 5 Firefox versions', 'Safari >= 6', 'ie > 8'] })]
    }
}
``

### 浏览器兼容
postcss: {
  preset: {
    autoprefixer: {
      overrideBrowserslist: ['last 2 versions']
    }
  }
},