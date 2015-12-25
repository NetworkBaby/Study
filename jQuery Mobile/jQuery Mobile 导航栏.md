# jQuery Mobile 导航栏

导航栏是由一组水平排列的链接组成，通常包含在头部或尾部内。

![jquery mobile] (./imgs/jquery mobile 2.jpg)

默认情况下，导航栏中的链接将自动变成按钮（不需要 `data-role="button"`）。

使用 `data-role="navbar"` 属性来定义导航栏：

	<div data-role="header">
	<div data-role="navbar">
	<ul>
	<li><a href="#anylink">首页</a></li>
	<li><a href="#anylink">页面二</a></li>
	<li><a href="#anylink">搜索</a></li>
	</ul>
	</div>
	</div>

>默认情况下，按钮的宽度与它的内容一样。使用一个无序列表来平均地划分按钮的宽度：1 个按钮占 100% 宽度，2 个按钮则各占 50% 的宽度，3 个按钮则每个占 33,3% 的宽度，依此类推。然而，如果您在导航栏中指定了超过 5 个按钮，将会拆成多行（查看"更多实例"）。

### 导航按钮图标

我们可以使用 data-icon 属性为导航按钮添加图标:

	<a href="#anylink" data-icon="search">搜索</a>

`data-icon` 属性与在图标章节中的 CSS 类使用相同的值。CSS 类使用方法 `class="ui-icon-value"`, `data-icon` 属性使用方法 `data-icon="value"`。

### 定位图标

就像 `"ui-btn-icon-position"` 类一样 (图标章节有详细说明), 你可以设置图标显示的位置： top（头部）, right（右侧）, bottom（底部） 或 left（左侧）。

图标位置在导航栏容器上设置，使用 `data-iconpos` 属性来指定位置：

- data-iconpos="top" 图标顶部对齐
- data-iconpos="right" 图标右侧对齐
- data-iconpos="bottom" 图标底部对齐
- data-iconpos="left" 图标左侧对齐

> 默认情况， 导航按钮的图标位于文本之上 (`data-iconpos="top"`)。

### 激活按钮

当导航栏中的某个链接被点击，它将获得被选中（按下）的外观。

如果想在不点击链接时获得这种外观，请使用 `class="ui-btn-active"`：

	<li><a href="#anylink" class="ui-btn-active">首页</a></li>

对于多个页面，您可能想要每个按钮的选中外观代表当前用户所在的页面。要做到这一点，请添加 "ui-state-persist" 和 "ui-btn-active" 到链接的 class：

	<li><a href="#anylink" class="ui-btn-active ui-state-persist">首页</a></li>

































