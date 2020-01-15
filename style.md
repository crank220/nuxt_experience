# globe style

css: ['~assets/css/reset.css']

##  使用sass的mixin实现动态样式

当前位置 ~assets/sass/resources.scss

@mixin bg_img($path, $ext){
  @media screen and (max-device-width: 768px){
    background: url($path + '@1x.' + $ext);
  }
  @media screen and (min-device-width: 768px){
    background: url($path + '@2x.' + $ext);
  }
}


> postcss-pxtorem（将px自动转换成rem）
``
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
``
