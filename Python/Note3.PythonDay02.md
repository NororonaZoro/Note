#  Python学习Day02（2024.06.24）

> 笔者学习笔记依据B站UP主***鱼C-小甲鱼***，学习视频为：[【Python教程】《零基础入门学习Python》最新版]([序章_哔哩哔哩_bilibili](https://www.bilibili.com/video/BV1c4411e77t?p=1&vd_source=3052c1e7ab8ae1ae3bd0668a229fc4b7))
>
> 本次学习章节为P13-P19

（以上记录止于2024.06.25 00:23:41，以下记录始于2024.07.14 10:36:00，***先睡了，明儿还要当牛马***）

## 谋定而后动，知止而有得（P13-P14）

### 流程图

流程图在笔者的理解中，更多是用来理清代码背后的逻辑，从而清楚地知道代码是如何运行的

![686fe9e74010151874477bdf494f9a2](https://gitee.com/lu-hua7/picture/raw/master/686fe9e74010151874477bdf494f9a2.png)

### 思维导图

思维导图是将需求从抽象到具体的映射到代码的工作中去，这样有利于开发者进行代码编写

![bb0d3db4dda3445b7b017a9a3411831](https://gitee.com/lu-hua7/picture/raw/master/bb0d3db4dda3445b7b017a9a3411831.png)

## 了不起的分支与循环（P15-P19）

### 一、分支

针对if，有四种不同的表示方法：最简单的if、if不成立的else、if和elif、if和多重else均不成立的最终else

![43d689a3d0d1b6f084ef837ea5b49a9](https://gitee.com/lu-hua7/picture/raw/master/43d689a3d0d1b6f084ef837ea5b49a9.png)

![ea065c459b42b48f119f54682f6e7c7](https://gitee.com/lu-hua7/picture/raw/master/ea065c459b42b48f119f54682f6e7c7.png)

以下是两种不同形式的ifelse，根据流程图可以清晰看出代码效率不同

![4efc4e1a9fe1ab570a19fd01be4bed8](https://gitee.com/lu-hua7/picture/raw/master/4efc4e1a9fe1ab570a19fd01be4bed8.png)

![41ac96ad4345fcab36d38fc224796d0](https://gitee.com/lu-hua7/picture/raw/master/41ac96ad4345fcab36d38fc224796d0.png)

![5e227466365f8fb10e4bd0552612857](https://gitee.com/lu-hua7/picture/raw/master/5e227466365f8fb10e4bd0552612857.png)

### 二、条件表达式

我们可以看一下以下两段代码，表示的是同一个功能

![68240d3001c6cada8add82370a221cb](https://gitee.com/lu-hua7/picture/raw/master/68240d3001c6cada8add82370a221cb.png)

以下便是条件表达式的格式

![ff8740385d784039df77a799ac2d874](https://gitee.com/lu-hua7/picture/raw/master/ff8740385d784039df77a799ac2d874.png)

所以之前写的代码也可以有很大的改变（当然还是图中上面写法更加简单易懂）

![12563f2ad0b0d03d05294173e77f578](https://gitee.com/lu-hua7/picture/raw/master/12563f2ad0b0d03d05294173e77f578.png)

### 三、分支的嵌套

![5fc279ca345c7e6bc5d44b457640727](https://gitee.com/lu-hua7/picture/raw/master/5fc279ca345c7e6bc5d44b457640727.png)

### 四、循环结构

循环最简单的开始就是while，但是也要注意死循环的产生

![0930f3c5d3ce2d1783ae79cd57f8987](https://gitee.com/lu-hua7/picture/raw/master/0930f3c5d3ce2d1783ae79cd57f8987.png)

为了防止死循环的产生，或者为了结束自己故意写的死循环，要加入break

（视频里的死循环把笔者视频搞得卡死了，这循环真的厉害，给笔者搞红温了）

![2ebd7e3a708b992f23ead59bb135f36](https://gitee.com/lu-hua7/picture/raw/master/2ebd7e3a708b992f23ead59bb135f36.png)

continue是跳过本次循环，但回回到循环的开始进行下一次的判断

![274fb52aead797663a1d5409517e3b3](https://gitee.com/lu-hua7/picture/raw/master/274fb52aead797663a1d5409517e3b3.png)

else语句在循环中，当循环条件***不再***为真的时候，else语句才会被执行

![93023524d491b226899b7e26fbd563d](https://gitee.com/lu-hua7/picture/raw/master/93023524d491b226899b7e26fbd563d.png)

### 五、循环结构的嵌套

![dcef501ca5dd2a77e7e8a4737b5251f](https://gitee.com/lu-hua7/picture/raw/master/dcef501ca5dd2a77e7e8a4737b5251f.png)

![a9cbed679d07c3a75601895394bf13a](https://gitee.com/lu-hua7/picture/raw/master/a9cbed679d07c3a75601895394bf13a.png)

以下图片展示了无论是break还是continue语句，都只能作用于***一层***循环体

![cc2a31dea8dad2468e019affe294214](https://gitee.com/lu-hua7/picture/raw/master/cc2a31dea8dad2468e019affe294214.png)

![dfc253a95a747087cf8a49ffee14078](https://gitee.com/lu-hua7/picture/raw/master/dfc253a95a747087cf8a49ffee14078.png)

### 六、for循环

![5f75612cd205efc86f40368385a1bd8](https://gitee.com/lu-hua7/picture/raw/master/5f75612cd205efc86f40368385a1bd8.png)

![82ef02b22e69adeca853850b86aff69](https://gitee.com/lu-hua7/picture/raw/master/82ef02b22e69adeca853850b86aff69.png)

而像以下例子，100w是一个整数，他无法作为一个迭代对象

![b20f337361d23151a6227540452a91f](https://gitee.com/lu-hua7/picture/raw/master/b20f337361d23151a6227540452a91f.png)

range是for的好兄弟

要注意他是从0开始，***小于***range中的stop

![cb4eca48da47fe406fb6a9f70319703](https://gitee.com/lu-hua7/picture/raw/master/cb4eca48da47fe406fb6a9f70319703.png)

而step控制了他的步进长度

![70556b102d7f9c534af4aec0563b8e8](https://gitee.com/lu-hua7/picture/raw/master/70556b102d7f9c534af4aec0563b8e8.png)

找到10以内的所有素数

![025fa2134ee195b7d545321a80e8a3d](https://gitee.com/lu-hua7/picture/raw/master/025fa2134ee195b7d545321a80e8a3d.png)
