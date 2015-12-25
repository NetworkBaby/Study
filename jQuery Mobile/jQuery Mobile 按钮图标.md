# jQuery Mobile 按钮图标

jQuery Mobile 提供了一套让按钮看起来更称心如意的图标。

### 添加图标到 jQuery Mobile 按钮

我们可以使用 ui-icon 类将图标添加到按钮上，并可以使用指定类来设置按钮位置。

	<a href="#anylink" class="ui-btn ui-icon-search ui-btn-icon-left">Search</a>

**注意**： 在其他方式的按钮上，如列表或表单中的按钮需要使用 data-icon 属性。在接下来的章节中我们会具体介绍。

下面我们列出一些 jQuery Mobile 提供的可用图标：

- ui-icon-arrow-l 左箭头
- ui-icon-arrow-r 右箭头
- ui-icon-info 信息
- ui-icon-delete 删除
- ui-icon-back 后退
- ui-icon-audio 扬声器
- ui-icon-lock 挂锁
- ui-icon-search 搜索
- ui-icon-alert 警告
- ui-icon-grid 网格
- ui-icon-home 主页

### 定位图标

您也可以规定图标定位在按钮的什么部位：顶部（top）、右侧（right）、底部（bottom）、左侧（left）。

请使用 ui-btn-icon 属性来指定位置：

	<a href="#anylink" class="ui-btn ui-icon-search ui-btn-icon-top">顶部</a>
	<a href="#anylink" class="ui-btn ui-icon-search ui-btn-icon-right">右侧</a>
	<a href="#anylink" class="ui-btn ui-icon-search ui-btn-icon-bottom">底部</a>
	<a href="#anylink" class="ui-btn ui-icon-search ui-btn-icon-left">左侧</a>

>如果你未指定按钮图片的位置，图标将不显示。

### 只显示图标

如果你只想显示图标，可以使用 "notext":

	<a href="#anylink" class="ui-btn ui-icon-search ui-btn-icon-notext">搜索</a>

### 移除圆圈

默认情况下，所有的图标都有一个灰色的圆圈。如果你不需要它，可以在元素中使用 "ui-nodisc-icon" 类：

	<a href="#anylink" class="ui-btn ui-icon-search ui-btn-icon-left">使用圆圈 (默认)</a>
	<a href="#anylink" class="ui-btn ui-icon-search ui-btn-icon-left ui-nodisc-icon">去掉圆圈</a>

### 黑色、白色按钮

默认情况下，所有图标都是白色的。 如果需要改变图标颜色为黑色，可以在元素添加 "ui-alt-icon"：

	<a href="#anylink" class="ui-btn ui-icon-search ui-btn-icon-left">白色</a>
	<a href="#anylink" class="ui-btn ui-icon-search ui-btn-icon-left ui-alt-icon">黑色</a>

