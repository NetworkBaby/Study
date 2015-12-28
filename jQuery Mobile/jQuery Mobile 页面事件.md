# jQuery Mobile 页面事件

在 jQuery Mobile 中与页面打交道的事件被分为四类：

- Page Initialization - 在页面创建前，当页面创建时，以及在页面初始化之后

- Page Load/Unload - 当外部页面加载时、卸载时或遭遇失败时

- Page Transition - 在页面过渡之前和之后

- Page Change - 当页面被更改，或遭遇失败时

### jQuery Mobile Initialization 事件

当 jQuery Mobile 中的一张典型页面进行初始化时，它会经历三个阶段：

- 在页面创建前

- 页面创建

- 页面初始化

每个阶段触发的事件都可用于插入或操作代码。

![pageEvent img] (./imgs/pageEvent1.jpg)

下面的例子演示在 jQuery Mobile 中创建页面时，何时触发每种事件：

	$(document).on("pagebeforecreate",function(event){
	  alert("pagebeforecreate 事件触发!");
	}); 
	$(document).on("pagecreate",function(event){
	  alert("pagecreate 事件触发!");
	});
	
### jQuery Mobile Load 事件

页面加载事件属于外部页面。

无论外部页面何时载入 DOM，将触发两个事件。第一个是 `pagebeforeload`，第二个是 `pageload` （成功）或 `pageloadfailed`（失败）。

下表中解释了这些事件：

![pageEvent img] (./imgs/pageEvent2.jpg)

下列演示 `pageload` 和 `pagloadfailed` 事件的工作原理：

	$(document).on("pageload",function(event,data){
	  alert("触发 pageload 事件！\nURL: " + data.url);
	});
	$(document).on("pageloadfailed",function(event,data){
	  alert(";抱歉，被请求页面不存在。");
	});

### jQuery Mobile 过渡事件

我们还可以在从一页过渡到下一页时使用事件。

页面过渡涉及两个页面：一张"来"的页面和一张"去"的页面 - 这些过渡使当前活动页面（"来的"页面）到新页面（"去的"页面的改变过程变得更加动感。

![pageEvent img] (./imgs/pageEvent3.jpg)

下列演示了过渡时间的工作原理：

	$(document).on("pagebeforeshow","#pagetwo",function(){ //当进入页面二时 
	  alert("页面二即将显示");
	});
	$(document).on("pageshow","#pagetwo",function(){ // 当进入页面二时
	  alert("现在显示页面二");
	});
	$(document).on("pagebeforehide","#pagetwo",function(){ // 当进入页面二时
	  alert("页面二即将隐藏");
	});
	$(document).on("pagehide","#pagetwo",function(){ // When leaving pagetwo
	  alert("现在隐藏页面二");
	});
