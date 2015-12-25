# jQuery Mobile 按钮

Mobile 应用程序是建立在您想要显示的简单的点击事物上。

### 在 jQuery Mobile 中创建按钮

在 jQuery Mobile 中，按钮可通过三种方式创建：

- 使用 `<button>` 元素
- 使用 `<input>` 元素
- 使用带有 `data-role="button"` 的 `<a>` 元素


	<button>按钮</button>

	<input type="button" value="按钮">
	
	<a href="#" data-role="button">按钮</a>

>在 jQuery Mobile 中，按钮会自动样式化，让它们在移动设备上更具吸引力和可用性。我们推荐您使用带有 `data-role="button"` 的 `<a>` 元素在页面间进行链接，使用 `<input>` 或 `<button>` 元素进行表单提交。

### 导航按钮
 
如需通过按钮在页面间进行链接，请使用带有 `data-role="button"` 属性的 <a> 元素：

	<a href="#pagetwo" data-role="button">访问第二个页面</a>

### 内联按钮

默认情况下，按钮占满整个屏幕宽度。如果你想要一个仅是与内容一样宽的按钮，或者如果您想要并排显示两个或多个按钮，请添加 `data-inline="true"`：

	<a href="#pagetwo" data-role="button" data-inline="true">访问第二个页面</a>

### 组合按钮

jQuery Mobile 提供了一个简单的方法来将按钮组合在一起。

请把 `data-role="controlgroup"` 属性和 `data-type="horizontal|vertical"` 一起使用来规定是否水平或垂直组合按钮：

	<div data-role="controlgroup" data-type="horizontal">
	<a href="#anylink" data-role="button">按钮 1</a>
	<a href="#anylink" data-role="button">按钮 2</a>
	<a href="#anylink" data-role="button">按钮 3</a>
	</div>
	
>默认情况下，组合按钮是垂直组合，它们之间没有外边距和空间。并且只有第一个和最后一个按钮是圆角，以便它们组合在一起的时候创建一个漂亮的外观。

### 后退按钮

如需创建后退按钮，请使用 data-rel="back" 属性（这会忽略锚的 `href` 值）：

	<a href="#" data-role="button" data-rel="back">返回</a>

### 更多链接按钮实例

- ui-btn-b 修改按钮颜色为黑色，字体为白色(默认为灰色背景，黑色字体)。
- ui-corner-all 为按钮添加圆角
- ui-mini 制作小按钮
- ui-shadow 为按钮添加阴影

>如果你需要使用更多的样式，每个样式类使用空格隔开，如： class="ui-btn ui-btn-inline ui-btn-corner-all ui-shadow"
>
>默认情况下 `<input>` 按钮有圆角及阴影效果。 `<a>` 和 `<button>` 元素没有。








