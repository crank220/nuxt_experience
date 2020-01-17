## mete 

### Nuxt.js 使用了 vue-meta 更新应用的 头部标签(Head) and html 属性。  
### Nuxt.js 使用以下参数配置 vue-meta:
```javascript
{
  keyName: 'head', // 设置 meta 信息的组件对象的字段，vue-meta 会根据这 key 值获取 meta 信息 
  attribute: 'n-head', // vue-meta 在监听标签时所添加的属性名
  ssrAttribute: 'n-head-ssr', // 让 vue-meta 获知 meta 信息已完成服务端渲染的属性名
  tagIDKeyName: 'hid' // 让 vue-meta 用来决定是否覆盖还是追加 tag 的属性名
}
```
__在 head 方法里可通过 this 关键字来获取组件的数据，你可以利用页面组件的数据来设置个性化的 meta 标签。__

> 为了避免子组件中的meta标签不能正确覆盖父组件中相同的标签而产生重复的现象，建议利用 hid 键为meta标签配一个唯一的标识编号。

[vue-meta](https://github.com/nuxt/vue-meta)
[官网](https://zh.nuxtjs.org/guide/views/#html-%E5%A4%B4%E9%83%A8)