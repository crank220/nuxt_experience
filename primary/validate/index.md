## validate
__如果校验方法返回的值不为 true， Nuxt.js 将自动加载显示 404 错误页面。__
```javascript
export default {
  validate ({ params }) {
    // Must be a number
    return /^\d+$/.test(params.id)
  }
}
```
__你也可以在validate 方法中校验 store 的数据 (如果 store 此前在 nuxtServerInit 方法 中被设置了的话):__
```javascript
export default {
  validate ({ params, store }) {
    // 校验 `params.id` 是否存在
    return store.state.categories.some(category => category.id === params.id)
  }
}
```


___您还可以在验证函数执行期间抛出预期或意外错误：___
```javascript
export default {
  async validate ({ params, store }) {
    // 使用自定义消息触发内部服务器500错误
    throw new Error('Under Construction!')
  }
}
```