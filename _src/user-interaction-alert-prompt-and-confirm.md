> 译者: 朱志国

## 用户交互：警告、提示和确认。
* alert
* prompt
* confirm
* 总结
### 用户的UI操作可以分为alert，prompt和confirm。

## alrert（警告）

* 语法： arert（message）
* alert输出窗口的消息并停止执行，直到用户按"OK"按钮。
* 对话框的窗口有两种类型：模态窗口和非模态窗口。这里对话框的窗口是模态窗口。"模态"这个词意味着页面接口将被暂停，知道用户点击确认"OK".用户不能做任何事情。

```
alert("Test me");
```
运行上面的这句代码，浏览器会弹出一个模态窗口，如下图。
![0_1454032954403_QQ图片20160129100224.png](/uploads/files/1454032956037-qq图片20160129100224.png) 

## prompt(提示)
该函数接受两个参数的提示：
```
result = prompt(text[，default])；
```
* 他输出的模式窗口text，确认OK或者取消按纽和输入字段。
prompt返回一个字符串（可能是空的）或null。

* 返回的结果取决于用户的行动。有三个选项：
1. 如果用户输入信息并按OK，那么用户文本是结果。
默认100如下图。
![0_1454035432935_QQ图片20160129104114.png](/uploads/files/1454035434927-qq图片20160129104114.png) 

![0_1454035515082_QQ图片20160129104456.png](/uploads/files/1454035516626-qq图片20160129104456.png) 
2. 如果用户没有输入信息，按OK，那么结果就是default。
![0_1454035546172_QQ图片20160129104149.png](/uploads/files/1454035547614-qq图片20160129104149.png) 
3. 如果用户按下取消，结果就是null。
![0_1454035568814_QQ图片20160129104210.png](/uploads/files/1454035570281-qq图片20160129104210.png) 
```
var years = prompt('How old are you?',100)
alert('You are ' + years = 'years old!')
```
* 和alert模态窗口，用户可以不用做任何事情，直到用户用鼠标点击两个按钮之一。

* 设置第二个参数的时候
设置默认值prompt;否则输入"undefined"为对话框：
可以在IE浏览器试试：
```
prompt("test")
```

## confirm(确认)
* 语法：
```
result = confirm（message）
```
confirm输出message有两个按钮：确认或者取消。
返回的结果是true/false。
![0_1454035600178_QQ图片20160129104241.png](/uploads/files/1454035601602-qq图片20160129104241.png) 
![0_1454035611565_QQ图片20160129104257.png](/uploads/files/1454035613033-qq图片20160129104257.png)

```
var result = confirm（"should I say hello？"）
alert（result）
```
需要注意的是，用户不能装饰或者改变屏幕位置的模态窗口。这个就是UI功能的主要缺点。

但是这些功能有很简单，不需要额外的代码，这就是为什么人们仍然使用它们。

#
# 总结
* alrert输出一条消息。
* prompt提示输出信息，并等待用户输入，如果按下ESC键返回值或空值。
* confirm输出一条消息并等待，直到用户按下确认或者取消，返回结果是true/false。