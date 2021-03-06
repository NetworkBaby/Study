# jQuery Mobile 方向改变事件

jQuery Mobile 方向改变`（orientationchange）`事件

当用户垂直或水平旋转移动设备时，触发方向改变`（orientationchange）`事件。

如需使用方向改变`（orientationchange）`事件，请附加它到 `window` 对象：

	$(window).on("orientationchange",function(){
		alert("方向有改变!");
	});

回调函数可有一个参数，`event` 对象，返回移动设备的方向："纵向"（设备保持在垂直位置）或"横向"（设备保持在水平位置）：

	$(window).on("orientationchange",function(event){
		alert("方向是: " + event.orientation);
	});

由于方向改变`（orientationchange）`事件绑定到 `window` 对象，我们可以使用 `window.orientation` 属性来设置不同的样式，以便区分纵向和横向的视图：

	$(window).on("orientationchange",function() {
		if(window.orientation == 0) { // Portrait
			$("p").css({"background-color":"yellow","font-size":"300%"});
		}else { // Landscape
			$("p").css({"background-color":"pink","font-size":"200%"});
		}
	});

> `window.orientation` 属性针对纵向视图返回 0，针对横向视图返回 90 或 -90。





