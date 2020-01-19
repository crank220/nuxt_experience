## loading

https://zh.nuxtjs.org/api/configuration-loading/#loading-%E5%B1%9E%E6%80%A7%E9%85%8D%E7%BD%AE

1. loading属性配置
  > 在页面切换的时候，Nuxt.js 使用内置的加载组件显示加载进度条。你可以定制它的样式，禁用或者创建自己的加载组件。

  > 在你的组件中你可以使用this.$nuxt.$loading.start()来启动加载条。使用this.$nuxt.$loading.finish()来使加载条结束。

2. 自定义加载进度条  
    __type: obj__  
    | 键 |	类型 |	默认值 |	描述 |
    | -- |  ---  |  ----  |  --- |
    |color|	String|	'black'	进度条的颜色|
    |failedColor|	String|	'red'	|页面加载失败时的颜色 （当 data 或 fetch 方法返回错误时）。
    |height|	String|	'2px'|	进度条的高度 (在进度条元素的 style 属性上体现)。
    |throttle	|Number	|200|	在ms中，在显示进度条之前等待指定的时间。用于防止条形闪烁。
    |duration|	Number|	5000|	进度条的最大显示时长，单位毫秒。Nuxt.js 假设页面在该时长内加载完毕。
    |continuous|	Boolean|	false	|当加载时间超过duration时，保持动画进度条。
    |css|	Boolean	|true|	设置为false以删除默认进度条样式（并添加自己的样式）。
    |rtl|	Boolean|	false|从右到左设置进度条的方向。


3. 自定义加载组件
  - 接口方法  
    | 方法	| 是否必须	| 描述 |
    | -- |  ---  |  ----  |
    | start()	| 是	| 路由更新（即浏览器地址变化）时调用, 请在该方法内显示组件。
    | finish()	| 是	| 路由更新完毕（即asyncData方法调用完成且页面加载完）时调用，请在该方法内隐藏组件。
    | fail()	| 否	| 路由更新失败时调用（如asyncData方法返回异常）。
    | increase(num)	| 否	| 页面加载过程中调用, num 是小于 100 的整数。