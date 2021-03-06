> 译者: 宇卿

正则表达式中有一些有特殊用法的字符：`[ \ ^ $ . | ? * + ( )`.

这些字符之所以特殊，是因为它们常被用来增强正则表达式查找的能力。不用刻意去记这些特殊字符，我们之后讲的内容会涉及到这些字符的具体用法，到那时再去记忆会变得非常容易。

如果你要匹配一般的字符中恰好涉及到这些特殊字符，那这些字符就必须被转义。或者，换句话说，要在起始位置附上反斜杠。

比如说，我们要匹配 `.` 这个字符。由于在正则表达式中它表示除了换行外的任意字符。

我们可以使用转义去匹配：

```
showMatch( "Chapter 5.1 ", /\d\.\d/)
```
这里如果不加转义，`\d.\d` 也会匹配到 `5 + 1`：

```
showMatch( "5+1 = 6", /\d.\d/ )  // 5+1
```

圆括号也是特殊字符，因此要匹配一个左圆括号，必须使用 `\(`. 下面的这个例子会匹配会匹配任意字符后接着一个左括号：

```
showMatch( "function g()", /\w\(/ )  // g(

```

斜杠 `/` 并非正则表达式中的特殊字符，但是在使用双斜杠表示的正则表达式中，例如：`/...pattern.../` 中如果需要匹反斜杠，那应该使用转义：`\/`，这样 javascript 语法解析器就知道你是想匹配 `'/'`, 而非正则表达式的结束。

看下面这个例子：

```
showMatch( "/", /\//) // '/'
```