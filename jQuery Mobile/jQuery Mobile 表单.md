# jQuery Mobile 表单

jQuery Mobile 会自动为 HTML 表单自动添加样式，让它们看起来更具吸引力，触摸起来更具友好性。

![jquery mobile 6] (./imgs/jquery mobile 6.jpg)

### jQuery Mobile 表单结构

jQuery Mobile 使用 CSS 为 HTML 表单元素添加样式，让它们更具吸引力，更易于使用。

在 jQuery Mobile 中，您可以使用下列表单控件：

- 文本输入框
- 搜索输入框
- 单选按钮
- 复选框
- 选择菜单
- 滑动条
- 翻转拨动开关

当使用 jQuery Mobile 表单时，您应当知道：

- `<form>` 元素必须有一个 method 和一个 action 属性
- 每个表单元素必须有一个唯一的 "id" 属性。id 必须是整个站点所有页面上唯一的。这是因为 jQuery Mobile 的单页导航机制使得多个不同页面在同一时间被呈现
- 每个表单元素必须有一个标签。设置标签的 for 属性来匹配元素的 id

	<form method="post" action="demoform.html">
	<label for="fname">姓名:</label>
	<input type="text" name="fname" id="fname">
	</form>

如需隐藏标签，请使用 `class ui-hidden-accessible`。这在您把元素的 `placeholder` 属性作为标签时经常用到：

	<form method="post" action="demoform.html">
	<label for="fname" class="ui-hidden-accessible">姓名:</label>
	<input type="text" name="fname" id="fname" placeholder="姓名...">
	</form>

**提示**： 我们可以使用 `data-clear-btn="true"` 属性来添加清除输入框内容的按钮 (一个在输入框右侧的 X 图标):

	<label for="fname">姓名:</label>
	<input type="text" name="fname" id="fname" data-clear-btn="true"> 

> 清除输入框的按钮可以在 `<input>` 元素中使用，但不能在 `<textarea>` 中使用。 搜索框中 `data-clear-btn` 默认值为 `"true" `，你可以使用 `data-clear-btn="false"` 移除该图标。

### jQuery Mobile 表单图标

表单中的按钮代码是标准的 `HTML <input>` 元素 (`button`, `reset`, `submit`)。他们会自动渲染样式，可以自动适配移动设备与桌面设备：

	<input type="button" value="按钮">
	<input type="reset" value="重置按钮">
	<input type="submit" value="提交按钮"> 

如果需要在 `<input>` 按钮中添加额外的样式，可以使用下表中的 `data-*` 属性：

- data-corners true|false 指定按钮是否有圆角
- data-icon 指定按钮图标
- data-iconpos left|right|top|bottom|notext 指定图标位置
- data-inline true|false 指定是否内联按钮
- data-mini true|false 指定是否为迷你按钮
- data-shadow true|false 指定按钮是否添加阴影效果

### 字段容器

如需让标签和表单元素看起来更适应宽屏，请用带有 `"ui-field-contain"` 类的 `<div>` 或 `<fieldset>` 元素包围 `label/form` 元素：

> `ui-field-contain` 类基于页面的宽度为标签和表单控件添加样式。当页面的宽度大于 480px 时，它会自动把标签放置在与表单控件同一线上。当页面的宽度小于 480px 时，标签会被放置在表单元素的上面。

**提示：为了防止 jQuery Mobile 为可点击元素自动添加样式，请使用 data-role="none" 属性：**

	<label for="fname">姓名:</label>
	<input type="text" name="fname" id="fname" data-role="none">

>jQuery Mobile 中的表单提交
>
>jQuery Mobile 通过 AJAX 自动处理表单提交，并将试图集成服务器响应到应用程序的 DOM 中。


















