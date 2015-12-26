# jQuery Mobile 列表内容

### jQuery Mobile 列表图标

默认情况下每个列表项都会包含一个箭头图标 `"carat-r"` (右箭头)。如果要修改这个图标可以使用 `data-icon` 属性:

	<ul data-role="listview"> 
	  <li><a href="#">Default is right arrow</a></li>
	  <li data-icon="plus"><a href="#">data-icon="plus"</a></li>
	  <li data-icon="minus"><a href="#">data-icon="minus"</a></li>
	  <li data-icon="delete"><a href="#">data-icon="delete"</a></li>
	  <li data-icon="location"><a href="#">data-icon="location"</a></li> 
	  <li data-icon="false"><a href="#">data-icon="false"</a></li>
	</ul>

> `data-icon="false"` 将会移除图标。

### 16x16 图标

如果你想在你的列表添加标准的 16x16px 的图标, 可以在列表项中添加 `<img>` 元素，并使用 `"ui-li-icon"` 类:

	<ul data-role="listview">
	  <li><a href="#"><img src="us.png" alt="USA" class="ui-li-icon">USA</a></li>
	</ul>

### jQuery Mobile 列表缩略图

大于 16x16px 的图像，请在链接中添加 `<img>` 元素。

jQuery Mobile 将自动缩放图像到 80x80px:

	<ul data-role="listview">
	  <li><a href="#"><img src="chrome.png"></a></li>
	</ul>

使用标准的HTML添加列表信息：

	<ul data-role="listview">
	  <li>
	    <a href="#">
	    <img src="chrome.png">
	    <h2>Google Chrome</h2>
	    <p>Google Chrome 免费的开源 web 浏览器。发布于 2008 年。</p>
	    </a>
	  </li>
	</ul>

### jQuery Mobile 列表图标

在列表 `<img>` 元素使用 `class="ui-li-icon"` 添加 16x16px 图标：

	<li><a href="#"><img src="us.png" alt="USA" class="ui-li-icon">USA</a></li>

### 分割按钮

在JQuery Mobile的列表中，有时需要对选项内容做两个不同的操作，这时，需要对选项中的链接按钮进行分割。实现分割的方法是在`<li>`元素中再增加一个`<a>`元素，便可以在页面实现分割效果。

jQuery Mobile 会自动设置第二个链接为蓝色箭头的图标，图标的链接文字（如果有的话）将在用户将鼠标悬停在 图标时显示:

	<ul data-role="listview">
	  <li>
	    <a href="#"><img src="chrome.png"></a>
	    <a href="#">Some Text</a>
	  </li>
	</ul>

添加一些页面和对话框使链接功能更加丰富：

	<ul data-role="listview">
	  <li>
	    <a href="#"><img src="chrome.png"></a>
	    <a href="#download" data-rel="dialog">下载浏览器</a>
	  </li>
	</ul>

### 气泡数字

气泡数字是用来显示列表项相关的数字，如在一个邮箱的邮件：

![jquery mobile] (./imgs/jquery mobile 4.jpg)

如需添加气泡数字，请使用行内元素，比如 `<span>`，设置 `class "ui-li-count"` 属性并添加数字：

	<ul data-role="listview">
	  <li><a href="#">收件箱<span class="ui-li-count">25</span></a></li>
	  <li><a href="#">发件箱<span class="ui-li-count">432</span></a></li>
	  <li><a href="#">垃圾箱<span class="ui-li-count">7</span></a></li>
	</ul>

**注意：显示一个正确的气泡数字，必须修改编程方式。 这将在以后的章节解释。**