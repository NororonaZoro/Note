#  Python学习Day04（2024.07.15）

> 笔者学习笔记依据B站UP主***鱼C-小甲鱼***，学习视频为：[【Python教程】《零基础入门学习Python》最新版]([序章_哔哩哔哩_bilibili](https://www.bilibili.com/video/BV1c4411e77t?p=1&vd_source=3052c1e7ab8ae1ae3bd0668a229fc4b7))
>
> 本次学习章节为P34-P36

> [!IMPORTANT]
>
> 列表、元组和字符串的共同点
>
> 1.都可以通过索引获取每一个元素
>
> 2.第一个元素的索引值都是0
>
> 3.都可以通过切片的方法获取范围内的元素的集合
>
> 4.都有很多共同的运算符

## 一、序列（P34-P36）

列表、元组和字符串被统称为序列

根据**是否能被修改**这一原则，分为**可变序列**（列表）和**不可变序列**（元组和字符串）

### 1.序列的运算符和函数

#### （1）+ 和 *

id()会返回一个代表指定对象的唯一标识的整数值

![093ac79a35fe007a167dd6f4767cfa7](https://gitee.com/lu-hua7/picture/raw/master/093ac79a35fe007a167dd6f4767cfa7.png)

#### （2）is 和 is not

判断是否指向同一个对象

![dff98de1c4517535946476c71135f6a](../../WeChat/WeChat Files/WeChat Files/wxid_jnldfz5q87uq22/FileStorage/Temp/dff98de1c4517535946476c71135f6a.png)

#### （3）in 和 not in

判断是否包含

![0a9831feb46ab7e4f6d140e0533fa93](https://gitee.com/lu-hua7/picture/raw/master/0a9831feb46ab7e4f6d140e0533fa93.png)

#### （4）del

用于删除一个或多个指定对象

删除可变序列中的指定元素

![5747d8fbb3e55fa84381b3baf234d1e](https://gitee.com/lu-hua7/picture/raw/master/5747d8fbb3e55fa84381b3baf234d1e.png)

### 2.序列的函数

#### （1）列表、元组和字符串相互转换

![2c58e319f5dd0c57c4f096b14d96381](https://gitee.com/lu-hua7/picture/raw/master/2c58e319f5dd0c57c4f096b14d96381.png)

#### （2）max 和 min

![098d6686e63ec543a964aec42f0f22f](https://gitee.com/lu-hua7/picture/raw/master/098d6686e63ec543a964aec42f0f22f.png)

#### （3）len 和 sum

![972cd98454a9e94f11e367f80d53a3c](https://gitee.com/lu-hua7/picture/raw/master/972cd98454a9e94f11e367f80d53a3c.png)

#### （4）sorted 和 reversed

sorted会创建一个新的列表，而s.sort()会在s中排序

![83534c5c87984d684b3cd9e8b2cdb57](https://gitee.com/lu-hua7/picture/raw/master/83534c5c87984d684b3cd9e8b2cdb57.png)

#### （5）all 和 any

**all函数**判断可迭代对象中所有元素的值是否为真

**any函数**判断可迭代对象中是否存在某个元素为真

![82b0586c80ed596a28f53c68f7b0f1d](https://gitee.com/lu-hua7/picture/raw/master/82b0586c80ed596a28f53c68f7b0f1d.png)

#### （6）enumerate

用于返回一个枚举对象，它的功能就是将可迭代对象中的每个元素及从0开始的序号共同构成一个二元组的列表。

![1818d1674d40a3f277d288a9f052540](https://gitee.com/lu-hua7/picture/raw/master/1818d1674d40a3f277d288a9f052540.png)

#### （7）zip

用于创建一个聚合多个可迭代对象的迭代器。

它会将作为参数传入的每个可迭代对象的每个元素依次组合成元组，即第i个元组包含来自每个参数的第i个元素。

![](https://gitee.com/lu-hua7/picture/raw/master/7abd1d36cd4fd56339da8725830bd95.png)

对于以上丢失的部分，可以通过itertools来保证其完整性

#### （8）map

会根据提供的函数对指定的可迭代对象的每个元素进行运算，并将返回运算结果的迭代器。

![ce049ced287b5b33422806fac87bd52](https://gitee.com/lu-hua7/picture/raw/master/ce049ced287b5b33422806fac87bd52.png)

#### （9）filter

会根据提供的函数对指定的可迭代对象的每个元素进行运算，并将运算结果为真的元素，以迭代器的形式返回。

![3e990b81ac49074a030d30d5bdb0d2f](https://gitee.com/lu-hua7/picture/raw/master/3e990b81ac49074a030d30d5bdb0d2f.png)

### 3.迭代器 VS 可迭代对象

> [!IMPORTANT]
>
> 一个迭代器肯定是一个可迭代对象
>
> 可迭代对象可进行重复操作
>
> 迭代器是一次性的

![46b40a9d28801c7250ff469f5172bac](https://gitee.com/lu-hua7/picture/raw/master/46b40a9d28801c7250ff469f5172bac.png)

next可取出迭代器中的元素，没有元素可取会抛出异常，我们可以设置该异常提示

![2a94b6baff3ceb04409a7e3aadce20a](https://gitee.com/lu-hua7/picture/raw/master/2a94b6baff3ceb04409a7e3aadce20a.png)