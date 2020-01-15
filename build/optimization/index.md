# optimization 优化js、css

*默认:*

```javascript
{
  minimize: true,
  minimizer: [
    // terser-webpack-plugin
    // optimize-css-assets-webpack-plugin
  ],
  splitChunks: {
    chunks: 'all',
    automaticNameDelimiter: '.',
    name: undefined,
    cacheGroups: {}
  }
}
```
<details>
  <summary>details</summary>
  
  __[官方/optimization](https://zh.nuxtjs.org/api/configuration-build/#optimization)__

  在开发或分析模式下，splitChunks.name的默认值为true。 You can set minimizer to a customized Array of plugins or set minimize to false to disable all minimizers. 您可以将minimizer设置为自定义插件，或将minim设置为false以禁用所有minimize。(默认在开发环境情况下，minimize被禁用)。

  [webpack/optimization](https://webpack.js.org/configuration/optimization/)
</details>

> nuxt.js框架默认使用过了一套配置，但是看了编译出来的源码后发现css文件全部在源码里，感觉不是很利于收缩引擎的SEO，所以自定义了打包配置，代码如下：
```javascript
optimization: {
  runtimeChunk: {
    name: 'manifest'
  },
  splitChunks: {
    chunks: 'all',
    cacheGroups: {
      libs: {
        name: 'chunk-libs',
        chunks: 'initial',
        priority: -10,
        reuseExistingChunk: false,
        test: /node_modules\/(.*)\.js/
      },
      styles: {
        name: 'chunk-styles',
        test: /\.(scss|css)$/,
        chunks: 'all',
        minChunks: 1,
        reuseExistingChunk: true,
        enforce: true
      }
    }
  }
},
extractCSS: true, /** 将css单独打包成一个文件，默认的是全部加载到有事业 **/
```

### webpack 官方示例
```javascript
optimization: {
  splitChunks: {
    cacheGroups: {
      commons: {
        test: /[\\/]node_modules[\\/]/,
        // cacheGroupKey here is `commons` as the key of the cacheGroup
        name(module, chunks, cacheGroupKey) {
          const moduleFileName = module.identifier().split('/').reduceRight(item => item);
          const allChunksNames = chunks.map((item) => item.name).join('~');
          return `${cacheGroupKey}-${allChunksNames}-${moduleFileName}`;
        },
        chunks: 'all'
      }
    }
  }
}
```
------------
[参考2](https://www.jianshu.com/p/54ad0d1d43e4)