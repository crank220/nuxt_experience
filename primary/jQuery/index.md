## jQuery

### jquery => jQuery
>jQuery requires a window with a document

>jsdom and process.client

### require && alias
> 引用&声明
```javascript
const webpack = require('webpack')
build: {
  plugins: [
    new webpack.ProvidePlugin({
      jQuery: 'jquery'
    })
  ],
}
```