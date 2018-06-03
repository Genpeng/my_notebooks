# 《Think Python》第8章学习笔记

[TOC]

## 8.1 字符串是一个序列（A string is a sequence）

字符串是一个字符序列。可以使用中括号运算符 `[]` 一次从字符串中读取一个字符，中括号中的表达式称为索引（index），用于指示序列中你想要字符的位置。值得注意的是，**索引指的是从字符串起始位置开始的偏移（offset）**，因此第一字母的偏移为 0。

## 8.2 `len`

`len` 是 Python 中的内建函数，返回字符串中字符的数目。

```python
>>> fruit = 'banana'
>>> len(fruit)
6
```

对于字符串，Python 也提供了负向的索引，方便从字符串的末尾开始计数。

```python
>>> fruit = 'banana'
>>> last = fruit[-1]
>>> last
'a'
```

## 8.3 用一个 `for` 循环进行遍历（Traversal with a `for` loop）

在 Python 中，可以使用 `while` 语句和 `for` 循环对字符串进行遍历。

```python
# while statement
fruit = 'banana'
i = 0
while i < len(fruit):
    print(fruit[i])
    i = i + 1
    
# for loop
fruit = 'banana'
for letter in fruit:
    print(letter)
```

## 8.4 字符串切片（String slices）

字符串的一个片段（segment）称为一个切片（slice）。运算符 `[n:m]` 返回字符串从第 `n` 个字符到第 `m` 个字符的部分，但是只包括起始索引 `n`，不包括结束索引 `m`。

如果省略第一个索引，切片将从字符串的起始位置开始；如果省略第二个索引，切片将一直到字符串的结束位置。

```python
>>> fruit = 'banana'
>>> fruit[:3]
'ban'
>>> fruit[3:]
'ana'
```

如果第一索引的值大于等于第二个，那么结果将是空字符串（empty string）。

```python
>>> fruit = 'banana'
>>> fruit[3:3]
''
```

如果第一个索引和第二个索引都省略，那么将返回该字符串。

```python
>>> fruit = 'banana'
>>> fruit[:]
'banana'
```

## 8.5 字符串是不可变的（Strings are immutable）

**字符串是不可变的（immutable），意味着我们无法改变一个已经存在的字符串**。“改变”一个字符串的方式只能是从新生成一个字符串。

## 8.6 搜索（Searching）

无

## 8.7 循环和计数（Looping and counting）

无

## 8.8 字符串方法（String methods）

字符串类型（ `str` 类）提供了许多有用的方法，通过点运算符 `.` 进行调用，常用的方法有：

- `upper()` 和 `lower()`
- `find(...)`

## 8.9 `in` 运算符（The `in` operator）

`in` 运算符是一种布尔运算符，输入两个字符串，当第一个字符串是第二个字符串的字串时，返回 `True`。

```python
>>> 'a' in 'banana'
True
```

## 8.10 字符串比较（String comparison）

关系运算符（`>`、`<` 和 `==`）在字符串上也是起作用的。与 Java 中不同，Python 用 `==` 比较两个字符串是否相等。

```python
>>> 'abc' == 'banana'
False
>>> 'abc' == 'abc'
True
```

关系运算符（`>` 和 `<`）能够用于对字符串按照字母顺序进行排序。

```python
>>> 'abc' < 'banana'
True
>>> 'cat' > 'banana'
True
```

需要注意的是，在 Python 中，**所有的大写字母顺序都是排在小写字母前面的**。

```python
>>> 'Pipeapple' > 'banana'
False
```

因此，在进行字符串比较前，最好将所有的字符串转换成标准的格式，比如：小写。

## 8.11 调试（Debugging）

无