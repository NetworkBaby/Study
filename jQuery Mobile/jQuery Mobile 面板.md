# jQuery Mobile 面板

jQuery Mobile 中的面板会在屏幕的左侧向右侧划出。

通过向指定 id 的 `<div>` 元素添加 `data-role="panel"` 属性来创建面板。

在 `<div>` 中添加 HTML 标记来显示你的面板内容：

	<div data-role="panel" id="myPanel">
	  <h2>面板标题..</h2>
	  <p>文本内容..</p>
	</div>

**注意： panel 标记必须置于头部、内容、底部组成的页面之前或之后。
要访问面板，需要创建一个指向面板 `<div> id` 的链接，点击该链接即可打开面板:**

	<a href="#myPanel" class="ui-btn ui-btn-inline">打开面板</a>

简单的面板实例

	<div data-role="page" id="pageone">
	  <div data-role="panel" id="myPanel"> 
	    <h2>面板头部..</h2>
	    <p>面板内容..</p>
	  </div> 
	
	  <div data-role="header">
	    <h1>标准页面头部</h1>
	  </div>
	
	  <div data-role="main" class="ui-content">
	    <p>点击下面按钮打开面板。</p>
	    <a href="#myPanel" class="ui-btn ui-btn-inline">打开面板</a>
	  </div>
	
	  <div data-role="footer">
	    <h1>底部文本</h1>
	  </div> 
	</div>

### 关闭面板

你可以通过点击面板外部区域或按下 Esc 键或滑动来关闭面板。你可以通过使用 data-* 属性来禁用滑动和点击来关闭面板：

- data-dismissible true|false 指定面板是否可以通过点击面板外部区域来关闭。
- data-swipe-close true|false 指定是否可以通过滑动来关闭。

你可以使用按钮来关闭面板：仅需要在面板的 `<div>` 中添加 `data-rel="close"` 属性。 从性能上考虑，我们需要键关闭链接的 `href` 属性指向页面的 ID 。

	<div data-role="panel" id="myPanel"> 
	  <h2>面板头部..</h2>
	  <p>面板中的一些文本内容..</p>
	  <a href="#pageone" data-rel="close" class="ui-btn ui-btn-inline">关闭面板</a>
	</div> 

### 面板展示

你可以通过使用 data-display 属性来控制面板的展示方式:

- data-display="overlay" 在内容上显示面板
- data-display="push" 是同时"推动"面板和页面。
- data-display="reveal" 默认值，将页面像幻灯片一样从屏幕划出，将面板显示出来

	<div data-role="panel" id="overlayPanel" data-display="overlay">
	<div data-role="panel" id="revealPanel" data-display="reveal">
	<div data-role="panel" id="pushPanel" data-display="push"> 

### 面板定位

默认情况下，面板会显示在屏幕的左侧。如果想让面板出现在屏幕的右侧，可以指定 `data-position="right"` 属性。

	<div data-role="panel" id="myPanel" data-position="right"> 

你可以指定面板的内容根据页面滚动而滚动。默认情况下面板是随着页面一起滚动的（但是面板的内容仍然位于页面顶部）。如果你需要实现面板内容固定不随页面滚动而滚动，可以在面板添加 `data-position-fixed="true"` 属性:

	<div data-role="panel" id="myPanel" data-position-fixed="true"> 

