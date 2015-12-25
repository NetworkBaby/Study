# jQuery Mobile 表格

### 响应式表格

响应式设计一般用于适配用户各种移动设备。

我们只需要使用一个简单的类名，jQuery Mobile 就能根据屏幕的尺寸自动调整页面内容。

响应式表格让页面内容在移动端和桌面设备上能够很好的适配。

响应式表格有两种类型： `reflow`(回流) 与 列切换。

### 回流表格

回流模型表格在屏幕尺寸足够大时是水平显示，而在屏幕尺寸达到足够小时，所有的数据会变成垂直显示。

创建表格，在 `<table>` 元素上添加 `data-role="table"` 和 `"ui-responsive"` 类:

	<table data-role="table" class="ui-responsive">

>对于响应式表格，你必须包含 <thead> 和 <tbody> 元素。
>
>不要使用 rowspan 或 colspan 属性; 响应式表格中是不支持这两个属性的。

### 列切换

列切换模型会在宽度不够时隐藏数据。

列切换的表格创建方式如下：

	<table data-role="table" data-mode="columntoggle" class="ui-responsive" id="myTable">

默认情况下，jQuery Mobile 会先隐藏表格右侧的列。但是，你可以在表格头部(`<th>`)通过添加 `data-priority` 属性指定隐藏列的顺序，`data-priority` 的值可以是 1 (最高优先级) 到 6 (最低优先级):

	<th>I will never be hidden</th>
	<th data-priority="1">我是非常重要的列 - 我不会被隐藏</th>
	<th data-priority="3">我是重要的列 - 我可能被隐藏</th>
	<th data-priority="5"我是不怎么重要的列 - 我最先被隐藏</th>

> 如果你没未列指定优先级，则列会一直存在，不会被隐藏。

把上面的两段代码组合起来即可创建一个列切换的表格，这样用户就可以自定义要隐藏表格的哪些列：

	<table data-role="table" data-mode="columntoggle" class="ui-responsive" id="myTable">
	  <thead>
	    <tr>
	      <th data-priority="6">CustomerID</th>
	      <th>CustomerName</th>
	      <th data-priority="1">ContactName</th>
	      <th data-priority="2">Address</th>
	      <th data-priority="3">City</th>
	      <th data-priority="4">PostalCode</th>
	      <th data-priority="5">Country</th>
	    </tr>
	  </thead>
	  <tbody>
	    <tr>
	      <td>1</td>
	      <td>Alfreds Futterkiste</td>
	      <td>Maria Anders</td>
	      <td>Obere Str. 57</td>
	      <td>Berlin</td>
	      <td>12209</td>
	      <td>Germany</td>
	    </tr>
	  </tbody>
	</table>

我们可以使用 `data-column-btn-text` 属性来修改切换表格的文本：

	<table data-role="table" data-mode="columntoggle" class="ui-responsive" data-column-btn-text="点我显示或隐藏列!" id="myTable">

### 表格样式

我们使用 `"ui-shadow"` 类来为表格添加阴影：

	<table data-role="table" data-mode="columntoggle" class="ui-responsive ui-shadow" id="myTable">

使用 CSS 来进一步设置表格样式:

为所有行添加底部边框:

	<style>
	tr {
	    border-bottom: 1px solid #d6d6d6;
	}
	</style>


为 `<th>` 元素添加按钮及为偶数行添加背景:

	<style>
	th {
	    border-bottom: 1px solid #d6d6d6;
	}
	
	tr:nth-child(even) {
	    background: #e9e9e9;
	}
	</style>







