### ASP.NET MVC - HTML 帮助器
HTML 帮助器用于修改 HTML 输出。

### HTML 帮助器
通过 MVC，HTML 帮助器类似于传统的 ASP.NET Web Form 控件。

就像 ASP.NET 中的 Web Form 控件，HTML 帮助器用于修改 HTML。但是 HTML 帮助器是更轻量级的。与 Web Form 控件不同，HTML 帮助器没有事件模型和视图状态。

在大多数情况下，HTML 帮助器仅仅是一个返回字符串的方法。

通过 MVC，您可以创建您自己的帮助器，或者直接使用内建的 HTML 帮助器。

### 标准的 HTML 帮助器
MVC 包含了大多数常用的 HTML 元素类型的标准帮助器，比如 HTML 链接和 HTML 表单元素。

### HTML 链接
呈现 HTML 链接的最简单的方法是使用 HTML.ActionLink() 帮助器。

通过 MVC，Html.ActionLink() 不连接到视图。它创建一个连接到控制器操作。

Razor 语法：
```
@Html.ActionLink("About this Website", "About")
```
ASP 语法：
```
<%=Html.ActionLink("About this Website", "About")%>
```
第一个参数是链接文本，第二个参数是控制器操作的名称。

上面的 Html.ActionLink() 帮助器，输出以下的 HTML：
```
<a href="/Home/About">About this Website</a>
```
Html.ActionLink() 帮助器的一些属性：
```
属性	描述
.linkText	URL 文本（标签），定位点元素的内部文本。
.actionName	操作（action）的名称。
.routeValues	传递给操作（action)的值，是一个包含路由参数的对象。
.controllerName	控制器的名称。
.htmlAttributes	URL 的属性设置，是一个包含要为该元素设置的 HTML 特性的对象。
.protocol	URL 协议，如 "http" 或 "https"。
.hostname	URL 的主机名。
.fragment	URL 片段名称（定位点名称）。
```
注释：您可以向控制器操作传递值。例如，您可以向数据库 Edit 操作传递数据库记录的 id：

Razor 语法 C#：
```
@Html.ActionLink("Edit Record", "Edit", new {Id=3})
```
Razor 语法 VB：
```
@Html.ActionLink("Edit Record", "Edit", New With{.Id=3})
```
上面的 Html.ActionLink() 帮助器，输出以下的 HTML：
```
<a href="/Home/Edit/3">Edit Record</a>
```
HTML 表单元素
以下 HTML 帮助器可用于呈现（修改和输出）HTML 表单元素：
```
BeginForm()
EndForm()
TextArea()
TextBox()
CheckBox()
RadioButton()
ListBox()
DropDownList()
Hidden()
Password()
```
ASP.NET 语法 C#：
```html
<%= Html.ValidationSummary("Create was unsuccessful. Please correct the errors and try again.") %>
<% using (Html.BeginForm()){%>
<p>
<label for="FirstName">First Name:</label>
<%= Html.TextBox("FirstName") %>
<%= Html.ValidationMessage("FirstName", "*") %>
</p>
<p>
<label for="LastName">Last Name:</label>
<%= Html.TextBox("LastName") %>
<%= Html.ValidationMessage("LastName", "*") %>
</p>
<p>
<label for="Password">Password:</label>
<%= Html.Password("Password") %>
<%= Html.ValidationMessage("Password", "*") %>
</p>
<p>
<label for="Password">Confirm Password:</label>
<%= Html.Password("ConfirmPassword") %>
<%= Html.ValidationMessage("ConfirmPassword", "*") %>
</p>
<p>
<label for="Profile">Profile:</label>
<%= Html.TextArea("Profile", new {cols=60, rows=10})%>
</p>
<p>
<%= Html.CheckBox("ReceiveNewsletter") %>
<label for="ReceiveNewsletter" style="display:inline">Receive Newsletter?</label>
</p>
<p>
<input type="submit" value="Register" />
</p>
<%}%>
```