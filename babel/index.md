## babel

### babel-polyfill 兼容 es6 ie9+
> cnpm install babel-polyfill

### poly.js
```javascript
import 'babel-polyfill'
```

#### nuxt.config
```javascript
plugins: [
  { src: '@/plugins/poly', ssr: true },
]
```

### .babelrc
```json
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
```