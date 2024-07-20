#  Python学习Day07（2024.07.20）

> 笔者学习笔记依据B站UP主***鱼C-小甲鱼***，学习视频为：[【Python教程】《零基础入门学习Python》最新版]([序章_哔哩哔哩_bilibili](https://www.bilibili.com/video/BV1c4411e77t?p=1&vd_source=3052c1e7ab8ae1ae3bd0668a229fc4b7))
>
> 本次学习章节为P54-P58

## 一、永久存储（P54-P56）

### 1.打开文件

打开文件进行操作后，要使用close关闭，否则操作将会丢失

![bf8fd7dde878fbf00ceb4ed50e2a689](https://gitee.com/lu-hua7/picture/raw/master/bf8fd7dde878fbf00ceb4ed50e2a689.png)

![e010b19cdb2356e40b2a308e60f7da8](https://gitee.com/lu-hua7/picture/raw/master/e010b19cdb2356e40b2a308e60f7da8.png)

![db8c21a01c3a0cc2b92d6eace64be91](https://gitee.com/lu-hua7/picture/raw/master/db8c21a01c3a0cc2b92d6eace64be91.png)

truncate是截断操作，并且若用w模式打开后再关闭，也会发生截断操作，导致文件中内容丢失！！！

![9e6877821429a9b21c6fb80dfaa2b3e](https://gitee.com/lu-hua7/picture/raw/master/9e6877821429a9b21c6fb80dfaa2b3e.png)

### 2.处理路径

可以导入Path进行路径操作

![266515c8b96960549eaac9306691049](https://gitee.com/lu-hua7/picture/raw/master/266515c8b96960549eaac9306691049.png)

可以获取当前对象的父级路径，也可利用循环一层一层读取

还可以读取文件大小

![c090d923c9519c64a66532ae947ab82](https://gitee.com/lu-hua7/picture/raw/master/c090d923c9519c64a66532ae947ab82.png)

一个点代表上一级路径，两个点代表上两级路径

可以查找该路径下的所有文件

![edfd34a521c6041ed3c87081625bc55](https://gitee.com/lu-hua7/picture/raw/master/edfd34a521c6041ed3c87081625bc55.png)

![c5194bf52e58990009c7d200b2834b7](https://gitee.com/lu-hua7/picture/raw/master/c5194bf52e58990009c7d200b2834b7.png)

可以重命名文件，并将文件放到对应的路径对象下

![02261fa9a65c5645a3114ce9fd17191](https://gitee.com/lu-hua7/picture/raw/master/02261fa9a65c5645a3114ce9fd17191.png)

可删除文件但需要该文件目录下无其他文件

![672c5c29a9149fa22d1e50d3ca357c6](https://gitee.com/lu-hua7/picture/raw/master/672c5c29a9149fa22d1e50d3ca357c6.png)

可查找当前目录下的所有某种类型的文件

![4b79a0b06240b5e487ceb48da6136de](https://gitee.com/lu-hua7/picture/raw/master/4b79a0b06240b5e487ceb48da6136de.png)

### 3.with语句和上下文管理器

with会在操作执行结束自动关闭文件保存

![05b1164f8ccd4799caff79f415d667c](https://gitee.com/lu-hua7/picture/raw/master/05b1164f8ccd4799caff79f415d667c.png)

在对文件进行操作的过程中，若被其他错误语句打断，有无with语句作用一目了然

![fe480130bb0354b29e85f31bac21d7b](https://gitee.com/lu-hua7/picture/raw/master/fe480130bb0354b29e85f31bac21d7b.png)

![fc9bc1bc46d4236264f577b4a019c42](https://gitee.com/lu-hua7/picture/raw/master/fc9bc1bc46d4236264f577b4a019c42.png)

### 4.pickle

它允许你将字符串、列表、字典这些Python对象给保存为文件形式

![b92b54d1ec7bd87d7632b25e9d9b4fc](https://gitee.com/lu-hua7/picture/raw/master/b92b54d1ec7bd87d7632b25e9d9b4fc.png)

![e6c21443d781d949a51cd710d74a263](https://gitee.com/lu-hua7/picture/raw/master/e6c21443d781d949a51cd710d74a263.png)

![4f66618e21bad3f3a4f50e61269e3e7](https://gitee.com/lu-hua7/picture/raw/master/4f66618e21bad3f3a4f50e61269e3e7.png)

![b253b0f98acdde76c233edd4c03df9a](https://gitee.com/lu-hua7/picture/raw/master/b253b0f98acdde76c233edd4c03df9a.png)

## 二、异常（P57-P58）

### 1.阅读异常

Python内部有很多内置异常，可以通过查询文档来读懂系统报出的异常

![c74e632a58a6cbe116535eafd8bd77f](https://gitee.com/lu-hua7/picture/raw/master/c74e632a58a6cbe116535eafd8bd77f.png)

### 2.处理异常

#### （1）try-except

![0973bbb34895eb59554dd83c69451ed](https://gitee.com/lu-hua7/picture/raw/master/0973bbb34895eb59554dd83c69451ed.png)

可以直接在except写异常处理代码，如果不对异常类型分类的话，就会将所有异常按同一种处理

也可以指定异常类型处理，但若代码出现了超出该异常类型的异常便不会处理

![8d9212718b1dd0111c63752915c750f](https://gitee.com/lu-hua7/picture/raw/master/8d9212718b1dd0111c63752915c750f.png)

加入as可以显示异常原因

![59f8fe50714cd4f02989177d8833b09](https://gitee.com/lu-hua7/picture/raw/master/59f8fe50714cd4f02989177d8833b09.png)

也可将多种异常统一处理

![19abc5cc544d26c795122789c319e7a](https://gitee.com/lu-hua7/picture/raw/master/19abc5cc544d26c795122789c319e7a.png)

也可分开处理，但若检测到某行代码异常则会直接跳到异常处理，不会继续运行下边的代码

![d202681e99c94e67ff50c557320fbce](https://gitee.com/lu-hua7/picture/raw/master/d202681e99c94e67ff50c557320fbce.png)

#### （2）try-except-else

![5df1344be8941e979af4eeee8c9b184](https://gitee.com/lu-hua7/picture/raw/master/5df1344be8941e979af4eeee8c9b184.png)

![3933fb450390f55559a355084412ac7](https://gitee.com/lu-hua7/picture/raw/master/3933fb450390f55559a355084412ac7.png)

#### （3）try-except-finally

![a51b7561a8757f2ddd0df2dc943d2f7](https://gitee.com/lu-hua7/picture/raw/master/a51b7561a8757f2ddd0df2dc943d2f7.png)

无论异常是否发生，都会执行finally，类似with上下文管理器

![c20a7973e7904ae1e0fa97fc1a5660a](https://gitee.com/lu-hua7/picture/raw/master/c20a7973e7904ae1e0fa97fc1a5660a.png)

![747bb415bf655707683bd3d5177f700](https://gitee.com/lu-hua7/picture/raw/master/747bb415bf655707683bd3d5177f700.png)

### 3.异常的嵌套

![cad74aa67129b1ea307d81bffd1f6a4](https://gitee.com/lu-hua7/picture/raw/master/cad74aa67129b1ea307d81bffd1f6a4.png)

### 4.raise语句

可以对存在异常作原因说明，但不能是不存在异常

![78f35be99dced8d6cc7888c261c59e9](https://gitee.com/lu-hua7/picture/raw/master/78f35be99dced8d6cc7888c261c59e9.png)

### 5.assert语句

也是主动引发异常，但只能引发AssertionError异常，用于代码调试

![4d7e4cfa9ea6cc10f9d851173cc0d6f](https://gitee.com/lu-hua7/picture/raw/master/4d7e4cfa9ea6cc10f9d851173cc0d6f.png)

### 6.用异常实现goto

![d3273a4ead7590a4be91fba9ff4c9b9](https://gitee.com/lu-hua7/picture/raw/master/d3273a4ead7590a4be91fba9ff4c9b9.png)