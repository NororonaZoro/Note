#  Python学习Day04（2024.07.15）

> 笔者学习笔记依据B站UP主***鱼C-小甲鱼***，学习视频为：[【Python教程】《零基础入门学习Python》最新版]([序章_哔哩哔哩_bilibili](https://www.bilibili.com/video/BV1c4411e77t?p=1&vd_source=3052c1e7ab8ae1ae3bd0668a229fc4b7))
>
> 本次学习章节为P27-P

## 一、元组（P27）

元组与列表直观上的差别是方括号和圆括号

![6554b2c0b0d500e5b599342d45568d3](https://gitee.com/lu-hua7/picture/raw/master/6554b2c0b0d500e5b599342d45568d3.png)

元组加不加圆括号都可以赋值，也可以通过下标查找，但是不能改变其值，可以进行切片操作

![3253c93ec6659e041958c098daff92b](https://gitee.com/lu-hua7/picture/raw/master/3253c93ec6659e041958c098daff92b.png)

![747529845a803d7cb7f189562134dca](https://gitee.com/lu-hua7/picture/raw/master/747529845a803d7cb7f189562134dca.png)

元组可以通过列表推导式生成列表，但是不能生成另一个元组，好像叫生成器巴拉巴拉，后面会讲

![a7fb3138e5219310156022d1a4e5ae6](https://gitee.com/lu-hua7/picture/raw/master/a7fb3138e5219310156022d1a4e5ae6.png)

如何生成只有**一个元素**的元组

![f9fcb99a56f32077fa333d34e6e97fc](https://gitee.com/lu-hua7/picture/raw/master/f9fcb99a56f32077fa333d34e6e97fc.png)

打包和**解包**

生成一个元组有时候也称为打包，列表也同理



![ff2750ba786dce2a640f1da79db0714](https://gitee.com/lu-hua7/picture/raw/master/ff2750ba786dce2a640f1da79db0714.png)

> [!NOTE]
>
> 赋值号左边容器数量要和右边元组中元素数量相同

![d0e31896708c38cd00c8a10ed73586c](https://gitee.com/lu-hua7/picture/raw/master/d0e31896708c38cd00c8a10ed73586c.png)

Python的多重赋值，底层原理就是先打包再解包

![0612bdc7b4b005a7490336b1d682854](https://gitee.com/lu-hua7/picture/raw/master/0612bdc7b4b005a7490336b1d682854.png)

虽然元组中的元素不可变，但是如果元组中的元素指向一个列表，那便是可以修改值的

![5bae5dd4b93a9499cfaafc88fe215f0](https://gitee.com/lu-hua7/picture/raw/master/5bae5dd4b93a9499cfaafc88fe215f0.png)

## 二、字符串（P28-P33）

### 1.再看回文数

![d5e4b345b5acb7f2af4450216d6a143](https://gitee.com/lu-hua7/picture/raw/master/d5e4b345b5acb7f2af4450216d6a143.png)

### 2.字符串的小伙伴们

#### （1）切换大小写

![dc08647ddae400b0d51894fd0d290ac](https://gitee.com/lu-hua7/picture/raw/master/dc08647ddae400b0d51894fd0d290ac.png)

![6da67ea2f8c5d120071f043d821ba43](https://gitee.com/lu-hua7/picture/raw/master/6da67ea2f8c5d120071f043d821ba43.png)

#### （2）对齐

![eed8655c560ca29528507d2610a9ce6](https://gitee.com/lu-hua7/picture/raw/master/eed8655c560ca29528507d2610a9ce6.png)

![83d162add5dda616ab0932f0a307dfb](https://gitee.com/lu-hua7/picture/raw/master/83d162add5dda616ab0932f0a307dfb.png)

#### （3）查找

![535c26eeb1b39b66891a6bf36ba4f82](https://gitee.com/lu-hua7/picture/raw/master/535c26eeb1b39b66891a6bf36ba4f82.png)

> [!NOTE]
>
> 注意find和index在找不到元素时，所返回的结果有差别

![b85c8823670b501d7d9dc868b171499](https://gitee.com/lu-hua7/picture/raw/master/b85c8823670b501d7d9dc868b171499.png)

#### （4）替换

![0ac67680af992f78e4de3ec0f258357](https://gitee.com/lu-hua7/picture/raw/master/0ac67680af992f78e4de3ec0f258357.png)

![01ad8f2f0c91f3de9dd20fb0c06fe65](https://gitee.com/lu-hua7/picture/raw/master/01ad8f2f0c91f3de9dd20fb0c06fe65.png)

#### （5）判断

![197d7c028d8baa719e32ffff092ab27](https://gitee.com/lu-hua7/picture/raw/master/197d7c028d8baa719e32ffff092ab27.png)

![731ee0b9704df5d39e4c22b930dd836](https://gitee.com/lu-hua7/picture/raw/master/731ee0b9704df5d39e4c22b930dd836.png)

![953d233ea2619ead5dc1bfcd9d5f674](https://gitee.com/lu-hua7/picture/raw/master/953d233ea2619ead5dc1bfcd9d5f674.png)

![a3d75f7af4db575223d63e2776d72db](https://gitee.com/lu-hua7/picture/raw/master/a3d75f7af4db575223d63e2776d72db.png)

isalnum()中，只要周围四个有一个判断为True，则为True

![d1307341985d825ac4d7e2fe8b6f4a6](https://gitee.com/lu-hua7/picture/raw/master/d1307341985d825ac4d7e2fe8b6f4a6.png)

以下是判断是否为合法标识符

![eb4a5152217cff4b73cf07db9dddb89](https://gitee.com/lu-hua7/picture/raw/master/eb4a5152217cff4b73cf07db9dddb89.png)

以下可以判断是否为关键字

![7227f15c950b67da1796a8b1650ad51](https://gitee.com/lu-hua7/picture/raw/master/7227f15c950b67da1796a8b1650ad51.png)

#### （6）截取

![6a6f8c22bfaf1572f1e2942a9c0df8f](https://gitee.com/lu-hua7/picture/raw/master/6a6f8c22bfaf1572f1e2942a9c0df8f.png)

![b4668c85c00519c68b7eb8079f7a7ac](https://gitee.com/lu-hua7/picture/raw/master/b4668c85c00519c68b7eb8079f7a7ac.png)

#### （7）拆分和拼接

![13267126f6922206bcb7039e00f0c5e](https://gitee.com/lu-hua7/picture/raw/master/13267126f6922206bcb7039e00f0c5e.png)

![beb663f2536cf7fd99a7fd7638cb9f8](https://gitee.com/lu-hua7/picture/raw/master/beb663f2536cf7fd99a7fd7638cb9f8.png)

#### （8）格式化字符串

![a8adf5e9582bf61dabc1994507463fc](https://gitee.com/lu-hua7/picture/raw/master/a8adf5e9582bf61dabc1994507463fc.png)

![e073f00bce31b1a6ebf7438c8cfc01b](https://gitee.com/lu-hua7/picture/raw/master/e073f00bce31b1a6ebf7438c8cfc01b.png)

![a84f21fab5e3a2a5cc4345b30892de3](https://gitee.com/lu-hua7/picture/raw/master/a84f21fab5e3a2a5cc4345b30892de3.png)

![859b2e64b6b54cb8977c0b53de741f5](https://gitee.com/lu-hua7/picture/raw/master/859b2e64b6b54cb8977c0b53de741f5.png)

![9b75bd99234b9711112e16434a0b11f](https://gitee.com/lu-hua7/picture/raw/master/9b75bd99234b9711112e16434a0b11f.png)

![be02e0bf02ac49fc882369c2b9692e3](https://gitee.com/lu-hua7/picture/raw/master/be02e0bf02ac49fc882369c2b9692e3.png)

![22ffa5834405863bee62be66a206ee1](https://gitee.com/lu-hua7/picture/raw/master/22ffa5834405863bee62be66a206ee1.png)

[.precision]精度

![9ab25aaa69d238d0e1371fc265788bb](https://gitee.com/lu-hua7/picture/raw/master/9ab25aaa69d238d0e1371fc265788bb.png)

![e38572062e0cea0c97316f70284eae6](https://gitee.com/lu-hua7/picture/raw/master/e38572062e0cea0c97316f70284eae6.png)

[.type]类型

![31da0274ec415fd58b08a99c82b4afd](https://gitee.com/lu-hua7/picture/raw/master/31da0274ec415fd58b08a99c82b4afd.png)

![237d649c55e09d4277c499ed5a32dbf](https://gitee.com/lu-hua7/picture/raw/master/237d649c55e09d4277c499ed5a32dbf.png)

[#]

![f82194d1ab06e202d6f5c4b0cd8bfc5](https://gitee.com/lu-hua7/picture/raw/master/f82194d1ab06e202d6f5c4b0cd8bfc5.png)

![7d77b45b1f029dda849b30b098d58f8](https://gitee.com/lu-hua7/picture/raw/master/7d77b45b1f029dda849b30b098d58f8.png)

![9aa1a7a5a8ac3867eb9d5cfb24f2948](https://gitee.com/lu-hua7/picture/raw/master/9aa1a7a5a8ac3867eb9d5cfb24f2948.png)

#### （9）f-字符串

进一步简化了格式化字符串

![2221b73b497b53c713e0f9ae6b2ccb3](https://gitee.com/lu-hua7/picture/raw/master/2221b73b497b53c713e0f9ae6b2ccb3.png)

前边加个F或f直接解决问题

![2a7a1d533062c304c6e1db67957483b](https://gitee.com/lu-hua7/picture/raw/master/2a7a1d533062c304c6e1db67957483b.png)

如果在未知Python版本时，为了保证兼容性，大多还是使用format方法