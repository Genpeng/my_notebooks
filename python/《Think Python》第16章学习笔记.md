# 《Think Python》第16章学习笔记

[TOC]

## 16.1 Time

无

## 16.2 纯函数（Pure functions）

纯函数不会对传入的参数（实参）做任何修改。

## 16.3 修改器（Modifiers）

与纯函数相反，修改器将会修改作为参数的对象。

一般而言，**只要是合理的情况下，推荐使用纯函数**，只有修改器有令人信服的优势时才使用修改器。这样的编程方式可以称为**函数式编程风格（functional programming style）**。

## 16.4 原型 vs. 方案（Prototyping versus planning）

无

## 16.5 调试（Debugging）

某些必须为真的条件，比如某个变量的值必须大于 0，这样的要求称之为**不变式（invariants）**。

在函数的开头，你应该检查传入的参数（实参）以保证它们是有效的，如果是无效的，可以使用 `raise` 语句抛出异常：

```python
def valid_time(t):
    if t.second < 0 or t.minute < 0 or t.hour < 0:
        return False
    if t.second >= 60 or t.minute >= 60 or t.hour >= 24:
        return False
    return True

def add_time(t1, t2):
    if not valid_time(t1) or not valid_time(t2):
        raise ValueError("Invalid Time object!!!")
    seconds = time_to_int(t1) + time_to_int(t2)
    return int_to_time(seconds)
```

或者，**也可以使用 `assert` 语句来检查已知的不变式**，如果不变式的值为 `False`，则会抛出异常：

```python
def add_time(t1, t2):
	assert valid_time(t1) and valid_time(t2)
    seconds = time_to_int(t1) + time_to_int(t2)
    return int_to_time(seconds)
```

`assert` 语句非常有用，因为它区分了处理正常条件的代码和检查错误的代码。