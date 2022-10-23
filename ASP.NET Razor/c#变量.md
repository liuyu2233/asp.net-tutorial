### ASP.NET Razor - C# 变量
变量是用来存储数据的命名实体。

### 变量
变量是用来存储数据的。

一个变量的名称必须以字母字符开头，并且不能包含空格或者保留字符。

一个变量可以是一个指定的类型，表示它所存储的数据类型。string 变量存储字符串值（"Welcome to RUNOOB.COM"），integer 变量存储数字值（103），date 变量存储日期值，等等。

变量使用 var 关键字声明，或通过使用类型（如果您想声明类型）声明，但是 ASP.NET 通常能自动确定数据类型。

实例
```c#
// Using the var keyword:
var greeting = "Welcome to RUNOOB.COM";
var counter = 103;
var today = DateTime.Today;

// Using data types:
string greeting = "Welcome to RUNOOB.COM";
int counter = 103;
DateTime today = DateTime.Today;
```

### 数据类型
下面列出了常用的数据类型：

| 类型 | 描述 | 实例 |
| ---- | ---- | ---- |
| int | 整数（全数字） | 103, 12, 5168 |
| float | 浮点数 | 3.14, 3.4e38 |
| decimal | 十进制数字（高精度） | 1037.196543 |
| bool | 布尔值 | true, false |
| string | 字符串 | Hello RUNOOB.COM, "John" |


### 运算符
运算符告诉 ASP.NET 在表达式中执行什么样的命令。

C# 语言支持多种运算符。下面列出了常用的运算符：

略...

### 转换数据类型
从一种数据类型转换到另一种数据类型，有时候是很有用的。

最常见的例子是将字符串输入转换为另一种类型，如整数或者日期。

一般规则下，都是将用户输入看做字符串处理，即使用户输入了数字。因此数值输入必须被转换成数字，然后才能将其用于计算。

下面列出了常用的转换方法：

| 方法 | 描述 | 实例 |	
| ---- | ---- | ---- |	
| AsInt()<br>IsInt() | 转换字符串为整数。 | if (myString.IsInt())<br>{myInt=myString.AsInt();} |	
| AsFloat()<br>IsFloat() | 转换字符串为浮点数。 | if (myString.IsFloat())<br>{myFloat=myString.AsFloat();} |	
| AsDecimal()<br>IsDecimal() | 转换字符串为十进制数。 | if (myString.IsDecimal())<br>{myDec=myString.AsDecimal();} |	
| AsDateTime()<br>IsDateTime() | 转换字符串为 ASP.NET DateTime 类型。 | myString="10/10/2012";<br>myDate=myString.AsDateTime(); |	
| AsBool()<br>IsBool() | 转换字符串为布尔值。 | myString="True";<br>myBool=myString.AsBool(); |	
| ToString() | 转换任何数据类型为字符串。 | myInt=1234;<br>myString=myInt.ToString(); |	
