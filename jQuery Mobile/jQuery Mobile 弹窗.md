# jQuery Mobile 弹窗

弹窗是一个非常流行的对话框，弹窗可以覆盖在页面上展示。

弹窗可用于显示一段文本，图片，地图或其他内容。

创建一个弹窗，需要使用 `<a>` 和 `<div>` 元素。在 `<a>` 元素上添加 `data-rel="popup"` 属性， `<div>` 元素添加 `data-role="popup"` 属性。 接着我们为 `<div>` 指定 `id`， 然后设置 `<a>` 的 `href` 值为 `<div>` 指定的 `id`。 `<div>` 中的内容为弹窗显示的内容。
注意: `<div>` 弹窗与点击的 `<a>` 链接必须在同一个页面上。

	<a href="#myPopup" data-rel="popup" class="ui-btn ui-btn-inline ui-corner-all">显示弹窗</a>
	
	<div data-role="popup" id="myPopup">
	  <p>这是一个简单的弹窗</p>
	</div>

如果你需要为弹窗添加内边距与外边距可以在 `<div>` 中添加 `"ui-content"` 类:

	<div data-role="popup" id="myPopup" class="ui-content">

### 关闭弹窗

默认情况下，点击弹窗之外的区域或按下 `"Esc"` 键即可关闭弹窗。 如果你不想点击弹窗之外的区域关闭弹窗可以在添加上添加 `data-dismissible="false"` 属性（不推荐）。 你也可以在弹窗上添加关闭按钮，按钮上使用 `data-rel="back"` 属性，并通过样式来控制按钮的位置。

### 定位弹窗

默认情况下，弹窗会直接显示在点击元素的上方，如果需要控制弹窗的位置，可以在用于打开弹窗的点击链接上使用 data-position-to 属性。

控制弹窗位置的三种方式：

- `data-position-to="window"` 弹窗在窗口居中显示
- `data-position-to="#myId"` 弹窗显示在知道的 #id 元素上
- `data-position-to="origin"` 默认。弹窗显示在点击的元素上。

### 过渡

默认情况下，弹窗是没有过渡效果的。如果你需要你可以通过 data-transition="value" 属性来添加过渡效果。

	<a href="#myPopup" data-rel="popup" class="ui-btn" data-transition="fade">Fade</a>

### 弹窗方向小边框

如果需要添加弹窗方向小边框，可以使用 data-arrow 属性，并指定值 "l" (左边), "t" (顶部), "r" (右边) or "b" (底部):

	<a href="#myPopup" data-rel="popup" class="ui-btn">打开弹窗</a>
	
	<div data-role="popup" id="myPopup" class="ui-content" data-arrow="l">
	  <p>左边框的方向。</p>
	</div>

### 弹窗对话框

你可以将弹窗制作为一个标准的对话框 (头部, 内容和底部标记):

	<a href="#myPopupDialog" data-rel="popup" class="ui-btn">打开对话框弹窗</a>
	
	<div data-role="popup" id="myPopupDialog">
	  <div data-role="header"><h1>头部文本..</h1></div>
	  <div data-role="main" class="ui-content"><p>一些文本..</p><a href="#">一些链接..</a>
	  <div data-role="footer"><h1>底部文本..</h1></div>
	</div>

### 图片弹窗

你可以在弹窗中显示图片:

	<a href="#myPopup" data-rel="popup" data-position-to="window">
	<img src="/wp-content/uploads/2015/10/runoob.jpeg" alt="Runoob" style="width:200px;"></a>
	
	<div data-role="popup" id="myPopup">
	  <img src="/wp-content/uploads/2015/10/runoob.jpeg" style="width:800px;height:400px;" alt="Runoob">
	</div>

### 弹窗背景覆盖

你可以使用 `data-overlay-theme` 属性在弹窗后添加背景颜色。

默认情况下覆盖的背景色的透明的。使用 `data-overlay-theme="a"` 添加浅色背景，使用 `data-overlay-theme="b"` 添加深色的覆盖背景：

	<a href="#myPopup" data-rel="popup">Show Popup</a>
	
	<div data-role="popup" id="myPopup" data-overlay-theme="b">
	  <p>在我身后有个深色背景。</p>
	</div>

一般图片弹窗经常使用背景覆盖：

	<a href="#myPopup" data-rel="popup" data-position-to="window">
	<img src="/wp-content/uploads/2015/10/runoob.jpeg" alt="Runoob" style="width:200px;"></a>
	
	<div data-role="popup" id="myPopup" data-overlay-theme="b">
	  <img src="/wp-content/uploads/2015/10/runoob.jpeg" style="width:800px;height:400px;" alt="Runoob">
	</div>

**注意： 在接下来的章节中，你将了解到如何在弹窗中使用表单。**