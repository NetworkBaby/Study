# jQuery Mobile Data 属性

jQuery Mobile 使用 `HTML5 data-*` 属性来为移动设备创建更具触摸友好性和吸引性的外观。

### 按钮

在1.4 版本以后已废弃。使用 `CSS` 类 替代。带有 `data-role="button"` 的超链接。`button` 元素、工具栏中的链接以及 `input` 字段都会自动渲染成按钮样式，不需要添加 `data-role="button"`。

![Data-属性] (./imgs/data-attribute1.png)

> 如需组合多个按钮，请使用带有 `data-role="controlgroup"` 属性和 `data-type="horizontal|vertical"` 的容器来规定是否水平或垂直组合按钮。

### 复选框

带有 `type="checkbox"` 的成双成对的 `label` 和 `input`。它们会被自动渲染程按钮样式，`data-role`不是必需的。

![Data-属性] (./imgs/data-attribute2.png)

> 如需组合多个复选框，请使用带有 `data-role="controlgroup"` 属性和 `data-type="horizontal|vertical"` 的容器来规定是否水平或垂直组合复选框。

### 可折叠块

在带有 `data-role="collapsible"` 的容器内部的后跟任意 `HTML` 标记的标题元素。

![Data-属性] (./imgs/data-attribute3.png)

### 可折叠集合

在带有 `data-role="collapsible-set"` 的容器内部的可折叠内容块。

![Data-属性] (./imgs/data-attribute4.png)

### 内容

 使用 `data-role="content"` 的容器。

![Data-属性] (./imgs/data-attribute5.png)

### 控件组

带有 `data-role="controlgroup"` 的 `<div>` 或 `<fieldset>` 容器。 组合单个类型（基于链接的按钮、单选按钮、复选框、`select` 元素）的多个按钮样式的 `input`。对于组合表单复选框和单选按钮，推荐在带有 `data-role="fieldcontain"` 的 `<div>` 内使用 `<fieldset>` 容器来改进标签样式。

![Data-属性] (./imgs/data-attribute6.png)

### 对话框

带有 `data-role="dialog"` 的容器或带有 `data-rel="dialog"` 的链接。

![Data-属性] (./imgs/data-attribute7.png)

### 增强

带有 `data-enhance="false"` 或 `data-ajax="false"` 的容器。

![Data-属性] (./imgs/data-attribute8.png)

**注意：`data-enhance="false"` 必须与 `$.mobile.ignoreContentEnabled=true"` 一同使用来阻止 jQuery Mobile 自动渲染页面。

当 `$.mobile.ignoreContentEnabled` 设置为 `true` 时，`data-ajax="false"` 容器内的任何链接或表单元素将会被框架的导航功能忽略。**

### 域容器

1.4 版本后已废弃，在 1.5 版本后不再支持，将使用 `class="ui-fieldcontain` 替代"。 包裹在 `label/form` 元素对，并带有 `data-role="fieldcontain"` 的容器。

### 固定工具栏

带有 `data-role="header"` 或 `data-role="footer"`，并带有 `data-position="fixed"` 属性的容器。

![Data-属性] (./imgs/data-attribute9.png)

### 翻转拨动开关

一个带有 `data-role="slider"` 的 `<select>` 元素和两个 `<option>` 元素。

![Data-属性] (./imgs/data-attribute10.png)

### 尾部栏

带有`data-role="footer"` 的容器

![Data-属性] (./imgs/data-attribute11.png)

**注意：如需启用全屏定位，请使用 `data-position="fixed"`，然后添加 `data-fullscreen` 属性到元素上。**

### 头部栏

带有 `data-role="header"` 的容器。

![Data-属性] (./imgs/data-attribute12.png)

**注意：如需启用全屏定位，请使用 `data-position="fixed"`，然后添加 `data-fullscreen` 属性到元素上。**

### 链接

所有的链接，包含那些带有 `data-role="button"` 的链接和表单提交按钮。

![Data-属性] (./imgs/data-attribute13.png)

### 列表

带有 `data-role="listview"` 的 `<ol>` 或 `<ul>`。

![Data-属性] (./imgs/data-attribute14.png)

### 列表项

带有 `data-role="listview"` 的 `<ol>` 或 `<ul>` 内的 `<li>`。

![Data-属性] (./imgs/data-attribute15.png)

**注意：data-icon 属性只作用于带有链接的列表项。**

### 导航栏

带有 `data-role="navbar"` 容器内部的 `<li>` 元素。

![Data-属性] (./imgs/data-attribute16.png)

> 导航栏从他们的父容器中继承了主题样本。为导航栏设置 `data-theme` 属性是不可能的。可以为导航栏中的每个链接单独设置 `data-theme` 属性。

### 页面

带有 `data-role="page"`的容器

![Data-属性] (./imgs/data-attribute17.png)

### 弹窗

带有 `data-role="popup"` 的容器。

![Data-属性] (./imgs/data-attribute18.png)

带有 `data-rel="popup"` 的锚：

![Data-属性] (./imgs/data-attribute19.png)

### 单选按钮

带有 `type="radio"` 的成双成对的 `label` 和 `input`。它们会被自动渲染程按钮样式，`data-role` 不是必需的。

![Data-属性] (./imgs/data-attribute20.png)

> 如需组合多个单选按钮，请使用带有 `data-role="controlgroup"` 属性和 `data-type="horizontal|vertical"` 的容器来规定是否水平或垂直组合单选按钮。

### 选择

所有的 `<select>` 元素。这些会被自动渲染成按钮样式，`date-role` 是不必需的。

![Data-属性] (./imgs/data-attribute21.png)

> 如需组合多个 `select` 元素，请使用带有 `data-role="controlgroup"` 属性和 `data-type="horizontal|vertical"` 的容器来规定是否水平或垂直组合 `select` 元素。

### 滑动块

带有 `type="range"` 的输入框。这些会被自动渲染成按钮样式，`date-role` 是不必需的。

![Data-属性] (./imgs/data-attribute22.png)

### 文本输入框 & 文本输入域

带有 `type="text|search|etc."` 的 `input` 或 `textarea` 元素。这些会被自动渲染成按钮样式，`date-role` 是不必需的。

![Data-属性] (./imgs/data-attribute23.png)






