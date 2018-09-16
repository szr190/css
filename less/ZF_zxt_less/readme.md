# Less
## less的作用
- css层叠样式表,是标记语言,不是编程语言
- 所有的预编译语言(例如：less),都是赋予了css的面向对象思想

## 开发环境
- 在本地开发

## 生产环境
- 本地生产完成,我们需要把代码上传到服务器上,服务器上的环境叫做生产环境

## less的编译
- less叫做预编译css,写好的less代码浏览器是不能够渲染的,需要我们把它编译成能够渲染的css才行
- 在开发环境下,我们一般都通过导入less插件(less.js)来随时编译less代码
```css
    <link rel="stylesheet/less" href="less/1.less">
    <script src="https://cdn.bootcss.com/less.js/3.0.4/less.min.js"></script>
```
- 由于每一次加载页面都需要导入less.js并且把less文件重新编译为css,很消耗性能,页面打开速度可能会变慢,所以在真实项目中,只有在开发环境下才使用这种模式,在生产环境下,我们要把写好的less文件编译成css后再上线,以后用户访问的都是编译好的css,而不是拿less现编译

- 生产环境下,我们需要事先把less转换成css
    - Node编译
        - 下载less模块 cnpm i less --save-dev
        - lessc less/1.less css/1.css  编译less -> css
        - lessc less/1.less css/1.min.css -x 不仅编译成css,还压缩了
    - 使用编译工具
        - 考拉
        ......

## less中的变量
- 和Js中的变量一样,只是less的变量定义不是用var,而是用@

## less中的混合
## less作用域和命名空间
## less extend继承
```css
    .pub{
        width: 100px;
        height: 100px;
        background-color: green;
    }
    .box:extend(.pub){
        background-color: blue;
    }
```
## less条件
```css
    .pub(@x) when(@x<10){
        width: 100px;
        height: 100px;
    }
    .pub(@x) when(@x>10) and (@x<40){
        width: 400px;
        height: 200px;
    }
    .box{
        .pub(30);
        background-color: green;
    }
```