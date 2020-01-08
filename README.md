# nuxt_experience

``
vue【nuxt【vue-router + vuex + vue-meta + axios + vue-loader + vue-server-renderer】 + iview 】+ ES6 + sass + jquery + node + webpack + babel
``

## extractCSS

``
extractCSS: { allChunks: true },

optimization: { splitChunks: { chunks: "all" } },

### 将css打成文件
extractCSS: true,
``

## postcss

``
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
``

## babel

### babel-polyfill 兼容 es6 ie9+

poly.js
import 'babel-polyfill'

nuxt.config
plugins: [
  { src: '@/plugins/poly', ssr: true },
]

``.babelrc
{
  "presets": [
    [
      "env",
      {
        "modules": false,
        "useBuiltIns": "entry"
      }
    ],
    "stage-3"
  ]
}
``

## pm2
pm2 start npm --name "bookstore-render" -- run start
