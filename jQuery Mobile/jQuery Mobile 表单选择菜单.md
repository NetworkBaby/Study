# jQuery Mobile 表单选择菜单

### jQuery Mobile 选择菜单

`<select>` 元素创建带有若干选项的下拉列表。

`<select>` 元素内的 `<option>` 元素定义了列表中的可用选项：

	<form method="post" action="demoform.html">
		<fieldset class="ui-field-contain">
			<label for="day">Select Day</label>
			<select name="day" id="day">
				<option value="mon">Monday</option>
				<option value="tue">Tuesday</option>
				<option value="wed">Wednesday</option>
			</select>
		</fieldset>
	</form>

**提示**：如果您有一个带有相关选项的很长的列表，请在 `<select>` 内使用 `<optgroup>` 元素：

	<select name="day" id="day">
		<optgroup label="Weekdays">
			<option value="mon">Monday</option>
			<option value="tue">Tuesday</option>
			<option value="wed">Wednesday</option>
		</optgroup>
		<optgroup label="Weekends">
			<option value="sat">Saturday</option>
			<option value="sun">Sunday</option>
		</optgroup>
	</select>

### 自定义选择菜单

本页顶部的图像，演示了移动平台上如何使用它们的方式展示一个选择菜单。

如果您想要让选择菜单在所有的移动设备上都显示相同，请使用 jQuery 自带的自定义选择菜单，`data-native-menu="false"` 属性：

	<select name="day" id="day" data-native-menu="false">

### 多个选择

如需在选择菜单中选择多个选项，请在 `<select>` 元素中使用 `multiple` 属性：

	<select name="day" id="day" multiple data-native-menu="false">






































