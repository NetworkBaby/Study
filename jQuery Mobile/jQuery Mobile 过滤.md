# jQuery Mobile 过滤

![jquery mobile] (./imgs/jquery mobile 5.jpg)

### 可过滤元素

所有的元素如果有一个或更多的子元素均可过滤。

如何创建搜索字段:

- 你想过滤的元素必须使用 `data-filter="true"` 属性。
- 创建 `<input>` 元素并指定 id，元素上加上 `data-type="search"` 属性。这样就能创建基本的搜索字段。将 `<input>` 元素放置于一个表单中，表单 `<form>` 元素使用 `"ui-filterable"` 类 - 该类会调整搜索字段与过滤元素的外边距。
- 接着为过滤的元素添加 `data-input` 属性。该值需要是 `<input>` 元素的 id。

接下来我们创建一个可过滤的列表：

	<form class="ui-filterable">
	  <input id="myFilter" data-type="search">
	</form>
	
	<ul data-role="listview" data-filter="true" data-input="#myFilter">
	  <li><a href="#">Adele</a></li>
	  <li><a href="#">Billy</a></li>
	  <li><a href="#">Calvin</a></li>
	</ul>

提示: 可以在搜索字段中使用 placeholder 属性来设置提示信息：

	<input id="myFilter" data-type="search" placeholder="根据名称搜索..">

### 自定义过滤

一般的插入到各个列表项的文本就是作为过滤的文本使用(如 `A` 对应 `"Adele"` 或 `"B"` 对应 `"Billy"`)。 但是，如果你想指定自定义的过滤的文本，你需要在子元素中使用 `data-filtertext` 属性:

	<li data-filtertext="fav"><a href="#">Adele</a></li>

> 如果你在元素中使用了 `data-filtertext` 属性，元素的源文本内容在过滤时将被忽略， 这时你如果还要查找列表项`"Adele"`，需要使用的关键字为：f, a, v 或 fav。