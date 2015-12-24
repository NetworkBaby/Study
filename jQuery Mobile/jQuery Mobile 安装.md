# jQuery Mobile 安装

### 在你的网页中添加 jQuery Mobile

你可以通过以下几种方式将jQuery Mobile添加到你的网页中：
- 从 CDN 中加载 jQuery Mobile (推荐)
- 从jQuerymobile.com 下载 jQuery Mobile库

### 从 CDN 中加载 jQuery Mobile

> CDN的全称是Content Delivery Network，即内容分发网络。其基本思路是尽可能避开互联网上有可能影响数据传输速度和稳定性的瓶颈和环节，使内容传输的更快、更稳定。

使用 jQuery 内核, 你不需要在电脑上安装任何东西; 你仅仅需要在你的网页中加载以下层叠样式 (.css) 和 JavaScript 库 (.js) 就能够使用 jQuery Mobile:

	jQuery Mobile CDN:

	<head>
	
	<!-- meta使用viewport以确保页面可自由缩放 -->
	<meta name="viewport" content="width=device-width, initial-scale=1">
	
	<!-- 引入 jQuery Mobile 样式 -->
	<link rel="stylesheet" href="http://code.jquery.com/mobile/1.4.5/jquery.mobile-1.4.5.min.css">
	
	<!-- 引入 jQuery 库 -->
	<script src="http://code.jquery.com/jquery-1.11.3.min.js"></script>
	
	<!-- 引入 jQuery Mobile 库 -->
	<script src="http://code.jquery.com/mobile/1.4.5/jquery.mobile-1.4.5.min.js"></script>
	
	</head>

国内用户推荐使用百度CDN：

	<head>

	<!-- meta使用viewport以确保页面可自由缩放 -->
	<meta name="viewport" content="width=device-width, initial-scale=1">
	
	<!-- 引入 jQuery Mobile 样式 -->
	<link rel="stylesheet" href="http://apps.bdimg.com/libs/jquerymobile/1.4.5/jquery.mobile-1.4.5.min.css">
	
	<!-- 引入 jQuery 库 -->
	<script src="http://apps.bdimg.com/libs/jquery/1.10.2/jquery.min.js"></script>
	
	<!-- 引入 jQuery Mobile 库 -->
	<script src="http://apps.bdimg.com/libs/jquery/1.10.2/jquery.min.js"></script>
	
	</head>

### 下载 jQuery Mobile

如果你想将 jQuery Mobile 放于你的主机中,你可以从[jQuerymobile.com](http://jquerymobile.com/download/)下载该文件。

	<head>
	<meta name="viewport" content="width=device-width, initial-scale=1">
	<link rel="stylesheet" href="jquery.mobile-1.4.5.css">
	<script src="jquery.js"></script>
	<script src="jquery.mobile-1.4.5.js"></script>
	</head>