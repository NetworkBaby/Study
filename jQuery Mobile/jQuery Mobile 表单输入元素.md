# jQuery Mobile 表单输入元素

### jQuery Mobile 文本输入框

输入字段是通过标准的 HTML 元素编码的，jQuery Mobile 将为它们添加样式使其看起来更具吸引力，在移动设备上更易使用。您也能使用新的 HTML5 的 `<input>` 类型：

	<form method="post" action="demo_form.php">
		<div class="ui-field-contain">
			<label for="fullname">全名:</label>
			<input type="text" name="fullname" id="fullname">
			
			<label for="bday">生日:</label>
			<input type="date" name="bday" id="bday">
			
			<label for="email">E-mail:</label>
			<input type="email" name="email" id="email" placeholder="你的电子邮箱..">
		</div>
	</form>

**提示：请使用 placeholder 来指定一个简短的描述，用来描述输入字段的期望值：**

	<input placeholder="sometext">

### 文本域

对于多行文本输入可使用 `<textarea>` 。

注意：当您键入一些文本时，文本域会自动调整大小以适应新增加的行。

	<form method="post" action="demo_form.php">
		<div class="ui-field-contain">
		<label for="info">附加信息:</label>
		<textarea name="addinfo" id="info"></textarea>
		</div>
	</form>

### 搜索输入框

`type="search"` 类型的输入框是在 HTML5 中新增的，它是为输入搜索定义文本字段：

	<form method="post" action="demo_form.php">
		<div class="ui-field-contain">
			<label for="search">搜索:</label>
			<input type="search" name="search" id="search">
		</div>
	</form>

### 单选按钮

当用户在有限数量的选择中仅选取一个选项时，使用单选按钮。

为了创建一系列单选按钮，请添加带有 `type="radio"` 的 `input` 以及相应的 `label`。把单选按钮包围在 `<fieldset>` 元素内。您也可以添加一个 `<legend>` 元素来定义 `<fieldset>` 的标题。

提示：请使用 `data-role="controlgroup"` 来把按钮组合在一起：

	<form method="post" action="demo_form.php">
		<fieldset data-role="controlgroup">
			<legend>Choose your gender:</legend>
			<label for="male">Male</label>
			<input type="radio" name="gender" id="male" value="male">
			<label for="female">Female</label>
			<input type="radio" name="gender" id="female" value="female"> 
		</fieldset>
	</form>

### 复选框

当用户在有限数量的选择中选取一个或多个选项时，使用复选框：

	<form method="post" action="demo_form.php">
		<fieldset data-role="controlgroup">
			<legend>Choose as many favorite colors as you'd like:</legend>
			<label for="red">Red</label>
			<input type="checkbox" name="favcolor" id="red" value="red">
			<label for="green">Green</label>
			<input type="checkbox" name="favcolor" id="green" value="green">
			<label for="blue">Blue</label>
			<input type="checkbox" name="favcolor" id="blue" value="blue"> 
		</fieldset>
	</form>

### 更多实例

如需水平组合单选按钮或复选框，请使用 `data-type="horizontal"`：

	<fieldset data-role="controlgroup" data-type="horizontal">

您也可以用一个 field 容器包围 `<fieldset>`：

	<div class="ui-field-contain">
		<fieldset data-role="controlgroup">
			<legend>请选择您的性别:</legend>
		</fieldset>
	</div>

如果您想要您的按钮中的一个预先选中，请使用 HTML 中 `<input>` 的 `checked` 属性：

	<input type="radio" checked>
	<input type="checkbox" checked>

你可以将表单放在弹窗中：

	<a href="#myPopup" data-rel="popup" class="ui-btn ui-btn-inline">Show Popup Form</a>
	
	<div data-role="popup" id="myPopup" class="ui-content">
	  <form method="post" action="demoform.php">
	    <div>
	      <h3>登录信息</h3>
	      <label for="usrnm" class="ui-hidden-accessible">用户名:</label>
	      <input type="text" name="user" id="usrnm" placeholder="用户名">
	      <label for="pswd" class="ui-hidden-accessible">密码:</label>
	      <input type="password" name="passw" id="pswd" placeholder="密码">
	    </div>
	  </form>
	</div> 












