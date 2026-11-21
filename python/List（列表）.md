# List（列表）

List（列表）是 Python 中使用最频繁的数据类型。

List 内置了有很多方法，例如 append()、pop() 等等。

列表中元素的类型可以不相同，它支持数字、字符串，甚至可以包含列表（即嵌套列表）。

列表写在方括号 [] 之间，用逗号分隔开的元素列表。

和字符串一样，列表同样可以被索引和截取，列表被截取后返回一个包含所需元素的新列表。

索引也可以从尾部开始，最后一个元素的索引为 -1，往前一位为 -2，以此类推。

```python
t = ['a', 'b', 'c', 'd', 'e']
print(t)                # 输出['a', 'b', 'c', 'd', 'e']
print(t[0])             # 输出a
print(t[1:3])           # 输出['b', 'c']
print(t * 2)            # 输出['a', 'b', 'c', 'd', 'e', 'a', 'b', 'c', 'd', 'e']
```

与 Python 字符串不一样的是，列表中的元素是可以改变的：

```python
t = ['a', 'b', 'c', 'd', 'e']
t[0] = 'x'
print(t)                # 输出['x', 'b', 'c', 'd', 'e']
t[2:4] = ['y', 'z']
print(t)                # 输出['x', 'b', 'y', 'z', 'e']
```

**同理，可以接收第三个参数，表示截取的步长**

```python
t = ['a', 'b', 'c', 'd', 'e']
print(t[1:4:2])         # 输出['b', 'd']
```

若第三个参数为负数，则表示逆向读取

```python
t = ['a', 'b', 'c', 'd', 'e']
print(t[-1::-1])        # 输出['e', 'd', 'c', 'b', 'a']
```

也可以使用 append() 方法来添加列表项：t.append('Baidu')

可以使用 del 语句来删除列表中的元素：del t[2]

`+` 号用于组合列表：[1, 2, 3] + [4, 5, 6] 返回 [1, 2, 3, 4, 5, 6]

`*` 号用于重复列表：['Hi!'] * 4 返回 ['Hi!', 'Hi!', 'Hi!', 'Hi!']

列表比较需要引入 operator 模块的 eq 方法

```python
import operator

a = [1, 2]
b = [2, 3]
c = [2, 3]
print("operator.eq(a,b): ", operator.eq(a, b))   # 输出False
print("operator.eq(c,b): ", operator.eq(c, b))   # 输出True
```

## 列表函数

- `len(list)`：列表元素个数
- `max(list)`：返回列表元素最大值
- `min(list)`：返回列表元素最小值
- `list(seq)`：将元组转换为列表

## 列表方法

- `list.append(obj)`
- `list.count(obj)`：统计某个元素在列表中出现的次数
- `list.extend(seq)`：在列表末尾一次性追加另一个序列中的多个值（用新列表扩展原来的列表）
- `list.index(obj)`：从列表中找出某个值第一个匹配项的索引位置
- `list.insert(index, obj)`：将对象插入列表
- `list.pop([index=-1])`：移除列表中的一个元素（默认最后一个元素），并且返回该元素的值
- `list.remove(obj)`：移除列表中某个值的第一个匹配项
- `list.reverse()`：反向列表中元素
- `list.sort(key=None, reverse=False)`：对原列表进行排序
