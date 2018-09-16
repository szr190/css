## Sass
### 1、变量与导入
    变量 - 注意sass中的变量是以$开头的,这与less还是有很大不同的
		1.局部变量
		2.全局变量
			只要在局部变量后面加一个!global就可以了
		3.变量默认值
			!default 会先找默认值的项,再去找其它的,不会进行覆盖
		4.多值变量
			(1)nth($,n) -n的索引下标是以1开始的
			(2)$map(key:value,key:value) 在获取的时候要用map-get($,key)
		5.变量的特殊用法
			(1)把变量放在属性或者选择器上 #{}
			(2)_ -在scss中是一样的

	样式导入
		1.部分文件 - 只为导入或引入去做的,不会进行css编译,避免重复在文件前面加_就是一个部分文件了
### 2、继承与嵌套
    嵌套
		1.选择器嵌套
		2.属性嵌套
		3.&引用父选择器
		4.@at-root跳出嵌套

	继承 - @extend
		1.单继承
		2.多继承
		3.链式继承
		4.交叉继承 - 使用的时候应该避免这种做法,会造成不可预计的后果
### 3、片段及运算
    数据类型
		Number
		String
		List
		Map
		Color
		Boolean
		Null

	运算
		== != 
		< > <= >= 
		+ - * / %

		注意：
			-运算的时候最好用空格隔开
			-单位需要保持一致

	mixin
		用@include引用片段
### 4、函数与调试
    函数
		1.内置函数
			rgb()
			rgba()
			//颜色变浅或加深
			lighten()
			darken()

			str-length
			str-index
		2.自定义函数

			@function

	调试
		@debug
		@warn
		@error
### 5、条件控制
    @if
	@for - 区分through和to
	@while - 可以设置间隔
	@each