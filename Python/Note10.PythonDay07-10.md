#  Python学习Day07-10（2024.07.20-2024.07.23）

> 笔者学习笔记依据B站UP主***鱼C-小甲鱼***，学习视频为：[【Python教程】《零基础入门学习Python》最新版]([序章_哔哩哔哩_bilibili](https://www.bilibili.com/video/BV1c4411e77t?p=1&vd_source=3052c1e7ab8ae1ae3bd0668a229fc4b7))
>
> 本次学习章节为P59-P83

## 一、是时候让大家拥有对象了--类和对象（Ⅰ）（P59）

**对象 = 属性 + 方法**

### 1.创建类

![9cfddd2ce008400fa6283da92cfc066](https://gitee.com/lu-hua7/picture/raw/master/9cfddd2ce008400fa6283da92cfc066.png)

### 2.封装

前面的例子中便是把甲鱼的特征属性和行为能力封装在了一起

> 注：不要把不相关的属性和方法封装到一块

### 3.何以见得Python到处是对象

![c85dfc37fd89457334c9bee8e95d708](https://gitee.com/lu-hua7/picture/raw/master/c85dfc37fd89457334c9bee8e95d708.png)

### 4.self是什么

类中的每一个方法默认的第一个参数都是self

![c52dce109d7ebb85bb40e6aa0249bc3](https://gitee.com/lu-hua7/picture/raw/master/c52dce109d7ebb85bb40e6aa0249bc3.png)

#### 详细解释

当你调用实例方法时，例如 `obj.display_value()`，Python 会自动将实例 `obj` 作为第一个参数传递给 `display_value` 方法。如果 `display_value` 方法定义时没有包含 `self` 参数，就会导致参数不匹配的错误。

#### 错误示例

```python
class MyClass:
    def display_value():  # 错误：缺少 self 参数
        print("This won't work")

# 创建实例
obj = MyClass()

# 尝试调用方法
obj.display_value()  # TypeError: display_value() takes 0 positional arguments but 1 was given

```

#### 错误原因

1. **定义方法时没有 `self` 参数**：
   - `def display_value():` 定义了一个不接受任何参数的方法。
2. **调用实例方法时，Python 会传递实例作为第一个参数**：
   - 当你调用 `obj.display_value()` 时，实际调用的是 `MyClass.display_value(obj)`。
3. **参数不匹配**：
   - `MyClass.display_value` 方法定义时没有参数，但是调用时却接收了一个参数（即实例 `obj`），因此会导致参数不匹配，抛出 `TypeError`。

#### 总结

在 Python 中，类的方法定义必须包含 `self` 参数，以便方法能够接收调用该方法的实例对象。如果方法定义时没有 `self` 参数，而调用时 Python 自动传递实例对象，就会导致参数不匹配的 `TypeError` 错误。确保方法定义包含 `self` 参数是编写类方法的基本约定和要求。

## 二、继承、多重继承、组合--类和对象（Ⅱ）（P60）

### 1.继承

继承于某个类的类可以使用其父类的方法和属性，也可覆盖

![e6d7af89dd8de06fe7984d0289e9c7d](https://gitee.com/lu-hua7/picture/raw/master/e6d7af89dd8de06fe7984d0289e9c7d.png)

判断一个对象是否属于某个类

![46c9f4bef8ae6b2403fea3d87b14ead](https://gitee.com/lu-hua7/picture/raw/master/46c9f4bef8ae6b2403fea3d87b14ead.png)

### 2.多重继承

访问顺序从左到右，从当前类中找不到，才会到下一个类中寻找

![c00f2eb16b82760303787cf0d295953](https://gitee.com/lu-hua7/picture/raw/master/c00f2eb16b82760303787cf0d295953.png)

### 3.组合

![f28139ef6385955bb8c493a6b3f5cae](https://gitee.com/lu-hua7/picture/raw/master/f28139ef6385955bb8c493a6b3f5cae.png)

## 三、绑定--类和对象（Ⅲ）（P61）

![24cf9107733deec54e0320804c9f598](https://gitee.com/lu-hua7/picture/raw/master/24cf9107733deec54e0320804c9f598.png)

为什么不加self就会报错

self用于绑定，实例对象和类的方法进行绑定

当我们在调用实例c.get_self()的时候，其实际的含义是调用类C的get_self()方法并将实例对象作为参数传递进去

![f46792b770cc45ac44739fbb8f32280](https://gitee.com/lu-hua7/picture/raw/master/f46792b770cc45ac44739fbb8f32280.png)

![3c9fcac6af2466d4568b468730ee642](https://gitee.com/lu-hua7/picture/raw/master/3c9fcac6af2466d4568b468730ee642.png)

![1be6abfde5a34bb289d26d9914c1216](https://gitee.com/lu-hua7/picture/raw/master/1be6abfde5a34bb289d26d9914c1216.png)

必须使用self进行绑定，否则修改的将不是对象的值

![2ff7152cc3edfa9b74a111961f593b4](https://gitee.com/lu-hua7/picture/raw/master/2ff7152cc3edfa9b74a111961f593b4.png)

> **不要像上述一样直接修改类的属性值，否则容易牵一发而动全身，引发意想不到的后果**

**最小的类！！！--可以当作字典使用**

![c9b332f4d4af1e709eaa5a8f8492f88](https://gitee.com/lu-hua7/picture/raw/master/c9b332f4d4af1e709eaa5a8f8492f88.png)

## 四、构造函数、重写、钻石继承--类和对象（Ⅳ）（P62）

### 1.构造函数

![f4ba9fee3b54f0833fa85ad3fbeb4e2](https://gitee.com/lu-hua7/picture/raw/master/f4ba9fee3b54f0833fa85ad3fbeb4e2.png)

### 2.重写

![7c78bc8e11f0bee1e0f2b3efa3ed4e5](https://gitee.com/lu-hua7/picture/raw/master/7c78bc8e11f0bee1e0f2b3efa3ed4e5.png)

运用不当会导致钻石继承

### 3.钻石继承

![c217170f83e6c284739e44fe17a7059](https://gitee.com/lu-hua7/picture/raw/master/c217170f83e6c284739e44fe17a7059.png)

以上例子发现A的构造函数被调用了两次

例：儿子父亲姑姑奶奶一起去动物园，由于奶奶是父亲和姑姑的妈妈，导致买了两张门票，总共花了五张门票钱

为了解决这个问题调用super()函数

![6e9c433ae58139e21cd5f4ee1f9a059](https://gitee.com/lu-hua7/picture/raw/master/6e9c433ae58139e21cd5f4ee1f9a059.png)

super()遵循MRO方法搜寻父类

> **MRO（Method Resolution Order）是指在多重继承情况下，Python 用来确定方法和属性解析顺序的规则。MRO 决定了从哪个类开始查找方法或属性，以确保在调用方法时按照正确的顺序进行解析。**

![e0544ad9b48ed389158c670935b9f68](https://gitee.com/lu-hua7/picture/raw/master/e0544ad9b48ed389158c670935b9f68.png)

![bd98df92f4973545e286fb24f693200](https://gitee.com/lu-hua7/picture/raw/master/bd98df92f4973545e286fb24f693200.png)

## 五、Mixin及案例源码剖析--类和对象（Ⅴ）（P63）

![8c232b9314853454b7e15d93cc5f25a](https://gitee.com/lu-hua7/picture/raw/master/8c232b9314853454b7e15d93cc5f25a.png)

![cbd41d36f0c354f6f6cba150a03743c](https://gitee.com/lu-hua7/picture/raw/master/cbd41d36f0c354f6f6cba150a03743c.png)

![0e078f08e95090308cf81c316724fc2](https://gitee.com/lu-hua7/picture/raw/master/0e078f08e95090308cf81c316724fc2.png)

![a2ec56c2c64c2c8034f8ddf217e36e8](https://gitee.com/lu-hua7/picture/raw/master/a2ec56c2c64c2c8034f8ddf217e36e8.png)

## 六、多态和鸭子类型--类和对象（Ⅵ）（P64）

### 1.多态

它是指同一个运算符、函数或对象在不同场景下具有不同的作用效果

![89f1d62f3ce6f19eeeae8a8f92acd3e](https://gitee.com/lu-hua7/picture/raw/master/89f1d62f3ce6f19eeeae8a8f92acd3e.png)

![ecc1e52758b29c41ec1325d9441e528](https://gitee.com/lu-hua7/picture/raw/master/ecc1e52758b29c41ec1325d9441e528.png)

![04e2dfe41bc4e411c4754310e68a8e4](https://gitee.com/lu-hua7/picture/raw/master/04e2dfe41bc4e411c4754310e68a8e4.png)

![760b4b900de43116a3463ca71ff5778](https://gitee.com/lu-hua7/picture/raw/master/760b4b900de43116a3463ca71ff5778.png)

![934fa4c9d30ab00af12f98000fdc4c9](https://gitee.com/lu-hua7/picture/raw/master/934fa4c9d30ab00af12f98000fdc4c9.png)

### 2.鸭子类型

鸭子类型（Duck Typing）是动态类型语言（如 Python）中的一种编程风格，它的核心思想是“如果它像鸭子一样走路，像鸭子一样叫，那么它就是鸭子。” 换句话说，在鸭子类型中，不关注对象的类型，而关注对象的行为（方法和属性）。

![88c7f925c2dcd61d5382110e1e9b7cd](https://gitee.com/lu-hua7/picture/raw/master/88c7f925c2dcd61d5382110e1e9b7cd.png)

## 七、私有变量和\_\_slots\_\_--类和对象（Ⅶ）（P65）

### 1.“私有变量”

![97f992650ec00f832b4a518adbbf553](https://gitee.com/lu-hua7/picture/raw/master/97f992650ec00f832b4a518adbbf553.png)

实例化对象后无法再创建类中的私有变量

![88d37dcf36eccd97f093c4414bf0e71](https://gitee.com/lu-hua7/picture/raw/master/88d37dcf36eccd97f093c4414bf0e71.png)

![73cf10abe701dbd81e228520fe2153e](https://gitee.com/lu-hua7/picture/raw/master/73cf10abe701dbd81e228520fe2153e.png)

前者是仅供内部使用的变量属于约定俗成的命名规则

后者例如class，是Python用来定义类的不要随便使用

### 2.效率提升之道

字典是用空间换时间，但若当前类只有几个固定属性不需要动态添加，就会很浪费空间，所以使用\_\_slots\_\_

![42759f59ccc004c1f663a360dc86092](https://gitee.com/lu-hua7/picture/raw/master/42759f59ccc004c1f663a360dc86092.png)

![64a54e376503f03674ce00e4ae5ed1a](https://gitee.com/lu-hua7/picture/raw/master/64a54e376503f03674ce00e4ae5ed1a.png)

![5951332538dd23b58db74ef835dfe5a](https://gitee.com/lu-hua7/picture/raw/master/5951332538dd23b58db74ef835dfe5a.png)

![539893f8e63f3b3cd263e79d9067dd8](https://gitee.com/lu-hua7/picture/raw/master/539893f8e63f3b3cd263e79d9067dd8.png)

## 八、原来Python懂魔法--类和对象（Ⅷ）（P66）

![b19cb671377e46876832a89b26e28cb](https://gitee.com/lu-hua7/picture/raw/master/b19cb671377e46876832a89b26e28cb.png)

![f7b022868ac338287ae94081ac437c1](https://gitee.com/lu-hua7/picture/raw/master/f7b022868ac338287ae94081ac437c1.png)

![a8cad48dce9dce488de0e23173d2230](https://gitee.com/lu-hua7/picture/raw/master/a8cad48dce9dce488de0e23173d2230.png)

![e35064e593741d30591d3b33a06948d](https://gitee.com/lu-hua7/picture/raw/master/e35064e593741d30591d3b33a06948d.png)

![578fe39a2840276a913ea6ce0ccd673](https://gitee.com/lu-hua7/picture/raw/master/578fe39a2840276a913ea6ce0ccd673.png)

若在对象被删除前得以传出去，就可以使得对象重生

![35f87c9675e7a7fe801d88ed439fce3](https://gitee.com/lu-hua7/picture/raw/master/35f87c9675e7a7fe801d88ed439fce3.png)

![98557978cbce06c2395a9c4de1ca2bc](https://gitee.com/lu-hua7/picture/raw/master/98557978cbce06c2395a9c4de1ca2bc.png)

以下定义为闭包函数的原因是为了让self保存在外部函数的x变量中，内部函数的作用适用于窃取这个self对象

在\_\_del\_\_()魔法方法中调用它的时候是带参数的，它就把这个参数给存储起来，如果在外部调用这个函数

它不带参数，就使用默认值None，那么就会返回刚刚拿到的self对象

![69a24b83cfab679ee4eba0d36245ef1](https://gitee.com/lu-hua7/picture/raw/master/69a24b83cfab679ee4eba0d36245ef1.png)

## 九-十、运算相关的魔法方法--类和对象（Ⅸ-Ⅹ）（P67-P68）

![14e6eb1d7bd3a23942c220addbdafac](https://gitee.com/lu-hua7/picture/raw/master/14e6eb1d7bd3a23942c220addbdafac.png)

![e3580f554d6b930ac4c5f5f76af127e](https://gitee.com/lu-hua7/picture/raw/master/e3580f554d6b930ac4c5f5f76af127e.png)

![1957ea675c88890ba047c0e2148f4ff](https://gitee.com/lu-hua7/picture/raw/master/1957ea675c88890ba047c0e2148f4ff.png)

![2fd2491a25b8c432c05d6eb8051fecc](https://gitee.com/lu-hua7/picture/raw/master/2fd2491a25b8c432c05d6eb8051fecc.png)

![807f7b1da853e6010a1e5af6ef7a3d8](https://gitee.com/lu-hua7/picture/raw/master/807f7b1da853e6010a1e5af6ef7a3d8.png)

![2f0beef9d6780ae6059072132402aef](https://gitee.com/lu-hua7/picture/raw/master/2f0beef9d6780ae6059072132402aef.png)

![599fe338a1d6737221c11306200414b](https://gitee.com/lu-hua7/picture/raw/master/599fe338a1d6737221c11306200414b.png)

![29ca55d8f8d53b8b63e166eb6e254b5](https://gitee.com/lu-hua7/picture/raw/master/29ca55d8f8d53b8b63e166eb6e254b5.png)

而下图结果仍是拼接，是因为s2 += s2是两个同对象相加，不符合S2类的函数重写，所以只能从父类中找

而父类中只有原来的 + 也就是拼接，所以结果就是拼接

![5244934f3540c5c84fc7f300742f6de](https://gitee.com/lu-hua7/picture/raw/master/5244934f3540c5c84fc7f300742f6de.png)

![5c66afcdcff8e6520bf5831bececc50](https://gitee.com/lu-hua7/picture/raw/master/5c66afcdcff8e6520bf5831bececc50.png)

代码利用了异常捕获的原理，来解决原本的int无法处理中文的问题

在ValueError中设置好字典，每次判断一个字是否在字典中，若在则将对应数字加到result中

若不在则直接使用int将其转换成数字，每次读取后进行乘十进位

最后通过地板除化为整型

![4322bfec834ec0d2289d5b6e2f110d0](https://gitee.com/lu-hua7/picture/raw/master/4322bfec834ec0d2289d5b6e2f110d0.png)

![adc5cbef62e2cda977388ba5a7a774a](https://gitee.com/lu-hua7/picture/raw/master/adc5cbef62e2cda977388ba5a7a774a.png)

![b60c3bae913ca11ff64fbef8c4337f4](https://gitee.com/lu-hua7/picture/raw/master/b60c3bae913ca11ff64fbef8c4337f4.png)

1. **2 的二进制表示**：
   - `00000010`
2. **按位取反 `~2`**：
   - `00000010` 变为 `11111101`
3. **解释 `11111101`**（由于二进制是负数，所以表达为十进制需要进行操作）：
   - 取反得到 `00000010`
   - 加 1 得到 `00000011`
   - `00000011` 的十进制值是 3
   - 由于原数最高位是 1，表示负数，所以结果是 -3

![67edebba9b89152c5d727a458a782cf](https://gitee.com/lu-hua7/picture/raw/master/67edebba9b89152c5d727a458a782cf.png)

![207b913bdf6e924519a4620712b5726](https://gitee.com/lu-hua7/picture/raw/master/207b913bdf6e924519a4620712b5726.png)

![d151799a0e2da5da1033b2a9a04af37](https://gitee.com/lu-hua7/picture/raw/master/d151799a0e2da5da1033b2a9a04af37.png)

math的ulp会加该数的最低有效位

![445b8c12c347a65fbbdd32bdff94372](https://gitee.com/lu-hua7/picture/raw/master/445b8c12c347a65fbbdd32bdff94372.png)

上图中容易被误会的index，应该把对象作为索引值或者参数的时候，他才会起作用

## 十一、属性访问相关的魔法方法--类和对象（‌XI）（P69）

![0ab2cf3e7b450f0d18559c3b9bd7422](https://gitee.com/lu-hua7/picture/raw/master/0ab2cf3e7b450f0d18559c3b9bd7422.png)

getattr和\_\_getattribute\_\_函数对应

![193320798a9c918ab75dad5f5fe2138](https://gitee.com/lu-hua7/picture/raw/master/193320798a9c918ab75dad5f5fe2138.png)

![](https://gitee.com/lu-hua7/picture/raw/master/e5251742968f71c310636962f7c99fd.png)

setattr应该是给键的值赋值，而不是给赋值给键

![df37a09aa0b059bde904e0cc15163f4](https://gitee.com/lu-hua7/picture/raw/master/df37a09aa0b059bde904e0cc15163f4.png)

![31ea2f128855ba23372851840c9874f](https://gitee.com/lu-hua7/picture/raw/master/31ea2f128855ba23372851840c9874f.png)

## 十二、索引、切片、迭代协议--类和对象（XII）（P70）

笔者感觉看到目前，才明白甲老师把每一种方法背后所对应的类和函数给讲了一遍，也就是原理

![8904b1b6a94a5fd249930e1e96883ad](https://gitee.com/lu-hua7/picture/raw/master/8904b1b6a94a5fd249930e1e96883ad.png)

![67e26b3c98b91293b1b8233382e5ab2](https://gitee.com/lu-hua7/picture/raw/master/67e26b3c98b91293b1b8233382e5ab2.png)

![51429a4dee88852917b5bf60d372577](https://gitee.com/lu-hua7/picture/raw/master/51429a4dee88852917b5bf60d372577.png)

![aeeeacb98cb47efdecfc4511642dd4c](https://gitee.com/lu-hua7/picture/raw/master/aeeeacb98cb47efdecfc4511642dd4c.png)

## 十三、代偿--类和对象（XIII）（P71）

![70b6668b8e1910581c1b8ab18290d66](https://gitee.com/lu-hua7/picture/raw/master/70b6668b8e1910581c1b8ab18290d66.png)

当我们使用 in 和 not in 而类中没有实现时，Python会用 \__iter\_\_ 和 \_\_next\_\_ 代偿

![0ff59bae7c7f1b678aa213a2d9c9cb1](https://gitee.com/lu-hua7/picture/raw/master/0ff59bae7c7f1b678aa213a2d9c9cb1.png)

若没有 \__iter\_\_ 和 \_\_next\_\_ 还会使用 \_\_getitem\_\_

![5fdf4451907372fa516aa6c4f98a6c0](https://gitee.com/lu-hua7/picture/raw/master/5fdf4451907372fa516aa6c4f98a6c0.png)

如果没有 bool 就会用 \_\_len\_\_ 代偿

![1732013d88f8bac7076da8cd685c4d0](https://gitee.com/lu-hua7/picture/raw/master/1732013d88f8bac7076da8cd685c4d0.png)

![3dc76a3aa6051d7856b3d527416df98](https://gitee.com/lu-hua7/picture/raw/master/3dc76a3aa6051d7856b3d527416df98.png)

下图中前三个用的是类中已经写好的长度比较，而后者几个是走的父类的传统比较编码值

![626786f1df0f4ddc829df060902b88c](https://gitee.com/lu-hua7/picture/raw/master/626786f1df0f4ddc829df060902b88c.png)

若不想让某个魔法方法生效，可以直接赋值为None

![00a92d9448d908b0bfafc03bd427877](https://gitee.com/lu-hua7/picture/raw/master/00a92d9448d908b0bfafc03bd427877.png)

![8c2d7fe5c7feefcb191f001298fcbfe](https://gitee.com/lu-hua7/picture/raw/master/8c2d7fe5c7feefcb191f001298fcbfe.png)

## 十四、给人看还是给程序看--类和对象（XIV）（P72）

![cb86c0393a715ca0eb5b14db29fa635](https://gitee.com/lu-hua7/picture/raw/master/cb86c0393a715ca0eb5b14db29fa635.png)

![f5f1dbd7b69f8d8c7be2a66b41c1258](https://gitee.com/lu-hua7/picture/raw/master/f5f1dbd7b69f8d8c7be2a66b41c1258.png)

将以上闭包用魔法方法实现

![c52e33cd29bfc881cca79e2582164cc](https://gitee.com/lu-hua7/picture/raw/master/c52e33cd29bfc881cca79e2582164cc.png)

str()函数是将参数转换为字符串对象，是给人看的

repr()函数则是将对象转换为程序可执行的字符串，是给程序看的

eval()作用是将参数去引号后执行

换句话说，eval()函数是repr()函数的反函数

![b80e0d8dd3f68065ab1e9c6b6cc9361](https://gitee.com/lu-hua7/picture/raw/master/b80e0d8dd3f68065ab1e9c6b6cc9361.png)

str会找repr代偿，反过来则不行

![01f3427e6d4609a4ef3ae37b59394d6](https://gitee.com/lu-hua7/picture/raw/master/01f3427e6d4609a4ef3ae37b59394d6.png)

\_\_str\_\_ 魔法方法对应的只能应用于对象出现在打印操作的顶层

如果我们把多个对象放到一个列表中，然后把这个列表打印出来的话，就无法访问到这个对应的字符串了

![3e19812c41054c75340629dc862a8a5](https://gitee.com/lu-hua7/picture/raw/master/3e19812c41054c75340629dc862a8a5.png)

不过，我们通过同时定义两个方法的实现，可以让对象在不同场景下支持不同的显示效果

![74d85d537cb6d1a87ed1e80d6194434](https://gitee.com/lu-hua7/picture/raw/master/74d85d537cb6d1a87ed1e80d6194434.png)

## 十五、property()--类和对象（XV）（P73）

![3fb4474f7fd6706eb81ec40431013eb](https://gitee.com/lu-hua7/picture/raw/master/3fb4474f7fd6706eb81ec40431013eb.png)

![48ece02271253826e12ef8ee74a6da2](https://gitee.com/lu-hua7/picture/raw/master/48ece02271253826e12ef8ee74a6da2.png)

![f02d7eb536e472f11539086887a1ee1](https://gitee.com/lu-hua7/picture/raw/master/f02d7eb536e472f11539086887a1ee1.png)

![f473598e4f9f4fa390805e2105e8699](https://gitee.com/lu-hua7/picture/raw/master/f473598e4f9f4fa390805e2105e8699.png)

![9c47bba3897e801484f30d8810d25bf](https://gitee.com/lu-hua7/picture/raw/master/9c47bba3897e801484f30d8810d25bf.png)

## 十六、类方法和静态方法--类和对象（XVI）（P74）

### 1.类方法

类中的方法无法直接通过类来使用，需要通过类实例化对象来使用，究其根本是需要实例化对象的绑定

![d27bb4e4d6542d69330c775532930d8](https://gitee.com/lu-hua7/picture/raw/master/d27bb4e4d6542d69330c775532930d8.png)

![d179997868019cc0698081f95aba062](https://gitee.com/lu-hua7/picture/raw/master/d179997868019cc0698081f95aba062.png)

这里直接使用类名也可以来访问类属性，但若涉及到继承问题，那么使用类方法无疑会有更大的优势

## 2.静态方法

作用是在类里边去定义一个不需要绑定的函数

![215e16c512ea74770f54811a79e6328](https://gitee.com/lu-hua7/picture/raw/master/215e16c512ea74770f54811a79e6328.png)

![e36b902945e104ef541331523dc3fb0](https://gitee.com/lu-hua7/picture/raw/master/e36b902945e104ef541331523dc3fb0.png)

## 十七、描述符和property()实现原理--类和对象（XVII）（P75）

### 1.描述符

只要是实现了以下一个或多个方法的类，这个类就叫做描述符

![4dc841610106e52b20fa29e0f6ec2cd](https://gitee.com/lu-hua7/picture/raw/master/4dc841610106e52b20fa29e0f6ec2cd.png)

![10e10394b3d9ca338212b58ec752171](https://gitee.com/lu-hua7/picture/raw/master/10e10394b3d9ca338212b58ec752171.png)

![45e95a855a169f8e536a69df8484524](https://gitee.com/lu-hua7/picture/raw/master/45e95a855a169f8e536a69df8484524.png)

将上述代码，用描述符实现

![5985d717fdcee1034ce14f94ed72a4f](https://gitee.com/lu-hua7/picture/raw/master/5985d717fdcee1034ce14f94ed72a4f.png)

### 2.property()函数

> 尝试利用描述符创造一个property()函数

![90304a16cd989aeaa60ead3a9a0d18f](https://gitee.com/lu-hua7/picture/raw/master/90304a16cd989aeaa60ead3a9a0d18f.png)

> 尝试自己实现getter()、setter()、deleter()方法

![5859d9d4e119c4dd2efcd3e6df6568c](https://gitee.com/lu-hua7/picture/raw/master/5859d9d4e119c4dd2efcd3e6df6568c.png)

![a024a59df534973fe8c0825ee145b20](https://gitee.com/lu-hua7/picture/raw/master/a024a59df534973fe8c0825ee145b20.png)

![3a933ecc7c7b9d0baa7fa14ed60b8da](https://gitee.com/lu-hua7/picture/raw/master/3a933ecc7c7b9d0baa7fa14ed60b8da.png)

## 十八、描述符、非数据描述符、优雅编程--类和对象（XIII）（P76）

描述符应该作用于类属性才会起作用，而不是作用于对象属性

![984c2b5292213a0fc0a78d871edf1e7](https://gitee.com/lu-hua7/picture/raw/master/984c2b5292213a0fc0a78d871edf1e7.png)

![2121e08c54e8b01297e0c83492f2082](https://gitee.com/lu-hua7/picture/raw/master/2121e08c54e8b01297e0c83492f2082.png)

当发生属性访问时，优先级从高到低

![92e4f76ed53e4b7a7cec62a5ec4b2fc](https://gitee.com/lu-hua7/picture/raw/master/92e4f76ed53e4b7a7cec62a5ec4b2fc.png)

由下图可知，用c.x访问时会被get~拦截，尽管用set方法进行了FishC的赋值操作，直接查询c.x仍然是get~

![5c18706e9c939485c5b2ec277f8610f](https://gitee.com/lu-hua7/picture/raw/master/5c18706e9c939485c5b2ec277f8610f.png)

get()方法写在getattribute中的，是它的默认实现逻辑

![f144dddb6c559c8f559ddb36defd394](https://gitee.com/lu-hua7/picture/raw/master/f144dddb6c559c8f559ddb36defd394.png)

![ee768b5e486824c3c9ad359fcdd6332](https://gitee.com/lu-hua7/picture/raw/master/ee768b5e486824c3c9ad359fcdd6332.png)

上图实现中，类C中把字符串转换成属性非常不优雅，于是便有了下图的 \_\|set_name\_\_ 

![5cb22da58cc69d425de3a4933290560](https://gitee.com/lu-hua7/picture/raw/master/5cb22da58cc69d425de3a4933290560.png)

## 十九、函数、方法、静态方法、类方法的底层实现原理--类和对象（XIX）（P77）

![d1d1d8dded3f3b9033ce85e1dabd6eb](https://gitee.com/lu-hua7/picture/raw/master/d1d1d8dded3f3b9033ce85e1dabd6eb.png)

Python是如何分辨函数和方法的呢--答案指向了描述符

![16c63f4f5a091a9aa89c6a9d351f43d](https://gitee.com/lu-hua7/picture/raw/master/16c63f4f5a091a9aa89c6a9d351f43d.png)

![bf0f72b255cff9d854f8ef050d55bf9](https://gitee.com/lu-hua7/picture/raw/master/bf0f72b255cff9d854f8ef050d55bf9.png)

![545d551ccc9f90c6c4fe814aa8a6413](https://gitee.com/lu-hua7/picture/raw/master/545d551ccc9f90c6c4fe814aa8a6413.png)

![2a31ccc2ae6de2fe3faaa4bfbf9d2bd](https://gitee.com/lu-hua7/picture/raw/master/2a31ccc2ae6de2fe3faaa4bfbf9d2bd.png)

![01bb807ecec73024d1201c413b605c2](https://gitee.com/lu-hua7/picture/raw/master/01bb807ecec73024d1201c413b605c2.png)

![2f9c39667063d8e195730b4fbd9db77](https://gitee.com/lu-hua7/picture/raw/master/2f9c39667063d8e195730b4fbd9db77.png)

![](https://gitee.com/lu-hua7/picture/raw/master/a3658966f6b27106cb834d9c27ec409.png)

## 二十、类装饰器--类和对象（XX）（P78）

![8f5b63ba6f9df1820549e80240b1fe9](https://gitee.com/lu-hua7/picture/raw/master/8f5b63ba6f9df1820549e80240b1fe9.png)

用类做装饰器，来装饰函数

![b0da293d44c624dea81724a3af50248](https://gitee.com/lu-hua7/picture/raw/master/b0da293d44c624dea81724a3af50248.png)

![5a6518e257026c90cca34018e3e39d9](https://gitee.com/lu-hua7/picture/raw/master/5a6518e257026c90cca34018e3e39d9.png)

上图c1的name被c2覆盖了，看似像是在实例化对象，实则不是，是在调用早已实例好的对象

因为对象在@check的时候就诞生了

我们在访问c1.name和c2.name时，实际上访问的是check类实例对象的name属性

而check类没有属性，它就会去\_\_getattr\_\_中寻找

所以看似在是实例化c1和c2，实际上是当作函数调用了两次，只实例化了Check一次

所以当第二次调用name为c2时，就会把前者覆盖掉

解决方法：再套一层

![1674b438a4aa17803af5272f4395ce5](https://gitee.com/lu-hua7/picture/raw/master/1674b438a4aa17803af5272f4395ce5.png)

这样写就会将Check类实例化两次，而非一次

## 二十一、type()函数和\_\_init\_subclass\_\_--类和对象（XⅪ）（P79）

### 1.type()函数

![690bfa6ec58d3fc69234abe7dddfb4b](https://gitee.com/lu-hua7/picture/raw/master/690bfa6ec58d3fc69234abe7dddfb4b.png)

![d122a826438fe3b1694af878c276ac8](https://gitee.com/lu-hua7/picture/raw/master/d122a826438fe3b1694af878c276ac8.png)

![d5ea522dcedb937727de3b833977824](https://gitee.com/lu-hua7/picture/raw/master/d5ea522dcedb937727de3b833977824.png)

![65f47cdf9f0aa0848b82d15d51df5c3](https://gitee.com/lu-hua7/picture/raw/master/65f47cdf9f0aa0848b82d15d51df5c3.png)

### 2.\_\_init\_subclass\_\_

![44b873dd6ed591583557aaf56e3c1ed](https://gitee.com/lu-hua7/picture/raw/master/44b873dd6ed591583557aaf56e3c1ed.png)

![b141f3e51369f9512903c9a776774ae](https://gitee.com/lu-hua7/picture/raw/master/b141f3e51369f9512903c9a776774ae.png)

## 二十二、元类--类和对象（XⅪ）（P80）

![cb241018df4b34d7ee6f66c278c88de](https://gitee.com/lu-hua7/picture/raw/master/cb241018df4b34d7ee6f66c278c88de.png)

![32598f13ef37ec933ca999e021bd29f](https://gitee.com/lu-hua7/picture/raw/master/32598f13ef37ec933ca999e021bd29f.png)

![39bbe8fe6bf347de8fd27d1f9ede520](https://gitee.com/lu-hua7/picture/raw/master/39bbe8fe6bf347de8fd27d1f9ede520.png)

## 二十三、元类的应用--类和对象（XXIII）（P81）

![eee040107e930c34bf6539feb5418db](https://gitee.com/lu-hua7/picture/raw/master/eee040107e930c34bf6539feb5418db.png)

对类名的定义规范做限制

![6b8c6762154e69f378be410620f491a](https://gitee.com/lu-hua7/picture/raw/master/6b8c6762154e69f378be410620f491a.png)

修改对象的属性值

![281f492a6b0bd7951aa6eb04608d863](https://gitee.com/lu-hua7/picture/raw/master/281f492a6b0bd7951aa6eb04608d863.png)

限制类实例化的传参方式

![847b66204696a4bacb39cf63c44bf2f](https://gitee.com/lu-hua7/picture/raw/master/847b66204696a4bacb39cf63c44bf2f.png)

禁止一个类被直接实例化

![b612fc34c97211409b8b310475ec37b](https://gitee.com/lu-hua7/picture/raw/master/b612fc34c97211409b8b310475ec37b.png)

![0042925e62868b0a58997ca3d4519d6](https://gitee.com/lu-hua7/picture/raw/master/0042925e62868b0a58997ca3d4519d6.png)

只允许实例化一个对象

![5187f70e9d405cc5d2e87f0fb440e2e](https://gitee.com/lu-hua7/picture/raw/master/5187f70e9d405cc5d2e87f0fb440e2e.png)

## 二十四、抽象基类--类和对象（XXIV）（P82）

![195d867c8abba952f2156dd5c6c5151](https://gitee.com/lu-hua7/picture/raw/master/195d867c8abba952f2156dd5c6c5151.png)

抽象基类只能继承使用，并要在子类中重写抽象方法

![5d021fb0b41ccdaf0255697bac702ee](https://gitee.com/lu-hua7/picture/raw/master/5d021fb0b41ccdaf0255697bac702ee.png)

鸭子类型和抽象类有点相似，但是鸭子类型可能手滑时产生一些容易被忽略的bug，可以使用抽象类将其暴露出来

![abead75ecb82102c9f19b2aa740691a](https://gitee.com/lu-hua7/picture/raw/master/abead75ecb82102c9f19b2aa740691a.png)

可以看到下图，在代码运行时就已经触发报错了，还没使用代码

![da26b2a32ab1f5d083c49e579ad5119](https://gitee.com/lu-hua7/picture/raw/master/da26b2a32ab1f5d083c49e579ad5119.png)

![25046d541337195278508012595014d](https://gitee.com/lu-hua7/picture/raw/master/25046d541337195278508012595014d.png)

## 二十五、类和对象（XXV）（P83）

![fb16d258bcc323355e4c17d83883e48](https://gitee.com/lu-hua7/picture/raw/master/fb16d258bcc323355e4c17d83883e48.png)

笔者感觉到后面越学越不精，希望自己可以坚持吧~