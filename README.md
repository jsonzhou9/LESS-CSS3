#LESS-CSS3#

一个基于less的常用css3预处理工具，以简化开发过程中为兼容不同浏览器而做的重复劳动，能有效的减少错误率，提高开发效率，当前版本为v0.1.0，欢迎大家扩充功能。

##使用##

在less中导入css3.less:

`@import "css3.less";`


##文件说明##

- css3.less 工具所在文件
- test.less 测试及示例
- test.css 测试编译文件

##方法列表##

###.backface-visibility(@visibility)###

####调用####

	.test-backface-visibility{
		.backface-visibility(visible);	
	}

####编译结果####

	.test-backface-visibility {
	  -webkit-backface-visibility: visible;
	  -moz-backface-visibility: visible;
	  backface-visibility: visible;
	}

###.background-gradient(@direction,@start,@end)###

- @direction 取值 [left|top|radial]，left：从左向右渐变；top：从上向下渐变；radial：径向渐变（圆形由内向外）
- 开始颜色
- 结束颜色

####调用####

	.test-background-gradient{
		.background-gradient(left,#ff0000,#000000);
	}

####编译结果####

	.test-background-gradient {
	  background: -webkit-gradient(linear, 0% 0%, 0% 100%, from(#ff0000), to(#000000));
	  background: -webkit-linear-gradient(top, #ff0000, #000000);
	  background: -moz-linear-gradient(top, #ff0000, #000000);
	  background: -o-linear-gradient(top, #ff0000, #000000);
	  background: -ms-linear-gradient(top, #ff0000, #000000);
	  background: linear-gradient(top, #ff0000, #000000);
	  background-color: #000000;
	}

###.border-radius(...)###

- 参数1-4个，参见css radius语法

####调用####

	.test-border-radius{
		.border-radius(5px);
	}

####编译结果####

	.test-border-radius {
	  -webkit-border-radius: 5px;
	  -moz-border-radius: 5px;
	  border-radius: 5px;
	}

###.box-shadow (@x,@y,@blur,@color,[@inset])###

- @x X轴偏移量
- @y Y轴偏移量
- @blur 阴影模糊半径
- @color 阴影颜色
- @inset，可选参数，传入 `inset` 时，为**内阴影**

####调用####

	.test-box-shadow-outer{
		.box-shadow(5px,10px,5px,#000000);
	}
	.test-box-shadow-inner{
		.box-shadow(5px,10px,5px,#000000,inset);
	}

####编译结果####

	.test-box-shadow-outer {
	  -webkit-box-shadow: 5px 10px 5px #000000;
	  -moz-box-shadow: 5px 10px 5px #000000;
	  box-shadow: 5px 10px 5px #000000;
	}
	.test-box-shadow-inner {
	  -webkit-box-shadow: inset 5px 10px 5px #000000;
	  -moz-box-shadow: inset 5px 10px 5px #000000;
	  box-shadow: inset 5px 10px 5px #000000;
	}

###.box-sizing(@style)###

- @style取值范围 [border-box | content-box | inherit]

####调用####

	.test-box-sizing{
		.box-sizing(border-box);
	}

####编译结果####

	.test-box-sizing {
	  -webkit-box-sizing: border-box;
	  -moz-box-sizing: border-box;
	  box-sizing: border-box;
	}

###.column-count(@num)###

- @num 数量

####调用####

	.test-column-count{
		.column-count(2);
	}

####编译结果####

	.test-column-count {
	  -webkit-column-count: 2;
	  -moz-column-count: 2;
	  -o-column-count: 2;
	  -ms-column-count: 2;
	  column-count: 2;
	}

###.column-gap(@gap)###

- @gap ，Gap Width (px)

####调用####

	.test-column-gap{
		.column-gap(25px);
	}

####编译结果####

	.test-column-gap {
	  -webkit-column-gap: 25px;
	  -moz-column-gap: 25px;
	  -o-column-gap: 25px;
	  -ms-column-gap: 25px;
	  column-gap: 25px;
	}

###.opacity(@opacity)###

- @opacity 取值[0-1]

####调用####

	.test-opacity{
		.opacity(0.5);
	}

####编译结果####

	.test-opacity {
	  filter: alpha(opacity=50);
	  opacity: 0.5;
	}

###.perspective(@size)###

- @size ，Perspective Size (px)

####调用####

	.test-perspective{
		.perspective(200px);
	}

####编译结果####

	.test-perspective {
	  -webkit-perspective: 200px;
	  -moz-perspective: 200px;
	  -o-perspective: 200px;
	  -ms-perspective: 200px;
	  perspective: 200px;
	}

###.perspective-origin (@x,@y)###

####调用####

	.test-perspective-origin{
		.perspective-origin(20%,50%);
	}

####编译结果####

	.test-perspective-origin {
	  -webkit-perspective-origin: 20%, 50%;
	  -moz-perspective-origin: 20%, 50%;
	  -o-perspective-origin: 20%, 50%;
	  -ms-perspective-origin: 20%, 50%;
	  perspective-origin: 20%, 50%;
	}

###.text-shadow (@x,@y,@blur,@color)###

- @x X轴偏移量
- @y Y轴偏移量
- @blur 阴影模糊半径
- @color 阴影颜色

####调用####

	.test-text-shadow{
		.text-shadow(5,10,5,#000000);
	}

####编译结果####

	.test-text-shadow {
	  text-shadow: 5 10 5 #000000;
	}

###.transform (...)###

- 任意参数

####调用####

	.test-transform{
		.transform(rotate(20deg));
	}

####编译结果####

	.test-transform {
	  -webkit-transform: rotate(20deg);
	  -moz-transform: rotate(20deg);
	  -o-transform: rotate(20deg);
	  -ms-transform: rotate(20deg);
	  transform: rotate(20deg);
	}

###.transform-perspective(@size)###

- @size，Perspective Size (px)

####调用####

	.test-transform-perspective{
		.transform-perspective(200px);
	}

####编译结果####

	.test-transform-perspective {
	  -webkit-transform: perspective(200px);
	  -moz-transform: perspective(200px);
	  -o-transform: perspective(200px);
	  -ms-transform: perspective(200px);
	  transform: perspective(200px);
	}

###.transform-rotate(@degrees)###

- @degrees，Degrees (deg)

####调用####

	.test-transform-rotate{
		.transform-rotate(20deg);
	}

####编译结果####

	.test-transform-rotate {
	  -webkit-transform: rotate(20deg);
	  -moz-transform: rotate(20deg);
	  -o-transform: rotate(20deg);
	  -ms-transform: rotate(20deg);
	  transform: rotate(20deg);
	}

###.transform-rotate3d (@x,@y,@z)###

####调用####

	.test-transform-rotate3d{
		.transform-rotate3d(0px,0px,0px);
	}

####编译结果####

	.test-transform-rotate3d {
	  -webkit-transform: rotateX(0px) rotateY(0px) rotateZ(0px);
	  -moz-transform: rotateX(0px) rotateY(0px) rotateZ(0px);
	  -o-transform: rotateX(0px) rotateY(0px) rotateZ(0px);
	  -ms-transform: rotateX(0px) rotateY(0px) rotateZ(0px);
	  transform: rotateX(0px) rotateY(0px) rotateZ(0px);
	}

###.transform-scale (@size)###

- @size，缩放比例

####调用####

	.test-transform-scale{
		.transform-scale(0.5);
	}

####编译结果####

	.test-transform-scale {
	  -webkit-transform: scale(0.5);
	  -moz-transform: scale(0.5);
	  -o-transform: scale(0.5);
	  -ms-transform: scale(0.5);
	  transform: scale(0.5);
	}

###.transform-scale3d(@x,@y,@z)###

####调用####

	.test-transform-scale3d{
		.transform-scale3d(1,1,1);
	}

####编译结果####

	.test-transform-scale3d {
	  -webkit-transform: scale3d(1, 1, 1);
	  -moz-transform: scale3d(1, 1, 1);
	  -o-transform: scale3d(1, 1, 1);
	  -ms-transform: scale3d(1, 1, 1);
	  transform: scale3d(1, 1, 1);
	}

###.transform-skew (@x,@y)###

倾斜角度

####调用####

	.test-transform-skew{
		.transform-skew(10deg,20deg);
	}

####编译结果####

	.test-transform-skew {
	  -webkit-transform: skew(10deg, 20deg);
	  -moz-transform: skew(10deg, 20deg);
	  -o-transform: skew(10deg, 20deg);
	  -ms-transform: skew(10deg, 20deg);
	  transform: skew(10deg, 20deg);
	}

###.transform-translate (@x,@y)###

位置偏移

####调用####

	.test-transform-translate{
		.transform-translate(10px,10px);
	}

####编译结果####

	.test-transform-translate {
	  -webkit-transform: translate(10px, 10px);
	  -moz-transform: translate(10px, 10px);
	  -o-transform: translate(10px, 10px);
	  -ms-transform: translate(10px, 10px);
	  transform: translate(10px, 10px);
	}

###.transform-translate3d(@x,@y,@z)###

3d位置偏移，会启用gpu加速

####调用####

	.test-transform-translate3d{
		.transform-translate3d(10px,10px,10px);
	}

####编译结果####

	.test-transform-translate3d {
	  -webkit-transform: translate3d(10px, 10px, 10px);
	  -moz-transform: translate3d(10px, 10px, 10px);
	  -o-transform: translate3d(10px, 10px, 10px);
	  -ms-transform: translate3d(10px, 10px, 10px);
	  transform: translate3d(10px, 10px, 10px);
	}

###.transform-origin (@x,@y)###

####调用####

	.test-transform-origin {
		.transform-origin(50%,50%);
	}

####编译结果####

	.test-transform-origin {
	  -webkit-transform-origin: 50% 50%;
	  -moz-transform-origin: 50% 50%;
	  -o-transform-origin: 50% 50%;
	  -ms-transform-origin: 50% 50%;
	  transform-origin: 50% 50%;
	}

###.transform-style (@style)###

- @style取值[flat | preserve-3d]

####调用####

	.test-transform-style {
		.transform-style(flat);
	}

####编译结果####

	.test-transform-style {
	  -webkit-transform-style: flat;
	  -moz-transform-style: flat;
	  -o-transform-style: flat;
	  -ms-transform-style: flat;
	  transform-style: flat;
	}

###.transition(...)###

- 任意合法参数

####调用####

	test-transition{
		.transition(all 0.5s ease);
	}

####编译结果####

	.test-transition {
	  -webkit-transition: all 0.5s ease;
	  -moz-transition: all 0.5s ease;
	  -o-transition: all 0.5s ease;
	  transition: all 0.5s ease;
	}

##其它##
- 项目主页：http://www.tuijs.com
- 作者博客：http://www.2fz1.com