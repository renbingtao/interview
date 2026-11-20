# Python 语句

## while 循环语句

在 python 中，while … else 在循环条件为 false 时执行 else 语句块：

```python
count = 0
while count < 5:
    print count, " is  less than 5"
    count = count + 1
else:
    print count, " is not less than 5"
```

以上实例输出结果为：

```text
0 is less than 5
1 is less than 5
2 is less than 5
3 is less than 5
4 is less than 5
5 is not less than 5
```

如果是break退出，则不会执行else

```python
a = True
while a:
    print("a")
    break
else:
    print("b")
```

以上代码输出 a

### 简单语句组

类似 if 语句的语法，如果你的 while 循环体中只有一条语句，你可以将该语句与while写在同一行中， 如下所示：

```python
flag = 1

while (flag): print 'Given flag is really true!'

print "Good bye!"
```

注意：以上的无限循环你可以使用 CTRL+C 来中断循环。

## for 循环语句

Python for循环可以遍历任何序列的项目，如一个列表或者一个字符串。

```python
for letter in 'Python':     # 第一个实例
    print("当前字母: %s" % letter)

fruits = ['banana', 'apple',  'mango']
for fruit in fruits:        # 第二个实例
    print ('当前水果: %s'% fruit)

print ("Good bye!")
```

### 通过序列索引迭代

```python
fruits = ['banana', 'apple',  'mango']
for index in range(len(fruits)):
    print ('当前水果 : %s' % fruits[index])

print ("Good bye!")
```

range返回一个序列的数。

### 循环使用 else 语句

for … else中，else 中的语句会在循环正常执行完（即 for 不是通过 break 跳出而中断的）的情况下执行，while … else 也是一样。

## pass 语句

pass 是空语句，是为了保持程序结构的完整性，不做任何事情，一般用做占位语句

```python


def sample(n_samples):
    pass
```

此处的pass便是占据一个位置，因为如果定义一个空函数程序会报错，当你没有想好函数的内容是可以用 pass 填充，使程序可以正常运行。
