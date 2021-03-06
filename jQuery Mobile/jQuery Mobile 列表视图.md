# jQuery Mobile 列表视图

![jquery mobile] (./imgs/jquery mobile 3.jpg)

### jQuery Mobile 列表视图

jQuery Mobile 中的列表视图是标准的HTML 列表; 有序(`<ol>`) 和 无序(`<ul>`).

列表视图是jQuery Mobile中功能强大的一个特性。它会使标准的无序或有序列表应用更广泛。应用方法就是在`ul`或`ol`标签中添加`data-role="listview"`属性。在每个项目(`<li>`)中添加链接，用户可以点击它：

	<ol data-role="listview">
	  <li><a href="#">列表项m</a></li>
	</ol>
	
	<ul data-role="listview">
	  <li><a href="#">列表项</a></li>
	</ul>

列表样式的圆角和边缘，使用 data-inset="true" 属性设置:

	<ul data-role="listview" data-inset="true">

> 默认情况下，列表项的链接会自动变成一个按钮 (不需要 `data-role="button"`)。

### 列表分隔

列表项也可以转化为列表分割项，用来组织列表，使列表项成组。

指定列表分割，给列表项`<li>`元素添加 `data-role="list-divider"` 属性即可：

	<ul data-role="listview">
	 <li data-role="list-divider">欧洲</li>
	  <li><a href="#">法国</a></li>
	  <li><a href="#">德国</a></li>
	</ul>

如果你有一个字母顺序排列的列表，（例如一个电话簿）通过 `<ol>` 或者`<ul>` 元素的 `data-autodividers="true"` 属性设置可以配置为自动生成的项目的分隔:

	<ul data-role="listview" data-autodividers="true">
	  <li><a href="#">Adele</a></li>
	  <li><a href="#">Agnes</a></li>
	  <li><a href="#">Billy</a></li>
	  <li><a href="#">Calvin</a></li>
	  ...
	</ul>

> `data-autodividers="true"` 可以配置为自动生成的项目的分隔。默认情况下，创建的分隔文本是列表项文本的第一个大写字母。