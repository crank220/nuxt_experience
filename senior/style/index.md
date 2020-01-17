## globe style

+  _css: ['~assets/css/reset.css']_

##  使用sass的mixin实现动态样式

+ __当前位置 ~assets/sass/resources.scss__

  ```css
  @mixin bg_img($path, $ext){
    @media screen and (max-device-width: 768px){
      background: url($path + '@1x.' + $ext);
    }
    @media screen and (min-device-width: 768px){
      background: url($path + '@2x.' + $ext);
    }
  }
  ```


## __postcss-pxtorem（将px自动转换成rem）__

```javascript
postcss: {
  plugins: {
　　'postcss-pxtorem':{
　　   rootValue: 40,
　　   propList: ['*']
　　 }
　},
　preset: {
　　 autoprefixer: true
　}
}
```
