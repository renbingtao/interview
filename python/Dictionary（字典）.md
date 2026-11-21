# Dictionary（字典）

字典是另一种可变容器模型，且可存储任意类型对象。

字典是一种映射类型，用 {} 标识，它是一个 键(key) : 值(value) 的集合。

键(key) 必须使用不可变类型（所以不能用列表），且在同一个字典中键必须是唯一的。

创建空字典使用 {}。

字典类型也有一些内置的函数，例如 clear()、keys()、values() 等

注意：Python 3.7 起，字典会保持元素的插入顺序，不再是无序的。如果需要有序字典的特性，直接使用普通 dict 即可。

```python
my_dict = {}
my_dict['one'] = "1 - 菜鸟教程"
my_dict[2]     = "2 - 菜鸟工具"

tinydict = {'name': 'runoob', 'code': 1, 'site': 'www.runoob.com'}

print(my_dict['one'])       # 输出键为 'one' 的值
print(my_dict[2])           # 输出键为 2 的值
print(tinydict)             # 输出完整的字典
print(tinydict.keys())      # 输出所有键
print(tinydict.values())    # 输出所有值
```

构造函数 dict() 可以直接从键值对序列中构建字典：

```python
dict([('Runoob', 1), ('Google', 2), ('Taobao', 3)])
```

也可以使用字典推导式，如

```python
my_map = {x: x**2 for x in (2, 4, 6)}
print(my_map)       # 输出{2: 4, 4: 16, 6: 36}
```

## 修改字典

向字典添加新内容的方法是增加新的键/值对，修改或删除已有键/值对如下实例：

```python
tinydict = {'Name': 'Runoob', 'Age': 7, 'Class': 'First'}

tinydict['Age'] = 8               # 更新 Age
tinydict['School'] = "菜鸟教程"  # 添加信息
```

## 删除字典

能删单一的元素也能清空字典，清空只需一项操作。

显式删除一个字典用 del 命令，如下实例：

```python
tinydict = {'Name': 'Runoob', 'Age': 7, 'Class': 'First'}

del tinydict['Name'] # 删除键 'Name'
tinydict.clear()     # 清空字典
del tinydict         # 删除字典
```

## 遍历

```python
for k, v in my_dict.items():
    print(k, v)
```

## 字典内置函数与方法

- `str(my_dict)`：输出字典，可以打印的字符串表示
- `my_dict.copy()`：返回一个字典的浅复制
- `dict.fromkeys(['a', 'c', 'b'], 0)`：创建一个新字典，key 包括 'a'、'c'、'b'，value 统一为 0
- `my_dict.update(my_dict2)`：把 my_dict2 的键值对更新到 my_dict
