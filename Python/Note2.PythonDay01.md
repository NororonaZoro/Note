# Python学习Day01（2024.06.23）

> 笔者学习笔记依据B站UP主***鱼C-小甲鱼***，学习视频为：[【Python教程】《零基础入门学习Python》最新版]([序章_哔哩哔哩_bilibili](https://www.bilibili.com/video/BV1c4411e77t?p=1&vd_source=3052c1e7ab8ae1ae3bd0668a229fc4b7))
>
> 本次学习章节为P1-P12

## 编译器选择（P1-P2）

甲老师说，为了防止现有idea惯坏新手，还是建议大家使用Python自带的IDLE（貌似确实很有道理~~~）

点击Windows菜单，找到已下载的Python文件夹（笔者为Python3.12），点击打开IDLE

![65cdb5e5ec0e6ae3855f9ed7b606460](https://gitee.com/lu-hua7/picture/raw/master/65cdb5e5ec0e6ae3855f9ed7b606460.png)

OK！我们成功完成了第一步，开始我们的编程之旅吧~

## 经典开局（P3）

和世界打招呼~

```python
print("Hello World!")
```

![a343b907c8cc4ebc5e8a2fda049ac7f](https://gitee.com/lu-hua7/picture/raw/master/a343b907c8cc4ebc5e8a2fda049ac7f.png)

### 彩蛋！

```python
import this
```

![f39915705329ab8aa5a661a9d1d5bcf](https://gitee.com/lu-hua7/picture/raw/master/f39915705329ab8aa5a661a9d1d5bcf.png)

Python开发者送给我们的一首诗，好好好，浪漫起来咯

## 编写第一个游戏--猜数字（P3）

我们所使用的IDLE有两种模式，分别是刚才所使用的**交互模式**，以及我们接下来要使用的**编辑器模式**

点击IDLE左上角"File"，并创建新的文件"New File"

![dfd876e491ccda1efb607971545cf1f](https://gitee.com/lu-hua7/picture/raw/master/dfd876e491ccda1efb607971545cf1f.png)

请务必一字一句敲出来以下代码！！！

```python
""" 用Python设计第一个游戏 """

temp = input("不妨猜一下小甲鱼现在心里想的是哪个数字:")
guess = int(temp)

if guess == 8:
    print("你是小甲鱼心里的蛔虫嘛？！")
    print("哼，猜中了也没奖励")
else:
    print("猜错啦，小甲鱼现在心里想的是8!")

print("游戏结束，不玩啦^-^")

```

辛苦啦~敲完后"Crtl + S"进行保存，并且点击"RUN"，再点击"Run Module"

![1a83be0a117f4d875ccaafefcd921ec](https://gitee.com/lu-hua7/picture/raw/master/1a83be0a117f4d875ccaafefcd921ec.png)

如果编译没有问题，则会有以下运行结果

![522ae99905d19cf73419da38d2df6d3](https://gitee.com/lu-hua7/picture/raw/master/522ae99905d19cf73419da38d2df6d3.png)

如果出现报错，请考虑以下几种可能出现的问题

```
1.请检查标点符号是否全部为英文符号？
2.请检查缩进是否正确？
3.请检查函数拼写是否正确？
```

- 解决问题一

  建议选择中英文区别较大的主题字体，点击"Options"，再选择"Configure IDLE"

  ![af007ef605fb4df12c04855c187ea7a](https://gitee.com/lu-hua7/picture/raw/master/af007ef605fb4df12c04855c187ea7a.png)

  建议选择"Consolas"字体，12号大小

  ![f8cafbb1353e87a959cd04c0bcfb6ff](https://gitee.com/lu-hua7/picture/raw/master/f8cafbb1353e87a959cd04c0bcfb6ff.png)

- 解决问题二

  在笔者感觉，Python的缩进就好比其它语言的花括号，Python的缩进代表的是语法

  不像其他语言加上大括号，即使缩进有些问题，但依然能够正常执行

  所以就想甲老师说的，一定要确定好每一行的缩进！！！

- 解决问题三

  代码中的函数名调用一定要正确，不然无法使用正常功能

  彩蛋：输入该代码可以显示所有可用函数功能

  ```python
  dir(__builtins__)
  ```

  ![343c7a074e1254b96233f7f4b08ed38](https://gitee.com/lu-hua7/picture/raw/master/343c7a074e1254b96233f7f4b08ed38.png)

## 变量和字符串（P4-P5）

目前笔者学习的感觉来说，和大部分语言一样，最大的区别就是不用声明，直接通过赋值去定义变量的属性

哦，对！还有swap很方便，可以直接互换变量赋值即可做到

```python
x = 3
y = 5
x, y = y, x
print(x, y)
```

![a5a76ecdc12421e6796d7e17659a10c](https://gitee.com/lu-hua7/picture/raw/master/a5a76ecdc12421e6796d7e17659a10c.png)

字符串的话，需要注意单引号双引号成对出现，内容中出现引号的部分需要用"\\"反斜杠标出

![e5e4e8ef054f90c0d85bf0ab23e6b03](https://gitee.com/lu-hua7/picture/raw/master/e5e4e8ef054f90c0d85bf0ab23e6b03.png)

同时他和Java一样，可以进行字符串的拼接，如下图所示

![a40217cea66d6d450e193ed52ac447c](https://gitee.com/lu-hua7/picture/raw/master/a40217cea66d6d450e193ed52ac447c.png)

## 阅读我们的第一个游戏代码（P6）

（以上记录止于2024.06.24 00:25:22，以下记录始于2024.06.25 00:03:26，***救命救命晚上疯狂补笔记***）

```python
""" 用Python设计第一个游戏 """

temp = input("不妨猜一下小甲鱼现在心里想的是哪个数字:")
guess = int(temp)

if guess == 8:
    print("你是小甲鱼心里的蛔虫嘛？！")
    print("哼，猜中了也没奖励")
else:
    print("猜错啦，小甲鱼现在心里想的是8!")

print("游戏结束，不玩啦^-^")
```

第一个游戏代码使用的是**编辑器模式**（另一种是**交互模式**别忘啦）

使用了功能函数**input**，感觉把coder完成用户交互功能做的更加简便了（这也是笔者学习Python的第一感受）

其次使用了分支语句**if else**，当然别忘了最重要的冒号“**:**”

## 改进我们的小游戏（P7-P8）

由于我们之前的小游戏只能猜一次，非常的不人性化，并且！每次的数字对于不同用户来说都一样

为了放置有人猜出来告诉其他人，并且增加游戏的乐趣，我们对当前代码进行了修改

```python
""" 用Python设计第一个游戏 """
import random

counts = 3
answer = random.randint(1, 10)

while counts > 0:
    temp = input("不妨猜一下小甲鱼现在心里想的是哪个数字:")
    guess = int(temp)

    if guess == answer:
        print("你是小甲鱼心里的蛔虫嘛？！")
        print("哼，猜中了也没奖励")
        break
    else:
        if guess < answer:
            print("小啦~")
        else:
            print("大啦~")
    counts = counts - 1

print("正确答案是：")
print(answer)
print("游戏结束，不玩啦^-^")

```

首先我们通过**import**导包，引入了随机数random函数，给答案赋了一个1~10的随机数，每个人有三次游戏机会

同时，在游戏中会提醒用户当前所猜的数字相较于正确答案大了还是小了，这样就更像一个真正的游戏了

笔者对代码进行了一行修改，加入了打印最终的正确答案，这样起码用户在游戏结束后可以知道答案~

（哈哈哈哈哈啊哈，我好善良↑，我在夜晚补笔记发的疯，别管！！！）

## 数字类型（P9-P10）

Python对于大数非常友好（笔者在编程前期已经被大数折磨很久了，虽然现在也是的说）

多大的数他都可以给出精确的答案

![aa881de4d38da46838e508868db25a7](https://gitee.com/lu-hua7/picture/raw/master/aa881de4d38da46838e508868db25a7.png)

并且正常的整数除以整数，也会以小数点的方式给出答案

![85d6a0a4299fb0ac50575d54c659f99](https://gitee.com/lu-hua7/picture/raw/master/85d6a0a4299fb0ac50575d54c659f99.png)

（以上记录止于2024.06.25 00:23:41，以下记录始于2024.07.13 21:53:00(我勒个拖了这么长时间，真的是~)，***先睡了，明儿还要当牛马***）

但是在进行浮点数计算的时候就会出现一些问题（Python使用IEEE754存储标准）

![66d741c3af083c7e379ba68c2b2a746](https://gitee.com/lu-hua7/picture/raw/master/66d741c3af083c7e379ba68c2b2a746.png)

为了解决这个问题，我们引入**Decimal**

![3ecfa6505b4f76a63ed486af6c59903](https://gitee.com/lu-hua7/picture/raw/master/3ecfa6505b4f76a63ed486af6c59903.png)

如上图所示，我们通过实例化，将数字字符转换成数字，这时进行浮点数的运算和比较则会出现正确的结果

除此之外，科学计数法也是一个很重要的点，在Python中我们用**E**来表示，相当于乘以10的多少次

![c9579327cb130594675daa2604ae209](https://gitee.com/lu-hua7/picture/raw/master/c9579327cb130594675daa2604ae209.png)

如上图，用科学计数法表示就是5x10(-5次方)

复数也是一个小点，将一个变量赋值成复数，则可以通过real和imag函数来读取它的实部和虚部

![3c3e71c65e71a8134d373fb7fe7ad3c](https://gitee.com/lu-hua7/picture/raw/master/3c3e71c65e71a8134d373fb7fe7ad3c.png)

以下是Python运算表，大部分运算与其他语言类似，也有少部分有区别![1741473c5dd788586512c5aa142178b](https://gitee.com/lu-hua7/picture/raw/master/1741473c5dd788586512c5aa142178b.png)

**x // y**是地板除，结果必为一个整数，是向下取整（**取比当前完整结果小的最大整数**）需要注意负数的地板除

![f9b519035779ed22e969ceff7aaf9d8](https://gitee.com/lu-hua7/picture/raw/master/f9b519035779ed22e969ceff7aaf9d8.png)

而被除数X其实也可以用以下式子进行计算

![9dc6a768c8953a49a09a12fe3e554d4](https://gitee.com/lu-hua7/picture/raw/master/9dc6a768c8953a49a09a12fe3e554d4.png)

且Python内置函数**divmod**可以直接同时求出两个数地板除和取余的结果，如下图所示

![2c98d49aac92d7436619eedede94474](https://gitee.com/lu-hua7/picture/raw/master/2c98d49aac92d7436619eedede94474.png)

绝对值基本一样，需要注意对复数取绝对值是在求它的**模**

![cb9ec6227ab5fd49eb7e9b5e01c0447](https://gitee.com/lu-hua7/picture/raw/master/cb9ec6227ab5fd49eb7e9b5e01c0447.png)

int和float可以将字符串或者数字取整（取浮点数），complex可以取为复数但是加号两边不能有空格

![9cc52056d270551b4dd180ac94d5619](https://gitee.com/lu-hua7/picture/raw/master/9cc52056d270551b4dd180ac94d5619.png)

幂次方有两种表示方法，pow和**，而引入第三个参数则相当于对幂次方运算后的结果做取余运算

![1dbe656a640ce500e9202e7b932e6e0](https://gitee.com/lu-hua7/picture/raw/master/1dbe656a640ce500e9202e7b932e6e0.png)

## 布尔类型（P11）

可以通过实例了解Python的布尔类型以及规则

![40e0b73330762e1c452a953c5af7cfd](D:/WeChat/WeChat Files/WeChat Files/wxid_jnldfz5q87uq22/FileStorage/Temp/40e0b73330762e1c452a953c5af7cfd.png)

![43f812cf02fcb3794ff12d95c6ae3ea](D:/WeChat/WeChat Files/WeChat Files/wxid_jnldfz5q87uq22/FileStorage/Temp/43f812cf02fcb3794ff12d95c6ae3ea.png)

由下图可知，布尔类型就是一种特殊的整数类型，它可以进行加减乘除的运算

![824e6461ea760fcccf5caeb5cb9443e](https://gitee.com/lu-hua7/picture/raw/master/824e6461ea760fcccf5caeb5cb9443e.png)

笔者觉得甲老师说的挺好的，就直接截图了（实际是懒了，感觉没什么可记的了）

![e100d6888c8f2bc00154dd5a7a6f97e](https://gitee.com/lu-hua7/picture/raw/master/e100d6888c8f2bc00154dd5a7a6f97e.png)

以下是对老师话的印证，但是同时也是疑问的抛出，为什么会是以下的结果

![5e9f6912c50b08eb4a30134897259d9](https://gitee.com/lu-hua7/picture/raw/master/5e9f6912c50b08eb4a30134897259d9.png)

## 短路逻辑和运算符优先级（P12）

### 短路逻辑

想想为什么以下题的答案是4，框中文字同时也是上述图片的官方解释

![d1449e192ab37d9f728c88a4df9ae64](https://gitee.com/lu-hua7/picture/raw/master/d1449e192ab37d9f728c88a4df9ae64.png)

在我的理解中，像and，只有全为真才能确定为真，所以依据**短路逻辑**，“FishC”为真还不够，需要确定and后面是否为真，所以当确定了“LOVE”后才确定为真，所以打印最后一个操作数“LOVE”，而or只需要一个为真即为真，所以当检测到有为真的操作时即可打印，所以为“FishC”

![2166f18a0b3cae8caba3d552054cb0e](https://gitee.com/lu-hua7/picture/raw/master/2166f18a0b3cae8caba3d552054cb0e.png)

### 运算符优先级

想想为什么答案是4

![dc16c9d7abba635d746a29995c89002](https://gitee.com/lu-hua7/picture/raw/master/dc16c9d7abba635d746a29995c89002.png)

来张图先，数字越大优先级越高（感觉要被截到包浆了这张图）

![3f83dd142513ed8ecc8bc59d92f7a27](https://gitee.com/lu-hua7/picture/raw/master/3f83dd142513ed8ecc8bc59d92f7a27.png)

根据上表我们可以看看下图的结果是怎么得出来的

![d3f510cc8ead8770e7a0c2f86a56aef](https://gitee.com/lu-hua7/picture/raw/master/d3f510cc8ead8770e7a0c2f86a56aef.png)

**1 + 2 > 3 - 4 **加减优先级大于比较，所以相当于在比较3 > -1

**not 1 < 2** 先进行比较，1小于2得到True，再not所以是False

**0 or 1 and not 2** 先计算not 2为False，再计算1 and False为False，最后0 or False得False
