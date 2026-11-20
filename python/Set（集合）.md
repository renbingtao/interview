# 集合（Set）

Python 中的集合（Set）是一种无序、可变的数据类型，用于存储唯一的元素。

集合中的元素不会重复，并且可以进行交集、并集、差集等常见的集合操作。

在 Python 中，集合使用大括号 {} 表示，元素之间用逗号 , 分隔。也可以使用 set() 函数创建集合。

**注意：创建一个空集合必须用 set() 而不是 {}，因为 {} 创建的是一个空字典。**

## 创建集合

```python
my_set = {1, 2, 3}
my_set2 = set("hello")
my_set3 = set([4, 5, 6, 7])

print(2 in my_set)      # 输出True
```

## 集合元素的类型限制

集合中的元素必须是可哈希（Hashable）的对象。

常见的可哈希对象包括整数、浮点数、字符串，以及所有成员都可哈希的元组。

列表、字典和普通集合通常不可哈希，不能直接作为集合元素。

```python
my_set = {1, 3.14, "Python", (1, 2)}

my_set2 = {[1, 2], [3, 4]}      # TypeError: unhashable type: 'list'
```

## 集合运算

设 `a = set('abracadabra')`，`b = set('alacazam')`：

| 运算符 | 运算 | 含义 |
| --- | --- | --- |
| `-` | `a - b` | 差集，在 a 中但不在 b 中。具有方向性，a - b 与 b - a 的结果通常不同 |
| `\|` | `a \| b` | 并集，在 a 或 b 中 |
| `&` | `a & b` | 交集，同时在 a 和 b 中 |
| `^` | `a ^ b` | 对称差集，在 a 或 b 中，但不同时存在 |

```python
a = set('abracadabra')
b = set('alacazam')

print(a)        # a 中的唯一字符（输出顺序不固定）  {'c', 'b', 'a', 'd', 'r'}
print(a - b)    # 差集     {'r', 'b', 'd'}
print(a | b)    # 并集     {'c', 'l', 'z', 'b', 'a', 'd', 'm', 'r'}
print(a & b)    # 交集     {'c', 'a'}
print(a ^ b)    # 对称差集 {'l', 'z', 'r', 'b', 'd', 'm'}
```

## 集合推导式

与列表推导式类似，Python 也支持集合推导式（Set Comprehension），可以使用简洁的语法创建集合。

```python
squares = {x * x for x in range(1, 6)}
print(sorted(squares))      # 输出[1, 4, 9, 16, 25]
```

## 集合的基本操作

| 方法 | 说明 |
| --- | --- |
| `add(x)` | 向集合添加一个元素 |
| `update(iterable1, iterable2, ...)` | 一次添加多个元素 |
| `remove(x)` | 删除指定元素，如果元素不存在，会抛出 KeyError 异常 |
| `discard(x)` | 删除指定元素，但如果元素不存在，不会抛出异常 |
| `pop()` | 移除并返回一个**任意**元素（不能预测它会返回哪个元素） |

```python
s = {1, 2, 3}

s.add(4)                    # {1, 2, 3, 4}
s.update([5, 6], [7])       # {1, 2, 3, 4, 5, 6, 7}
s.remove(7)                 # 删除 7；元素不存在时抛出 KeyError
s.discard(99)               # 99 不存在，不抛出异常
s.pop()                     # 移除并返回一个任意元素
```

## 判断子集、超集和不相交集合

```python
a = {1, 2}
b = {1, 2, 3, 4}
c = {5, 6}

print(a.isdisjoint(c))      # True，判断两个集合是否没有公共元素
print(a <= b)               # True，子集
print(a < b)                # True，真子集
print(b >= a)               # True，超集
```

## 不可变集合 frozenset

除了普通集合 set，Python 还提供不可变集合 frozenset。

两者都具有元素不重复、无固定顺序等特点，但 frozenset 创建后不能添加或删除元素。

可以使用 frozenset() 创建不可变集合。

```python
a = frozenset([1, 2, 3, 3])
print(a)                    # 输出frozenset({1, 2, 3})
```

frozenset 不支持 add()、remove()、update() 等修改方法。

由于 frozenset 本身可以作为可哈希对象使用，因此也可以将它作为其他集合的元素。

```python
nested_set = {
    frozenset({1, 2}),
    frozenset({3, 4})
}
```

## 集合使用注意事项

- 集合没有固定顺序：不要依赖 print(set) 的元素排列结果，也不要通过下标访问集合
- 元素不能重复：重复添加相同元素不会增加集合大小
- 元素必须可哈希：列表、字典等不可哈希对象不能直接作为集合元素
- set() 可以接收可迭代对象：例如字符串、列表、元组；传入字典时使用的是字典的键
- 集合可以遍历：可以通过 for 循环访问元素，但遍历顺序不应作为业务依据
- 集合不支持索引和切片：不能使用 s[0] 或 s[1:3]
- 注意相等性：例如 True 和 1 在集合中会被视为相等的元素，不能分别作为两个不同元素保存
