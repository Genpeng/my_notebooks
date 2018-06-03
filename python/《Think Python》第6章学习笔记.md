# 《Think Python》第6章学习笔记

> 备注：fruitful function 表示有返回值的函数，而不是翻译为丰富的函数。

[TOC]

## 6.1 返回函数值（Return values）

在 Python 中，**如果函数没有返回值，实际上，它们的返回值是 `None`**。

只要执行了 `return` 语句，函数就终止执行（不会再执行后续的语句）。在 `return` 语句后面的代码，或者是执行过程永远不会到达的地方，被称为无用代码（dead code）。

## 6.2 增量式开发（Incremental development）

增量式开发（incremental development）的目的就是避免过长的调试过程，一次只添加和测试少数的代码。

在程序开发过程中用到的、但最终不是程序的一部分的代码称为脚手架（scaffolding）。

## 6.3 组合（Composition）

无

## 6.4 布尔函数（Boolean functions）

无

## 6.5 更多的递归（More recursion）

无

## 6.6 信仰之跃（Leap of faith）

无

## 6.7 另一个例子（One more example）

无

## 6.8 检查类型（Checking types）

在 Python 中，内建（built-in）函数 `isinstance(...)` 可以判断对象的类型。

```python
>>> isinstance(5, int)
True
```

## 6.9 调试（Debugging）

把一个大的程序分解成小的函数有利于进行调试。