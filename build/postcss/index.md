## postcss

### 浏览器兼容
```javascript
postcss: {
  preset: {
    autoprefixer: {
      overrideBrowserslist: ['last 2 versions']
    }
  }
},
```

### 插件

```javascript
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
```