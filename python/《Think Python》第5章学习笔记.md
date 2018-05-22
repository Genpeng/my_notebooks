# 《Think Python》第5章学习笔记

> 备忘：**parameter 指的是形参，argument 指的是实参。**

[TOC]

## 5.1 整除和取模（Floor division and modulus）
在 Python 3 中，`/` 符号对两个操作数做的是浮点除法（floating-point division），而 `//` 符号对两个操作数做的是整除（floor division）。在 Python 2 中，则有所不同。当两个操作数都是整数时，`/` 符号做的是整除；只要两个操作数中有一个是浮点数时，`/` 符号做的是浮点除法。

## 5.2 布尔表达式（Boolean expressions）
无

## 5.3 逻辑运算符（Logical operators）
在 Python 中，有三种逻辑运算符（logical operator）：`and`、`or` 以及 `not`。

有一点值得注意，在 Python 中，**逻辑运算符的操作数并不需要是布尔表达式（boolean expression），任意非零的数都相当于布尔值 `True`**。

## 5.4 条件执行（Conditional execution）
当条件语句下面的执行语句暂时还未确定时，可以将 `pass` 语句作为占位符——暂时充当执行语句，即：
```python
if x < 0:
    pass  # TODO: need to handle negative values!
```

## 5.5 选择执行（Alternative execution）
无

## 5.6 链式条件（Chained conditionals）
无

## 5.7 嵌套条件（Nested conditionals）
在 Python 中，对于 `0 < x and x < 10` 这样的表达式，可以更加简洁地写成：`0 < x < 10`。

## 5.8 递归（Recursion）
函数调用自身的执行过程称为递归（recursion）。

## 5.9 递归函数的堆栈图（Stack diagrams for recursive functions）

无

## 5.10 无穷的递归（Infinite recursion）

无

## 5.11 键盘输入（Keyboard input）

Python 为我们提供了一个内建函数 `input` 用于从控制台输入，当执行 `input` 函数时，暂停程序的运行，等待用户输入，当用户输入完毕后（按下 Enter 或者 Return），程序继续执行，`input` 函数会将用户输入的字符作为一个字符串。

```python
>>> text = input()
What are you waiting for?
>>> text
'What are you waiting for?'
```

`input` 函数还可以将一个提示的字符串作为参数，提示用户应该输入什么。

```python
>>> name = input('What...is your name?\n')
What...is your name?
Arthur, King of the Britons!
>>> name
'Arthur, King of the Britons!'
```

## 5.12 调试（Debugging）

当语法或者运行错误（syntax or runtime error）发生时，错误提示中包含大量信息，但是错误提示经常是冗长的，包含许多不必要的部分。对于我们而言，其中最有用的部分应该是：

- 错误类型
- 错误发生的行数

值得注意的是，**错误提示虽然指出了错误发生的行数，但是实际中，错误发生的地方可能在前面**（比如前一行）。