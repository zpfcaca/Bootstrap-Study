#Bootstrap

##简介
  由Twitter开发的前端框架。它基于HTML，CSS，JavaScript，自带13个jQuery插件。

##参考网站
官网：            www.getbootstrap.com   
Bootstrap中文网： http://www.bootcss.com   
github: https://github.com/twbs/bootstrap

##组件
1. CSS12栅格系统：把网页的宽度分成12份；
2. 基础布局组件：
3. jQuery
4. 响应式设计
5. CSS组件
6. JavaScript插件
###CSS
  下拉菜单：
  按钮    ： btn
  按钮下拉菜单：
  导航    ： 
  导航条  ：
  面包屑导航：
  分页导航 ：
  标签与徽章：
  排版   ：
  缩略图 ：
  警告   ：alert
  进度条 ：
  媒体对象：
  其他   ： 

##常用插件



##学习要点
###版本模板
	<!DOCTYPE html>
	<html lang="en">
	<head>
	<meta charset="utf-8">
	<meta http-equiv="X-UA-Compatilbe" content="IE=edge">
	<!--默认情况了UI布局的宽度与移动设备的宽度一致-->
	<meta name="viewport" content="width=device-width,initial-scale=1">
	<!--上面3个“meta”必须在最开始位置-->
	<title>Bootstrap模板</title>
	<!--Bootstrap-->
	<link href="css/bootstrap.min.css" rel="stylesheet">

	<!-- HTML5 shim and Respond.js for IE8 support of HTML5 elements and media queries -->
    <!-- WARNING: Respond.js doesn't work if you view the page via file:// -->
    <!--[if lt IE 9]>
      <script src="https://oss.maxcdn.com/html5shiv/3.7.2/html5shiv.min.js"></script>
      <script src="https://oss.maxcdn.com/respond/1.4.2/respond.min.js"></script>
    <![endif]-->

	</head>
	<body>
		<h1>Hello, world!</h1>
   		<!-- jQuery (necessary for Bootstrap's JavaScript plugins) -->
    	<script src="https://ajax.googleapis.com/ajax/libs/jquery/1.11.3/jquery.min.js"></script>
    	<!-- Include all compiled plugins (below), or include individual files as needed -->
    	<script src="js/bootstrap.min.js"></script>
	</body>
	</html>  

###媒体查询
@media (attr:value){ }   

###JS立即执行函数:声明一个函数后立即执行
* (function(){/*code*/}());
* (function(){/*code*/})();
* (function(){/*code*/})(auguments);  

Bootstrap中定义函数：
	+function($){
	/*code*/
	}(jQuery);
	/*这里$为局部变量，参数为jQuery*/
	/*"+"和分号功能一样，防止前置代码不符合规范*/  

###事件绑定
jQuery事件绑定：on和off
	$("td").on("click",function(event){code});
	$("td").off("click");
Bootstrap事件绑定:
	$(document).on("click.bs.carousel.data-api","td",function(e){});
	$(document).off(".carousel.data-api");
	或
	$(“#id”).on("click.bs.carousel.data-api",,function(e){});

###$.data
以data-开头的自定义属性
$(selector).data(“xxx”):设置或获取形如“data-xxx:value”。
$(selector).data():获取所有形如“data-*:value”。

	<dive data-role="student">
	<script type="text/javascript">
		$("div").data("role") /*得到student*/
	</script>  

###12栅格系统
* 按行定义，列作为行的子元素；
* 支持嵌套；
* 必须包含在.container中；
* 样式：col-xs-*(超小),col-sm-*（小）,col-md-*(中)，col-lg-*(大)。
* 跨设备：组合多种样式一起使用   
* 某些情况下为了解决排列问题需要使用清除样式：clearfix visible-*(这里*指定某些内容，例如visible-xs)   


###Bootstrap的CSS设计思想

CSS的设计思想：AO模式。A-Append（附加）；O-Overwrite(重写)。同名的样式，后面的样式覆盖前面的样式。

Bootstrap的CSS架构：   
>1.基础样式（元素的缩写，例如按钮：btn，alert）
>>2.颜色样式（五种：primary（重点蓝），success（成功绿），info（信息蓝），warning（警告橙），danger（危险红），基础样式-primary,......）
>>>3.尺寸样式(超小（xs），小型（sm），普通，大型（lg），*-xs，...)
>>>>4.状态样式（active，disable）
>>>>>5.特殊元素样式（特定类型的组件，如警告框alert,导航nav。）
>>>>>>6.并列元素样式（子元素之间的间距问题）
>>>>>>>7.嵌套子元素样式(-group)
>>>>>>>>8.动画样式(一般用于进度条progress,在上面俯加active即可)。 

###JavaScript插件规则
* 基于自定义属性的HTML布局：自定义属性data-**，这里的**表示某些动作，如toggle（触发）；
* 遵循jQuery插件开发标准；

###实用
1. 居中：.container 样式
2. 响应式表格：在.table外包装.table-responsive
3. 表单form:表单内的元素filedset,legend,label
4. .form-control样式：input,select和textarea的宽度为100%。
5. btn系类样式支持a元素，input元素，button元素；
6. 图片img风格：.img-rounded,.img-circle,.img-thumbnail,不控制图片大小，需要额外的样式或限制父元素大小。
7. 向下箭头：.caret
8. 下拉菜单：.dropdown(父，必须相对定位)，.dropdown-menu(子，绝对定位)。分割符：.divider。多级嵌套：.dropdown-submenu.
9. 按钮：按钮组.btn-group，按钮工具栏.btn-toolbar
10. 按钮下拉菜单：.dropdown-toggle和属性data-toogle="dropdown"。
11. Addon:input和文字huoicon一起使用。.input-group-addon,.input-group-btn(按钮)
12. 导航：Bootstrap不提供默认导航。.nav 必须和其他一起使用，如.nav-tabs（选项卡导航），.nav-pills(胶囊式)，.nav-stacked(堆叠式)
13. 导航条：在ul元素上使用.nav .navbar-nav,再在其父元素上使用.navbar .navbar-default.
14. 导航条中的元素：navbar-form（表单），navbar-btn(按钮)，navbar-text(文本)，navbar-link(普通链接)。
15. 面包屑导航：一般用于当前页所在的位置，.breadcrumb。
16. 分页导航：页码分页--.pagination,支持状态（active，disabled），大小；翻页--.pager
17. 标签：.label 高亮显示。
18. 徽章：.badge  交互式系统或信息系统显示一些消息数目。一般配合<span>或<label>使用。
19. 大屏展播：.jumbotron。
20. 缩略图：.thumbnails  结合12个栅格系统使用。其内可以包括图片<img>和标题.caption类
21. 警告框：.alert。可以带一个关闭按钮，在按钮属性里添加data-dismiss="alert",
如<button type="button" class="close" data-dismiss="alert">&times;</button>
22. 进度条：.progress(进度条样式)和.progress-bar(进度条进度)。可以配置颜色，条纹。   
23. 媒体对象：图片、视频、音频的组合。
		嵌套表示：.media->.pull-right(.pull-left)->.media-object(媒体对象内容)+.media-body->.media-heading。
```

 	<div class="media">
		<a class="pull-left" href="#">
			<img class="media-object" src=... />
		</a>
		<div class="media-body">
			<h4 class="media-heading">media heading</h4>
			<!-- 嵌套的media对象-->
			<div class="media"> </div>
		</div>
 	</div>   
```
24. 媒体列表：```<ul class="media-list"><li class="media"></li></ul>```   
25. 列表组：.list-group和.list-group-item。定义颜色：.list-group-item-success(danger...)
26. 自定义列表组：在列表组中加入.list-group-item-heading(头部)和.list-group-item-text（内容）。
27. 面板：基础面板.panel;控制主体颜色.panel-default（primary...）;面板内容.panel-body。可以和表格，列表组一起使用。
28. 洼地：.well
29. 主题：对9种组件进行增强显示：btn,thumbnail,dropdown menu,navbar,alert,progress,list-group,panel,well
30. 模态窗口：modal,绝对定位。3层div容器，依次为.modal,.modal-dialog,.modal-content。.modal-content中包含.modal-header,
.modal-baody,.modal-footer。触发:按钮或<a>或其他，自定属性data-toggle="modal",data-target="自定义的class类名或者是'#id'"，相应的modal中设置“自定义的class类名或者是id”。这里最好使用id。

###Bootstrap.js
所有的插件可以通过HMTL声明式和JS来操作   
1. 动画过渡：.fade   
2. 模态窗口：$(selector).modal("show/hide/toggle"),属性设置$(selector).modal({backdrop:true/false,...}).   
4种事件：show.bs.modal,shown.bs.modal,hide.bs.modal,hidden.bs.modal,绑定$(selector).on('show.bs.modal',function(e){}); 
3. 下拉菜单：$(selector).dropdown()。对事件第一次单击注册：$(selector).one('click',function(){$(this).dropdown('toggle')})。4种事件：show.bs.dropdown,shown.bs.dropdown,hide.bs.dropdown,hidden.bs.dropdown    
4. 滚动侦测：设置滚动容器（监测），菜单容器（滚动的内容），菜单内必须有.nav,li,a组合。JS：$('滚动容器').scrollspy({target：'#菜单容器'});   
5. 选项卡tab：选项卡导航和选项卡面板同时有。在导航的选项内设置data-toggle="tab",并且设置data-target="选择符"
或href="选择符"。选项卡面板父元素.tab-content,子元素与导航对应，含有.tab-pane,并且id=“选择符”： 
```	

	<ul class="nav nav-tabs">
		<li><a href="#home" data-toggle="tab">Home</a></li>
		<li><a href="#profile" data-toggle="tab">Profile</a></li>
	</ul>
	<div class="tab-content">
		<div class="tab-pane" id="home">...</div>
		<div class="tab-pane" id="profile">...</div>
	</div>
	JS形式:
	$(function(){
		$(".nav a").click(function(){
			$(this).tab('show');
		});
	}); 
```	  

6. 提示框Tooltip：声明法data-toggle="tooltip"，data-oringinal-title="提示内容" 或title("提示内容")， 
				JS：$(selector).tooltip(option)。使用之前需要激活（`必须`）：$(function () { $("[data-toggle='tooltip']").tooltip(); });  默认提示框向上弹出，data-placement="left":改变提示框位置
				默认事件hover,focus
	例子：

7. 弹出框popover:自定义属性data-toggle="popover",data-origin-title="...",data-content="..." 同提示框,默认click

8. 警告框：.alert alert-warning fade in;关闭按钮.close ,data-dismiss="alert"  

9. 按钮：data-toggle="button"。input元素使用data-toggle="buttons"。按钮的自定义属性，这是data-toggle被data-**-text=""
替代。
```
	<button type="button" id="btn1" class="btn btn-default" data-loading-text="正在加载...">获取内容</button>
	//触发代码
	$(function(){
		$("#btn1").click(function(){
			var btn=$(this);
			btn.button('loading')
		});
	});
	//或者直接调用
	$("#btn1").button("loading");   
```  
10. 折叠collapse:一个触发按钮data-toggle="collapse",data-target="#id"。折叠区域.collapse in。实现手风琴效果，必须为
触发按钮加上data-parent="#parent id"。    

11. 轮播Carousel：   
```

	<div data-ride="carousel" class="carousel slide" id="carousel-container">
		<!--图片容器-->
		<div class="carousel-inner">
			<div class="item">
				<img alt="第一张" src=""/>
				<div class="carousel-caption">
					<h3>...</h3>
					<p>.....</p>
				</div>
			<div>
			<div class="item">
				<img alt="第二张" src=""/>
				<div class="carousel-caption">
					<h3>...</h3>
					<p>.....</p>
				</div>
			<div>
		</div>
		<!--指示符-->
		<ol class="carousel-indicators">
			<li data-slide-to="0" data-target="#carousel-container"></li>
			<li data-slide-to="1" data-target="#carousel-container"></li>
		</ol>
		<!--左右控制-->
		<a data-slide="prev" href="#carousel-container" class="left carousel-control">
			<span class="glyphicon glyphicon-chervon-left"></span></a>
		<a data-slide="prev" href="#carousel-container" class="right carousel-control">
			<span class="glyphicon glyphicon-chervon-right"></span></a>
	</div>
```
12. Affix:data-spy="affix" 位置属性data-offset="100"或data-offset-top="100"和data-offset-bottom="100"















