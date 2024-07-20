#  Python学习Day06（2024.07.19）

> 笔者学习笔记依据B站UP主***鱼C-小甲鱼***，学习视频为：[【Python教程】《零基础入门学习Python》最新版]([序章_哔哩哔哩_bilibili](https://www.bilibili.com/video/BV1c4411e77t?p=1&vd_source=3052c1e7ab8ae1ae3bd0668a229fc4b7))
>
> 本次学习章节为P42-P53

## 一、函数（Ⅰ）（P42）

### 1.创建和调用函数

![1018d0aa430a071676187395bea17d7](https://gitee.com/lu-hua7/picture/raw/master/1018d0aa430a071676187395bea17d7.png)

### 2.函数的参数

占坑位的是**形参**

实际传递数据的是**实参**

![e3537a71daf600b0a8971ac44c4c4b5](https://gitee.com/lu-hua7/picture/raw/master/e3537a71daf600b0a8971ac44c4c4b5.png)

### 3.函数的返回值

![b6c477cb0d0bfa25d3bffcf866d6958](https://gitee.com/lu-hua7/picture/raw/master/b6c477cb0d0bfa25d3bffcf866d6958.png)

## 二、函数（Ⅱ）（P43）

### 1.位置参数

![4d351d731ba61e21678b430e01459fc](https://gitee.com/lu-hua7/picture/raw/master/4d351d731ba61e21678b430e01459fc.png)

### 2.关键字参数

![d7a80e1b9c4e4ce6c5319458051a39e](https://gitee.com/lu-hua7/picture/raw/master/d7a80e1b9c4e4ce6c5319458051a39e.png)

> [!CAUTION]
>
> 位置参数必须在关键字参数之前

![2757bbe957e6b92aeb26effe3ccd99b](https://gitee.com/lu-hua7/picture/raw/master/2757bbe957e6b92aeb26effe3ccd99b.png)

### 3.默认参数

默认参数要放到最后

![91adac1b6f5c114c07b91218695ee4a](https://gitee.com/lu-hua7/picture/raw/master/91adac1b6f5c114c07b91218695ee4a.png)

### 4.冷门知识点

斜杠左边只能使用位置参数，右边无规定

![836068a8fa5148e5a684ae3708e30cf](https://gitee.com/lu-hua7/picture/raw/master/836068a8fa5148e5a684ae3708e30cf.png)

星号左边无规定，右边必须是关键字参数

![c38dec3c96932433a48c1776fdbd871](https://gitee.com/lu-hua7/picture/raw/master/c38dec3c96932433a48c1776fdbd871.png)

## 三、函数（Ⅲ）（P44）

### 1.收集参数

![1acbc3f0ac124e214f89288378e3da0](https://gitee.com/lu-hua7/picture/raw/master/1acbc3f0ac124e214f89288378e3da0.png)

### 2.函数的打包和解包

![7f3e39cf9b6862fbacd03f740913778](https://gitee.com/lu-hua7/picture/raw/master/7f3e39cf9b6862fbacd03f740913778.png)

当收集参数和关键字参数同时存在时，需要写清关键字参数，或者使用上节课讲的星号

![f645a6ab725137763e794d765ab447e](https://gitee.com/lu-hua7/picture/raw/master/f645a6ab725137763e794d765ab447e.png)

可以将参数打包为字典，使用两个连续的星号

![b63812281c3da3a0a0bd766b18dc0cf](https://gitee.com/lu-hua7/picture/raw/master/b63812281c3da3a0a0bd766b18dc0cf.png)

### 3.解包参数

![f56ce020328d8934cf0ae8014d61c22](https://gitee.com/lu-hua7/picture/raw/master/f56ce020328d8934cf0ae8014d61c22.png)

## 四、函数（Ⅳ）（P45）

### 1.作用域

![d2a89d7984062224787ec07ca082606](https://gitee.com/lu-hua7/picture/raw/master/d2a89d7984062224787ec07ca082606.png)

![df09db99ab31dedc4562613814d1194](https://gitee.com/lu-hua7/picture/raw/master/df09db99ab31dedc4562613814d1194.png)

### 2.global语句

![e4daeb525306dfc659f3fea9da69cdf](https://gitee.com/lu-hua7/picture/raw/master/e4daeb525306dfc659f3fea9da69cdf.png)

### 3.嵌套函数

![f24672221a6102168e8e7eb8edc2036](https://gitee.com/lu-hua7/picture/raw/master/f24672221a6102168e8e7eb8edc2036.png)

### 4.nonlocal语句

![014aef1d01c0eb97fc64ee97b08029b](https://gitee.com/lu-hua7/picture/raw/master/014aef1d01c0eb97fc64ee97b08029b.png)

### 5.LEGB规则

**Local、Enclosed、Global、Build-In**

赋值把BIF函数给覆盖掉了，注意不要起一些和BIF函数相同的变量名

![0e87e71a77e2840d302ed29dd17f611](https://gitee.com/lu-hua7/picture/raw/master/0e87e71a77e2840d302ed29dd17f611.png)

## 五、闭包--函数（Ⅴ）（P46）

![24fbc99c77ff766be45c4eec525143a](https://gitee.com/lu-hua7/picture/raw/master/24fbc99c77ff766be45c4eec525143a.png)

实现带记忆功能的函数

![fe68f7033bdae46d84c78925d29f1e8](https://gitee.com/lu-hua7/picture/raw/master/fe68f7033bdae46d84c78925d29f1e8.png)

![d36dcceed4a7848655bd99bc1c3333a](https://gitee.com/lu-hua7/picture/raw/master/d36dcceed4a7848655bd99bc1c3333a.png)

![3b352d8ac7d8851efc3e5aa6d0665f9](https://gitee.com/lu-hua7/picture/raw/master/3b352d8ac7d8851efc3e5aa6d0665f9.png)

## 六、装饰器--函数（Ⅵ）（P47）

闭包的作用：

1.利用嵌套函数的外层作用域具有记忆功能的特性让数据保存在外层函数的参数或者变量中

2.将内层函数作为返回值给返回，这样就可以从外部间接地调用到内层的函数

![b0c3b60683f6cf35b05e563e0d2f933](https://gitee.com/lu-hua7/picture/raw/master/b0c3b60683f6cf35b05e563e0d2f933.png)

除了以上的方法，我们还可以使用装饰器，如下图

![59dffb82aca9753949e091fa3db2e2b](https://gitee.com/lu-hua7/picture/raw/master/59dffb82aca9753949e091fa3db2e2b.png)

多个装饰器可以用于同个函数

![4ef24ec69c54acb017b666a459c7153](https://gitee.com/lu-hua7/picture/raw/master/4ef24ec69c54acb017b666a459c7153.png)

如何给装饰器传递参数

![8b75d82cd6c2e105351762f6ae67b76](https://gitee.com/lu-hua7/picture/raw/master/8b75d82cd6c2e105351762f6ae67b76.png)

## 七、lambda表达式--函数（Ⅶ）（P48）

![727b38321d6687143518d48b201bdbc](https://gitee.com/lu-hua7/picture/raw/master/727b38321d6687143518d48b201bdbc.png)

lambda是一个表达式而非语句，它能够出现在Python语法中不允许def语句出现的地方，是他最大的优势

但由于所有共=功能代码都局限在一个表达式中去实现，因此，lambda通常也只能实现那些较为简单的需求

## 八、生成器--函数（Ⅷ）（P49）

作用：每调用一次提供一个数据并且会记住当时的状态

![a97acc8daa7cdf8be0a710623b8c3f3](https://gitee.com/lu-hua7/picture/raw/master/a97acc8daa7cdf8be0a710623b8c3f3.png)

每次在执行到yield i的时候就生成一个数据，暂留并保留状态

下一次调用则从下一个语句i += 1开始继续执行

![dc23641d9d8b06190d6eb0d7ae1fad4](https://gitee.com/lu-hua7/picture/raw/master/dc23641d9d8b06190d6eb0d7ae1fad4.png)

用装饰器实现斐波那契数列

![875f310d4af3660802260f0289eda25](https://gitee.com/lu-hua7/picture/raw/master/875f310d4af3660802260f0289eda25.png)

生成器表达式

![1d2903c97f3e5aa25fec192a0bf9dae](https://gitee.com/lu-hua7/picture/raw/master/1d2903c97f3e5aa25fec192a0bf9dae.png)

## 九、递归--函数（Ⅸ）（P50）

递归就是函数调用自身的过程

![33b2ee328a3bd5a5e992c2130441d35](https://gitee.com/lu-hua7/picture/raw/master/33b2ee328a3bd5a5e992c2130441d35.png)

求一个数的阶乘

![1b738be0024cda7bc364d56484a5375](https://gitee.com/lu-hua7/picture/raw/master/1b738be0024cda7bc364d56484a5375.png)

斐波那契数列

![2af300a10af4e564f86c4b080be7369](https://gitee.com/lu-hua7/picture/raw/master/2af300a10af4e564f86c4b080be7369.png)

递归会引起效率问题

## 十、汉诺塔--函数（Ⅹ）（P51）

![8444bee9c59196ee409023342788e7a](https://gitee.com/lu-hua7/picture/raw/master/8444bee9c59196ee409023342788e7a.png)

## 十一、函数文档、类型注释、内省--函数（Xl）（P52）

### 1.函数文档

![e137e24d1216f456cd2bcf63a51dc81](https://gitee.com/lu-hua7/picture/raw/master/e137e24d1216f456cd2bcf63a51dc81.png)

### 2.类型注释

![557b57f3707e7be82e98ba92038d13d](https://gitee.com/lu-hua7/picture/raw/master/557b57f3707e7be82e98ba92038d13d.png)

### 3.内省

![438657e76694150416c9049a3661f06](https://gitee.com/lu-hua7/picture/raw/master/438657e76694150416c9049a3661f06.png)

## 十二、高阶函数（Xll）（P53）

### 1.reduce函数

将第二个参数的可迭代对象依次传递到第一个参数指定的函数中，最终返回结果

![08c7dee7873aa6f3f5c4615593c5fa6](https://gitee.com/lu-hua7/picture/raw/master/08c7dee7873aa6f3f5c4615593c5fa6.png)

### 2.偏函数

偏函数是指对指定的函数进行二次包装

通常是将现有的函数部分参数预先给绑定，从而得到一个新的函数称为偏函数

作用：将一个函数的多个参数拆分多次进行传递

![e6b812ad35b47b5c2e98e85fa7d565c](https://gitee.com/lu-hua7/picture/raw/master/e6b812ad35b47b5c2e98e85fa7d565c.png)

### 3.@wraps装饰器

![b4c67f356024961001cca08feaf8bcd](https://gitee.com/lu-hua7/picture/raw/master/b4c67f356024961001cca08feaf8bcd.png)

![07289bf6bf6a40e740f2d1e8f691443](https://gitee.com/lu-hua7/picture/raw/master/07289bf6bf6a40e740f2d1e8f691443.png)

为什么要使用 `@wraps`

- **保留原始函数的元信息**: 装饰器会覆盖被装饰函数的名称和文档字符串等信息。使用 `@wraps` 可以保留这些信息，使得调试和文档生成更加方便。
- **提高代码的可读性和可维护性**: 保留原始函数的元信息可以帮助开发者更好地理解和维护代码。
- **确保正确性**: 一些框架和库（如单元测试框架）可能依赖函数的元信息。使用 `@wraps` 可以确保这些信息不会丢失，从而避免潜在的问题。

