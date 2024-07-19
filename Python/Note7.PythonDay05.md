#  Python学习Day05（2024.07.16）

> 笔者学习笔记依据B站UP主***鱼C-小甲鱼***，学习视频为：[【Python教程】《零基础入门学习Python》最新版]([序章_哔哩哔哩_bilibili](https://www.bilibili.com/video/BV1c4411e77t?p=1&vd_source=3052c1e7ab8ae1ae3bd0668a229fc4b7))
>
> 本次学习章节为P37-P41

## 一、字典（P37-P39）

***字典是Python中唯一实现映射关系的内置类型***

```python
>>> def morsecode1(code):
        # 摩斯密文表
        c_table = [".-", "-...", "-.-.", "-..", ".", "..-.",
                   "--.", "....", "..", ".---", "-.-", ".-..",
                   "--", "-.", "---", ".--.", "--.-", ".-.",
                   "...", "-", "..-", "...-", ".--", "-..-",
                   "-.--", "--..", ".----", "..---", "...--", "....-",
                   ".....", "-....", "--...", "---..", "----.", "-----"]
        # 摩斯明文表
        d_table = ["A", "B", "C", "D", "E", "F",
                   "G", "H", "I", "J", "K", "L",
                   "M", "N", "O", "P", "Q", "R",
                   "S", "T", "U", "V", "W", "X",
                   "Y", "Z", "1", "2", "3", "4",
                   "5", "6", "7", "8", "9", "0"]
        split_code = code.split(" ")
        result = [d_table[c_table.index(each)] for each in split_code]
        return result

>>> def morsecode2(code):
        # 摩斯密码对比表
        c_table = [".-", "A", "-...", "B", "-.-.", "C", "-..", "D",
                   ".", "E", "..-.", "F", "--.", "G", "....", "H",
                   "..", "I", ".---", "J", "-.-", "K", ".-..", "L", 
                   "--", "M", "-.", "N", "---", "O", ".--.", "P",
                   "--.-", "Q", ".-.", "R", "...", "S", "-", "T",
                   "..-", "U", "...-", "V", ".--", "W", "-..-", "X",
                   "-.--", "Y", "--..", "Z", ".----", "1", "..---", "2",
                   "...--", "3", "....-", "4", ".....", "5", "-....", "6",
                   "--...", "7", "---..", "8", "----.", "9", "-----", "0"]
        split_code = code.split(" ")
        result = [c_table[c_table.index(each) + 1] for each in split_code]
        return result

>>> def morsecode3(code):
        # 摩斯密码对比表
        c_table = {".-":"A", "-...":"B", "-.-.":"C", "-..":"D",
                   ".":"E", "..-.":"F", "--.":"G", "....":"H",
                   "..":"I", ".---":"J", "-.-":"K", ".-..":"L", 
                   "--":"M", "-.":"N", "---":"O", ".--.":"P",
                   "--.-":"Q", ".-.":"R", "...":"S", "-":"T",
                   "..-":"U", "...-":"V", ".--":"W", "-..-":"X",
                   "-.--":"Y", "--..":"Z", ".----":"1", "..---":"2",
                   "...--":"3", "....-":"4", ".....":"5", "-....":"6",
                   "--...":"7", "---..":"8", "----.":"9", "-----":"0"}
        split_code = code.split(" ")
        result = [c_table[each] for each in split_code]
        return result

>>> timeit.timeit("morsecode1(test_code)", setup="from __main__ import morsecode1, test_code")
6.067698999999948
>>> timeit.timeit("morsecode2(test_code)", setup="from __main__ import morsecode2, test_code")
8.933190200000013
>>> timeit.timeit("morsecode3(test_code)", setup="from __main__ import morsecode3, test_code")
4.9598333999999795
```

```python
>>> timeit.timeit("l[l.index('...') + 1]", setup="from __main__ import l", number=100000000)
41.949857800000245
>>> timeit.timeit("d['...']", setup="from __main__ import d", number=100000000)
2.510694699999931
```

字典创建包括大括号和冒号两大部分

![c3761b5dc7dccd7be6e22cc6b60576a](https://gitee.com/lu-hua7/picture/raw/master/c3761b5dc7dccd7be6e22cc6b60576a.png)

字典创建的六种方法

![476ebf6dc54aa5151e4b736efd8ec7d](https://gitee.com/lu-hua7/picture/raw/master/476ebf6dc54aa5151e4b736efd8ec7d.png)

### 1.增

通过formkeys方法，赋初始值value

![795b41036303308fd64c1b514e3d0c8](https://gitee.com/lu-hua7/picture/raw/master/795b41036303308fd64c1b514e3d0c8.png)

![51fae986c613a268e2bbab8bfaf0d35](https://gitee.com/lu-hua7/picture/raw/master/51fae986c613a268e2bbab8bfaf0d35.png)

### 2.删

弹出指定的键值，若不存在会抛出异常，可以设置default参数提示不存在

![beb3c8692ad91505ee1726ad7f0a1ac](https://gitee.com/lu-hua7/picture/raw/master/beb3c8692ad91505ee1726ad7f0a1ac.png)

![a7fddf16d49b2797c8f775fafbac26b](https://gitee.com/lu-hua7/picture/raw/master/a7fddf16d49b2797c8f775fafbac26b.png)

popitem方法会弹出最后一个加入的键值

![8ab5064dda72bb8059f4d40d9471e9d](https://gitee.com/lu-hua7/picture/raw/master/8ab5064dda72bb8059f4d40d9471e9d.png)

del可以删除指定键值，也可以将字典整个删除

![576c9dba7e116b289a6df10e255b55d](https://gitee.com/lu-hua7/picture/raw/master/576c9dba7e116b289a6df10e255b55d.png)

而clear可以清除字典内的内容，使其变成一个空字典

![54a774e8ca1aff580327cea7a4f113b](https://gitee.com/lu-hua7/picture/raw/master/54a774e8ca1aff580327cea7a4f113b.png)

### 3.改

可以直接对指定字典进行更改，也可以使用update

![7e4c65ec43fd99a5501e16d5bb5e384](https://gitee.com/lu-hua7/picture/raw/master/7e4c65ec43fd99a5501e16d5bb5e384.png)

若查询不存在时会抛出异常，可以使用setdefault在查询不存在时返回默认值，对已存在的不会改变

![6bf10f8d30ed32197c44c05ad3ae4e6](https://gitee.com/lu-hua7/picture/raw/master/6bf10f8d30ed32197c44c05ad3ae4e6.png)

> 视图对象即字典动态视图，这就意味着当字典的内容发生改变时，视图对象的内容也会相应地跟着改变。

![1eca98bc2ef89b133d7c1b90d543e0a](https://gitee.com/lu-hua7/picture/raw/master/1eca98bc2ef89b133d7c1b90d543e0a.png)

![203f559bbc0ebdba75491cdf1c15729](https://gitee.com/lu-hua7/picture/raw/master/203f559bbc0ebdba75491cdf1c15729.png)

### 4.嵌套

![347a0950bb1a5bab77679f0b9fc5495](https://gitee.com/lu-hua7/picture/raw/master/347a0950bb1a5bab77679f0b9fc5495.png)

### 5.字典推导式

![88f44ce8af2f3f0393dc945635c176b](https://gitee.com/lu-hua7/picture/raw/master/88f44ce8af2f3f0393dc945635c176b.png)

让我们解释一下下面这段代码的执行结果：

```python
d = {x: y for x in [1, 3, 5] for y in [2, 4, 6]}
```

这段代码使用字典推导式创建了一个字典，其中：

1. `[1, 3, 5]` 是一个列表，包含数字 1、3 和 5。
2. `[2, 4, 6]` 是另一个列表，包含数字 2、4 和 6。
3. 外层的 `for x in [1, 3, 5]` 遍历列表中的每个 x 值。
4. 内层的 `for y in [2, 4, 6]` 遍历列表中的每个 y 值。

这会生成所有可能的 `(x, y)` 组合，作为字典中的键值对。具体步骤如下：

- 当 `x` 为 1 时，`y` 分别取 2、4、6，生成键值对 (1, 2)、(1, 4)、(1, 6)。
- 当 `x` 为 3 时，`y` 分别取 2、4、6，生成键值对 (3, 2)、(3, 4)、(3, 6)。
- 当 `x` 为 5 时，`y` 分别取 2、4、6，生成键值对 (5, 2)、(5, 4)、(5, 6)。

由于字典中的键必须是唯一的，因此相同键的值会被后面的值覆盖。最终生成的字典会是：

```python
{
    1: 6,
    3: 6,
    5: 6
}
```

也就是说，对于每个键 `1`、`3` 和 `5`，对应的值是最后一次遍历时的 `y` 值 `6`。

## 二、集合（P40-P41）

集合是无序的，所以不能使用下标的方式访问集合元素，可以使用循环访问

![f4a01cd01a2a34cf4c280e21267eaf8](https://gitee.com/lu-hua7/picture/raw/master/f4a01cd01a2a34cf4c280e21267eaf8.png)

可以使用isdisjoint检查是否具有关联性、issubset检查是否是子集、issuperset检查是否是超集

![d2c0c74ba48b0a4ed07fdd781956f00](https://gitee.com/lu-hua7/picture/raw/master/d2c0c74ba48b0a4ed07fdd781956f00.png)

除此之外，还可以进行并集、交集、差集，且和直接用大小于号是等价的

若使用运算符，则要保证符号两边都是集合，方法可以使用任何可迭代对象

![284fae3f465d07bc06ded1a37b13a1e](https://gitee.com/lu-hua7/picture/raw/master/284fae3f465d07bc06ded1a37b13a1e.png)

![75721d10bc1562f2d97070984a24ce2](https://gitee.com/lu-hua7/picture/raw/master/75721d10bc1562f2d97070984a24ce2.png)

不可变集合frozenset不可进行修改

![2107bc4145114ed0d22a6f3407bb4c5](https://gitee.com/lu-hua7/picture/raw/master/2107bc4145114ed0d22a6f3407bb4c5.png)

延续上文中的差集、交集、对称差集，可以做更新操作

![2b4fe5f8ff79fc646f84c1edcdba718](https://gitee.com/lu-hua7/picture/raw/master/2b4fe5f8ff79fc646f84c1edcdba718.png)

可哈希，一个整数的不同类型对应的哈希值是相同的

Python中大部分可变对象都是不可哈希的，大部分不可变对象都是可哈希的

![db081650241b4de174d97b8908c311b](https://gitee.com/lu-hua7/picture/raw/master/db081650241b4de174d97b8908c311b.png)

![68654f5ab5d83384ad42030545fb0a3](https://gitee.com/lu-hua7/picture/raw/master/68654f5ab5d83384ad42030545fb0a3.png)

添加一行代码，使得查找过程的执行效率提高10000倍以上

![2a3c5a778431d082312e7c07c54089e](https://gitee.com/lu-hua7/picture/raw/master/2a3c5a778431d082312e7c07c54089e.png)

![4ce54fc2475b65e227f6b706fb173a3](https://gitee.com/lu-hua7/picture/raw/master/4ce54fc2475b65e227f6b706fb173a3.png)
