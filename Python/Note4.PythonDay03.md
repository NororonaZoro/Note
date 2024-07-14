#  Python学习Day03（2024.07.14）

> 笔者学习笔记依据B站UP主***鱼C-小甲鱼***，学习视频为：[【Python教程】《零基础入门学习Python》最新版]([序章_哔哩哔哩_bilibili](https://www.bilibili.com/video/BV1c4411e77t?p=1&vd_source=3052c1e7ab8ae1ae3bd0668a229fc4b7))
>
> 本次学习章节为P20-P26

## 列表（P20-P26）

### 一、创建列表

列表笔者感觉和数组相似，但又比数组好用，它不限制同一列表中元素的属性

![52bdbf21fe28bdfc063167b6187c41e](https://gitee.com/lu-hua7/picture/raw/master/52bdbf21fe28bdfc063167b6187c41e.png)

### 二、列表切片

看完视频，笔者感觉Python真的太优雅了，不仅可以省略头或者省略尾输出，或者全省略，或者加步进

最最最神奇的是，可以利用上述的负数下标倒序输出！！！

![31d8b6d7df2836602795ea7b21f4349](https://gitee.com/lu-hua7/picture/raw/master/31d8b6d7df2836602795ea7b21f4349.png)

### 三、增

对于列表的增加可以使用append方法，每次在列表末尾增加一个元素，也可以使用extend方法

![ca5f37c24e5034c3cdf52366661b42b](https://gitee.com/lu-hua7/picture/raw/master/ca5f37c24e5034c3cdf52366661b42b.png)

可以利用切片来等同于上述两个方法

![b7da0f4166ae63894d1e4fcd7a04e11](https://gitee.com/lu-hua7/picture/raw/master/b7da0f4166ae63894d1e4fcd7a04e11.png)

insert有两个参数，第一个是插入位置，第二个是插入元素

![45fd7a27291719f7ba58aa214f404ac](https://gitee.com/lu-hua7/picture/raw/master/45fd7a27291719f7ba58aa214f404ac.png)

### 四、删

使用remove方法可以进行删除

![6e541cbd9156cb3630f8fc71ff409f3](https://gitee.com/lu-hua7/picture/raw/master/6e541cbd9156cb3630f8fc71ff409f3.png)

> [!NOTE]
>
> 1.如果列表中存在多个匹配的元素那么它只会删除第一个；
>
> 2.如果指定的元素不存在,那么程序就会报错。

![cddae810cf6f99b729e4355cf252c38](https://gitee.com/lu-hua7/picture/raw/master/cddae810cf6f99b729e4355cf252c38.png)

也可以使用pop进行弹出，显示并且删除（注意下标）

![a94c9c845d25610cbeff0a14f6d02ca](https://gitee.com/lu-hua7/picture/raw/master/a94c9c845d25610cbeff0a14f6d02ca.png)

使用clear直接清空列表

![fd475db96b1fdbf62ac2bf0e170349e](https://gitee.com/lu-hua7/picture/raw/master/fd475db96b1fdbf62ac2bf0e170349e.png)

### 五、改

![b634190b1369a08d0f897e736873b4c](https://gitee.com/lu-hua7/picture/raw/master/b634190b1369a08d0f897e736873b4c.png)

可以利用下标或者切片进行替换

![28997944c57eb2ed9aee3c6a8d829ae](https://gitee.com/lu-hua7/picture/raw/master/28997944c57eb2ed9aee3c6a8d829ae.png)

![a7bc6b4ac580652a1772d1001874172](https://gitee.com/lu-hua7/picture/raw/master/a7bc6b4ac580652a1772d1001874172.png)

sort可以从小到大排序输出，reverse可以逆序输出，二者可以配合使用，当reverse=True时，代表逆序

count可以输出当前列表中某个元素的个数

![61fb76d54b5b42a8023ccb8cf2acbcb](https://gitee.com/lu-hua7/picture/raw/master/61fb76d54b5b42a8023ccb8cf2acbcb.png)

index可以查找当前元素所在位置，也可以通过该方法替换当前只知道元素名称不知道位置的元素

若存在多个相同元素，会返回第一个查找到的下标，也可以通过设定范围返回某范围内下标

copy可以实现拷贝，也可以用切片实现（切片真是伟大的存在）

![96e6207e66307c9116f62dfb150f348](https://gitee.com/lu-hua7/picture/raw/master/96e6207e66307c9116f62dfb150f348.png)

### 六、列表的加法和乘法

![6e7472f7e88f2a737b3184648a7365b](https://gitee.com/lu-hua7/picture/raw/master/6e7472f7e88f2a737b3184648a7365b.png)

### 七、嵌套列表

![d7190836a982f3018783950c34b4113](https://gitee.com/lu-hua7/picture/raw/master/d7190836a982f3018783950c34b4113.png)

### 八、访问嵌套列表

和二维数组有点像

![96efe3b5b1acf827b5d1e8b824690ef](https://gitee.com/lu-hua7/picture/raw/master/96efe3b5b1acf827b5d1e8b824690ef.png)

而在创建的时候，两种看似相同的创建其实并不一样

![899cb42a06529a5f92f99efd1ccae75](https://gitee.com/lu-hua7/picture/raw/master/899cb42a06529a5f92f99efd1ccae75.png)

B这种创建是有问题的，这时我们引入**is**来进行判断，is用来判断对象是否指向同一个地址

![5e19e92674f30a5261e189760e7e23e](https://gitee.com/lu-hua7/picture/raw/master/5e19e92674f30a5261e189760e7e23e.png)

B的创建相当于一种拷贝，把同一个地址写了三份，所以会改变所有

![723a089861748da6c373b10da0cb1bf](https://gitee.com/lu-hua7/picture/raw/master/723a089861748da6c373b10da0cb1bf.png)

以下为正确的创建方式

![5332fa49ef3dc5cc64b29e42a3c2005](https://gitee.com/lu-hua7/picture/raw/master/5332fa49ef3dc5cc64b29e42a3c2005.png)

### 九、变量不是盒子

![ce7cb2f70d48f9813d2006a0a30ab34](https://gitee.com/lu-hua7/picture/raw/master/ce7cb2f70d48f9813d2006a0a30ab34.png)

上图直接将x赋给y，相当于引用，指向的是同一块地址，想要生成两块地址，需要参考以下内容

### 十、浅拷贝和深拷贝

以下两种为浅拷贝

![2091d8d9b3d3add40f075cc8d6a173e](https://gitee.com/lu-hua7/picture/raw/master/2091d8d9b3d3add40f075cc8d6a173e.png)

![2c46c79ec7f4f9775d9204a389c1ee9](https://gitee.com/lu-hua7/picture/raw/master/2c46c79ec7f4f9775d9204a389c1ee9.png)

对于嵌套列表，浅拷贝就不得行了

![9f7a79e5f6173190c90a72adb115112](https://gitee.com/lu-hua7/picture/raw/master/9f7a79e5f6173190c90a72adb115112.png)

引入copy包，也分为浅拷贝方法和深拷贝方法

![f05cd53dbead69191286a7c50f07f48](https://gitee.com/lu-hua7/picture/raw/master/f05cd53dbead69191286a7c50f07f48.png)

### 十一、列表推导式

将列表中的每一个元素都扩大二倍，用列表推导式优化循环

![32580e6625562c772183053c0dee62a](https://gitee.com/lu-hua7/picture/raw/master/32580e6625562c772183053c0dee62a.png)

![d094c92eabeeddf18f7bfdd65edf121](https://gitee.com/lu-hua7/picture/raw/master/d094c92eabeeddf18f7bfdd65edf121.png)

![06dfeed886e72a048b61c1c74ef7d4a](https://gitee.com/lu-hua7/picture/raw/master/06dfeed886e72a048b61c1c74ef7d4a.png)

```python
matrix = [[1, 2, 3], [4, 5, 6], [7, 8, 9]]
elements = [matrix[i][2 - i] for i in range(len(matrix))]
print(elements)  # 输出: [3, 5, 7]
```

### 十二、再谈列表推导式

可以加一个条件判断

![d2420b32119641f328486ca11a76077](https://gitee.com/lu-hua7/picture/raw/master/d2420b32119641f328486ca11a76077.png)

![3f7d3441a3cc5a03232add106bcc101](https://gitee.com/lu-hua7/picture/raw/master/3f7d3441a3cc5a03232add106bcc101.png)

外层循环放前面，内层嵌套循环放后面，不重要的列表可以用下划线当作列表名

![3d3f8a0b71c440e9b0ce70b13feb664](https://gitee.com/lu-hua7/picture/raw/master/3d3f8a0b71c440e9b0ce70b13feb664.png)

来点儿终极的

![597dc1b7595fb1a03f314b635a1de71](https://gitee.com/lu-hua7/picture/raw/master/597dc1b7595fb1a03f314b635a1de71.png)

![7908e177053cd4a13000fd9e7eb6755](https://gitee.com/lu-hua7/picture/raw/master/7908e177053cd4a13000fd9e7eb6755.png)

------

***KISS原则！！！***

![186a996fc9b877018718c41507ba2b2](https://gitee.com/lu-hua7/picture/raw/master/186a996fc9b877018718c41507ba2b2.png)

![4635abdb682990ed1e5d0683facbb9c](https://gitee.com/lu-hua7/picture/raw/master/4635abdb682990ed1e5d0683facbb9c.png)