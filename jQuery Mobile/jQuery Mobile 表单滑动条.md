# jQuery Mobile 表单滑动条

### jQuery Mobile 滑动条控件

滑动条允许您从一个范围的数字中选择一个值：

如需创建滑动条，请使用 `<input type="range">`：

	<form method="post" action="demoform.php">
	  <label for="points">进度:</label>
	  <input type="range" name="points" id="points" value="50" min="0" max="100">
	</form>

使用以下属性来规定限制：

- max - 规定允许的最大值
- min - 规定允许的最小值
- step - 规定合法的数字间隔
- value - 规定默认值

**提示**: 如果你想在按钮中显示进度的值可以添加 data-show-value="true" 属性:

	<input type="range" data-show-value="true">

**提示**：如果您想要高亮突出显示滑动条的值，请添加 `data-highlight="true"`：

	<input type="range" data-hightlight="true">

**提示**: 如果你想在滑动按钮上显示进度（类似一个小弹窗）可以使用 data-popup-enabled="true" 属性:

	<input type="range" data-popup-enabled="true">

### 拨动开关

波动开关通常用于 `on/off` 或 `true/false` 按钮：

我们可以使用 `<input type="checkbox">` 元素并指定 `data-role 为 "flipswitch"` 来创建开关:

	<form method="post" action="demoform.php">
	  <label for="switch">切换开关：</label>
	    <input type="checkbox" data-role="flipswitch" name="switch" id="switch">
	</form>

默认情况下，开关切换的文本为 `"On"` 和 `"Off"`。你可以使用 `data-on-text` 和 `data-off-text` 属性来修改它：

	<input type="checkbox" data-role="flipswitch" name="switch" id="switch" data-on-text="True" data-off-text="False">

**提示**:开关复选框可以使用 "checked" 属性来设置默认的选项：

	<input type="checkbox" data-role="flipswitch" name="switch" id="switch" checked>































