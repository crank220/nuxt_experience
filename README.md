# nuxt_experience

``
vue【nuxt【vue-router + vuex + vue-meta + axios + vue-loader + vue-server-renderer】 + iview 】+ ES6 + sass + jquery + node + webpack + babel
``

## extractCSS


extractCSS: { allChunks: true },

optimization: { splitChunks: { chunks: "all" } },

### 将css打成文件
extractCSS: true,


## postcss


postcss: [
  require('autoprefixer')({ browsers: ['last 10 Chrome versions', 'last 5 Firefox versions', 'Safari >= 6', 'ie> 8'] })
],

postcss: [ autoprefixer({ browsers: ['last 2 versions'] })

postcss: [require('autoprefixer')({
  overrideBrowserslist: ['last 2 versions']
})],

### 浏览器兼容
postcss: {
  preset: {
    autoprefixer: {
      overrideBrowserslist: ['last 2 versions']
    }
  }
},

## Postcss 插件

``json
export default {
  build: {
    postcss: {
      // 添加插件名称作为键，参数作为值
      // 使用npm或yarn安装它们
      plugins: {
        // 通过传递 false 来禁用插件
        'postcss-url': false,
        'postcss-nested': {},
        'postcss-responsive-type': {},
        'postcss-hexrgba': {}
      },
      preset: {
        // 更改postcss-preset-env 设置
        autoprefixer: {
          grid: true
        }
      }
    }
  }
}
``

## demo
[参考](https://github.com/wmui/essay)

## 精品文章
[plugins demo、路由鉴权](https://segmentfault.com/a/1190000012280812)
