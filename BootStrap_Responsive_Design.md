#BootStrap响应式设计#

##屏幕像素分类##

* xs:extra small 特别窄的屏幕，默认浏览器像素<768px;
* sm:small 窄屏幕，默认浏览器像素>=768px;
* md:middle 中等宽屏幕，默认浏览器像素>=992px;
* lg:large 大屏幕，默认浏览器像素>=1200px; 

`!!牢记!!`

##媒体查询##
```
	@media (max-width:767px){...}

	@media (min-width:768px) and (max-width:991px){...}

	@media (min-width:992px) and (max-width:1199px){...}

	@media (min-width:1200px) {...}

```
##页面栅格化##

BootStrap将内容区域分成12份，按百分比分配。因此可以适应浏览器不同宽度（像素多少）。

栅格定义：class="col-`*`-[1-12]",`*`为xs,sm,md,lg

* col-xs-1~col-xs-12:`始终`在同一行内；
* col-sm-1~col-sm-12:在浏览器像素>=768px时在同一行内；
* col-md-1~col-md-12:在浏览器像素>=992px时在同一行内；
* col-lg-1~col-lg-12:在浏览器像素>=1200px时在同一行内；

`如果浏览器像素有变化，同一行内的内容不符合浏览器大小时会分行显示。`

优先级：根据浏览器像素，尽可能匹配适用的大宽度类。例如class="col-sm-1 col-md-5"，当>=992px,先匹配col-md-5。

##栅格偏移##

* offset:左边距  col-xs[sm,md,lg]-offset-0~col-xs[sm,md,lg]-offset-12
* pull:右偏移  col-xs[sm,md,lg]-pull-0~col-xs[sm,md,lg]-pull-12
* push:左偏移  col-xs[sm,md,lg]-push-0~col-xs[sm,md,lg]-push-12

##常见排版##

1. 单列页面：
```
	<div class="container">
		<div class="row">
			<div class="col-md-6 col-md-offset-3"> //这里col-md-6可以换成其他的
				//code

				<div class="row">
					//嵌套
					<div class="col-sm-6"></div>
					<div class="col-sm-6"></div>
				</div>
			</div>
		<div>
	</div>
```
2. 两列页面
```
	<div class="container">
		<div class="row">
			<div class="col-md-3"> //这里col-md-6可以换成其他的
				//code

				<div class="row">
					//嵌套
					<div class="col-sm-6"></div>
					<div class="col-sm-6"></div>
				</div>
			</div>
			<div class="col-md-9"> //这里col-md-6可以换成其他的
				//code
				<div class="row">
					//嵌套
					<div class="col-sm-6"></div>
					<div class="col-sm-6"></div>
				</div>
			</div>
		<div>
	</div>
```