# jQuery Mobile 过渡

jQuery Mobile 包含 CSS3 效果让您选择页面打开的方式。

### jQuery Mobile 页面切换效果

jQuery Mobile 提供了各种页面切换到下一个页面的效果。

**注意：为了实现页面切换效果，浏览器必须支持 CSS3 3D 切换**

页面过渡效果可被应用于任何使用 data-transition 属性的链接或表单：

页面切换效果可被应用于任何使用 data-transition 属性的链接或表单提交：

	<a href="#anylink" data-transition="slide">切换到第二个页面</a>


下面显示了通过使用 data-transition 属性后可用的页面切换：

- fade 默认。淡入到下一页
- flip 从后向前翻转到下一页
- flow 抛出当前页，进入下一页
- pop 像弹出窗口那样转到下一页。
- slide 从右向左滑动到下一页。
- slidefade 从右向左滑动并淡入到下一页
- slideup 从下到上滑动到下一页。
- slidedown 从上到下滑动到下一页。
- turn 转向下一页
- none 无过渡效果。

>在 jQuery Mobile 的所有链接上，默认使用淡入淡出的效果（如果浏览器支持）。

**提示：上面的所有效果支持后退行为。例如，如果您想要页面从左向右滑动，而不是从右向左滑动，请使用带有 "reverse" 值的 data-direction 属性。在后退按钮上这是默认的。**

### 实例

	<a href="#pagetwo" data-transition="slide" data-direction="reverse">切换</a>




























