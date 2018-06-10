# 《Think Python》第15章学习笔记

[TOC]

## 15.1 程序员定义的类型（Programmer-defined types）

定义一个类的过程会创建一个**类型对象（type object）**。比如，我们创建一个点（`Point`）类：

```python
>>> class Point:
...     """
...     Represents a point in 2-D spaces.
...     """
... 
>>> type(Point)
<class 'type'>
>>> Point
<class '__main__.Point'>
```

因为点（`Point`）类定义在最高层，因此，它的“全名”（full name）是 `__main__.Point`。

一个类型对象（type object）就像一个“生产”对象的工厂，调用某一个类的类名，就可以创建该类的对象。调用的返回值是一个引用（reference），该引用指向该类的对象。比如，我们创建一个 `Point` 类的对象，则它的返回值是一个指向 `Point` 类对象的引用，同时我们将这个引用赋值给 `blank` 这个变量。

```python
>>> blank = Point()
>>> blank
<__main__.Point object at 0x100ef2c50>
```

生成一个新对象的过程称为**实例化（instantiation）**，生成的对象称为该类的一个**实例（instance）**。

## 15.2 属性（Attributes）

无

## 15.3 矩形（Rectangles）

无

## 15.4 对象作为返回值（Instances as return values）

无

## 15.5 对象是可变的（Objects are mutable）

无

## 15.6 复制（Copying）

**在 Python 中，`is` 运算符判断的是两个引用是否指向同一个对象（即引用相等），而 `==` 运算符判断的是两个对象是否相等（即值相等）**。这一点与 Java 恰好相反，在 Java 中，`==` 运算符判断的是引用相等，而值相等则是通过 `equals` 方法进行判断的。

但是，在 Python 中，对于用户自定义的类，`==` 运算符与 `is` 运算符实现的功能是一样的，都是检查对象的引用是否相等。

```python
# Case 1
>>> l1 = ['I', 'Love', 'Python']
>>> l2 = l1
>>> l1 is l2
True
>>> l1 == l2
True
>>> id(l1)
4502865672
>>> id(l2)
4502865672

# Case2
>>> l1 = ['a', 'b']
>>> l2 = ['a', 'b']
>>> l1 is l2
False
>>> l1 == l2
True
>>> id(l1)
4502885192
>>> id(l2)
4502885128
```

当你调用 `copy` 模块的 `copy` 方法复制对象时，实际上只是执行**浅复制（shallow copy）**，即 `copy` 方法只会复制该对象以及它包含的引用，而不包含引用所指向的对象。`copy` 模块的另一个方法 `deepcopy` 则不只是复制对象以及对象包含的引用，同时也会复制引用所指向的对象，这样操作称为**深复制（deep copy）**。

## 15.7 调试（Debugging）

可以用内建函数 `isinstance` 来检查一个对象是否为某个类的实例。

```python
>>> isinstance(p, Point)
True
```

可以用内建函数 `hasattr` 来检查一个对象是否含有某个特定的属性（attribute）。

```python
>>> hasattr(p, 'x')
True
```

除了可以使用 `hasattr` 方法，也可以使用 `try` 语句。

```python
try:
    x = p.x
except AttributeError:
    x = 0
```

