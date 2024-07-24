#  Python学习Day11（2024.07.24）

> 笔者学习笔记依据B站UP主***鱼C-小甲鱼***，学习视频为：[【Python教程】《零基础入门学习Python》最新版]([序章_哔哩哔哩_bilibili](https://www.bilibili.com/video/BV1c4411e77t?p=1&vd_source=3052c1e7ab8ae1ae3bd0668a229fc4b7))
>
> 本次学习章节为P84-P86

## 一、模块和包

### 1.模块

![648a414cb1652de4425bb90b29e3df3](https://gitee.com/lu-hua7/picture/raw/master/648a414cb1652de4425bb90b29e3df3.png)

![1b111f951d3ebdb541252dd100387eb](https://gitee.com/lu-hua7/picture/raw/master/1b111f951d3ebdb541252dd100387eb.png)

可以直接导包，然后使用其中的方法

![29c8d028cc25ffbddacc7af4d8e74a8](https://gitee.com/lu-hua7/picture/raw/master/29c8d028cc25ffbddacc7af4d8e74a8.png)

也可以具体写明使用那个方法

![83eb6f13a53797fe26e3e19b6b25d84](https://gitee.com/lu-hua7/picture/raw/master/83eb6f13a53797fe26e3e19b6b25d84.png)

或者可以加星号表示导入所有方法

![d1804e5764d56844c64b85f9a39772e](https://gitee.com/lu-hua7/picture/raw/master/d1804e5764d56844c64b85f9a39772e.png)

使用from import要注意名字冲突的问题，较迟导入的方法会覆盖同名较早导入的方法

![8817e862c6f520e31a03318673412a3](https://gitee.com/lu-hua7/picture/raw/master/8817e862c6f520e31a03318673412a3.png)

![7fa8b86aa8b7b0a5220c2dcf43c5601](https://gitee.com/lu-hua7/picture/raw/master/7fa8b86aa8b7b0a5220c2dcf43c5601.png)

![c692d8f2daa7ceba6ef0908c399fcea](https://gitee.com/lu-hua7/picture/raw/master/c692d8f2daa7ceba6ef0908c399fcea.png)

可以使用from as来关联，这样在使用时加上前缀便不会被覆盖

![7345978b2b425f26917cafb67920c26](https://gitee.com/lu-hua7/picture/raw/master/7345978b2b425f26917cafb67920c26.png)

![7df55c9048355e8ba795b3d9745ee8c](https://gitee.com/lu-hua7/picture/raw/master/7df55c9048355e8ba795b3d9745ee8c.png)

通过下图运行代码发现，tc文件中的测试语句也被执行了

这是需要通过if \_\_name\_\_ == "\_\_main\_\_" 因为只有当tc作为脚本执行时才会\_\_name\_\_ == "\_\_main\_\_"

这样就可以避免其他程序执行其测试语句

![d6c0f03ef50c71fcea245b74a91659d](https://gitee.com/lu-hua7/picture/raw/master/d6c0f03ef50c71fcea245b74a91659d.png)

![e288dc63f42a00bdf1955cd9f410954](https://gitee.com/lu-hua7/picture/raw/master/e288dc63f42a00bdf1955cd9f410954.png)

![518b1ca4737eae555f7b079506d10a1](https://gitee.com/lu-hua7/picture/raw/master/518b1ca4737eae555f7b079506d10a1.png)

![a94b51a5bb306101436d56699c2b0b5](https://gitee.com/lu-hua7/picture/raw/master/a94b51a5bb306101436d56699c2b0b5.png)

作为模块导入时，\_\_name\_\_ 就变成tc而非 "\_\_main\_\_" 

![e4916f9fff1c66de0a24b067cbd3787](https://gitee.com/lu-hua7/picture/raw/master/e4916f9fff1c66de0a24b067cbd3787.png)

### 2.包

![700c91dafcfe512b228af778e6b0c3f](https://gitee.com/lu-hua7/picture/raw/master/700c91dafcfe512b228af778e6b0c3f.png)

![80c4f7c04d9c5e5654d844a2e89b608](https://gitee.com/lu-hua7/picture/raw/master/80c4f7c04d9c5e5654d844a2e89b608.png)

![e0e38b718175075005cef4dd2f3ac4f](https://gitee.com/lu-hua7/picture/raw/master/e0e38b718175075005cef4dd2f3ac4f.png)

![26b6ac04cf44a44df879de01e0e742f](https://gitee.com/lu-hua7/picture/raw/master/26b6ac04cf44a44df879de01e0e742f.png)

tc和构造函数模块处于一个包下，这样tc文件不能直接导入构造函数模块，它是看不到这个包的

![37584ae4be4a4eb5341f57d19c29fae](https://gitee.com/lu-hua7/picture/raw/master/37584ae4be4a4eb5341f57d19c29fae.png)

![02cf43f93445bbfc5707ebfdf9937e9](https://gitee.com/lu-hua7/picture/raw/master/02cf43f93445bbfc5707ebfdf9937e9.png)

![10d80abfcd673dedb554362cb8fe727](https://gitee.com/lu-hua7/picture/raw/master/10d80abfcd673dedb554362cb8fe727.png)

![e377a8c4dd48cc8db4a9dfd1d1125ab](https://gitee.com/lu-hua7/picture/raw/master/e377a8c4dd48cc8db4a9dfd1d1125ab.png)

![e786ddd079c6904b7b2bbdab0af2cd2](https://gitee.com/lu-hua7/picture/raw/master/e786ddd079c6904b7b2bbdab0af2cd2.png)

![6130585180d0e67c18e31ae54ac83e6](https://gitee.com/lu-hua7/picture/raw/master/6130585180d0e67c18e31ae54ac83e6.png)

也可以在调用构造函数时，让其调用包中的模块

![92d7b39666a7974aba44325391d76c6](https://gitee.com/lu-hua7/picture/raw/master/92d7b39666a7974aba44325391d76c6.png)

![289cb52021b96f36dbc86800c46291f](https://gitee.com/lu-hua7/picture/raw/master/289cb52021b96f36dbc86800c46291f.png)

![c90b7938a179ed3784cc472104b20a5](https://gitee.com/lu-hua7/picture/raw/master/c90b7938a179ed3784cc472104b20a5.png)

### 3.\_\_all\_\_属性的作用

#### （1）遏制from ... import * 的附加伤害

在模块中使用\_\_all\_\_属性就可以指定from ... import * 所能导入的内容

![83da323c5cec0232502adf7b51bad62](https://gitee.com/lu-hua7/picture/raw/master/83da323c5cec0232502adf7b51bad62.png)

![b09459a1f32d7c26b7efc150ba0ecd6](https://gitee.com/lu-hua7/picture/raw/master/b09459a1f32d7c26b7efc150ba0ecd6.png)

![946ac0fe34d4b1e183b61a9022fd947](https://gitee.com/lu-hua7/picture/raw/master/946ac0fe34d4b1e183b61a9022fd947.png)

或者直接使用from as

![6372831d3bf30630cd7ffd9e75d1b83](https://gitee.com/lu-hua7/picture/raw/master/6372831d3bf30630cd7ffd9e75d1b83.png)

![724db75cf64a870dc99ea0fdab74cb5](https://gitee.com/lu-hua7/picture/raw/master/724db75cf64a870dc99ea0fdab74cb5.png)

#### （2）作用于包

默认情况下，使用from ... import *导入一个包，是无法直接访问其包含的模块的

![58e80619c0d2d43b2450e12152607db](https://gitee.com/lu-hua7/picture/raw/master/58e80619c0d2d43b2450e12152607db.png)

![bdbf206efc808948cc5a55c2ec7ada5](https://gitee.com/lu-hua7/picture/raw/master/bdbf206efc808948cc5a55c2ec7ada5.png)

![f65abd92da517f7fa3563f9c557caf3](https://gitee.com/lu-hua7/picture/raw/master/f65abd92da517f7fa3563f9c557caf3.png)

![193f2a16a095bf3fb5f709fa8cb2c6c](https://gitee.com/lu-hua7/picture/raw/master/193f2a16a095bf3fb5f709fa8cb2c6c.png)

![b663d730d03db30d5592b33311dcb82](https://gitee.com/lu-hua7/picture/raw/master/b663d730d03db30d5592b33311dcb82.png)

![73a082083ceace619bfdfe003ab17b6](https://gitee.com/lu-hua7/picture/raw/master/73a082083ceace619bfdfe003ab17b6.png)

![ecdba6ecbe653ac0cdfa3830adec26b](https://gitee.com/lu-hua7/picture/raw/master/ecdba6ecbe653ac0cdfa3830adec26b.png)

### 4.如何将程序发布到PyPI

![d3cc1a648d57240ee5a65f62a8ab842](https://gitee.com/lu-hua7/picture/raw/master/d3cc1a648d57240ee5a65f62a8ab842.png)

![da537877a54b6a721a388acc0b85ff4](https://gitee.com/lu-hua7/picture/raw/master/da537877a54b6a721a388acc0b85ff4.png)

许可证

![bafa6b0b7f1f4dcbac89545b40a4bae](https://gitee.com/lu-hua7/picture/raw/master/bafa6b0b7f1f4dcbac89545b40a4bae.png)

项目配置

![c4d52aeb2415bdb1d014af26cffaebc](https://gitee.com/lu-hua7/picture/raw/master/c4d52aeb2415bdb1d014af26cffaebc.png)

![a0cfa23fb5c1373ec132813c62b7990](https://gitee.com/lu-hua7/picture/raw/master/a0cfa23fb5c1373ec132813c62b7990.png)

![34ada93dc0a3f20bcaaf5a5a0839fd1](https://gitee.com/lu-hua7/picture/raw/master/34ada93dc0a3f20bcaaf5a5a0839fd1.png)

![e2796e1129c1c89bc54cbeeacca7b9b](https://gitee.com/lu-hua7/picture/raw/master/e2796e1129c1c89bc54cbeeacca7b9b.png)

![0439a1b0f22789881844070fc372e7b](https://gitee.com/lu-hua7/picture/raw/master/0439a1b0f22789881844070fc372e7b.png)

![ce77806c9cec883cbd86f8d2a620782](https://gitee.com/lu-hua7/picture/raw/master/ce77806c9cec883cbd86f8d2a620782.png)

![4c179760a0632f9a7394a85f30d1c00](https://gitee.com/lu-hua7/picture/raw/master/4c179760a0632f9a7394a85f30d1c00.png)

![47b819f229664baf15e732bbf4c0f9d](https://gitee.com/lu-hua7/picture/raw/master/47b819f229664baf15e732bbf4c0f9d.png)

![fa072798f34c00bf863046e0c1c58ed](https://gitee.com/lu-hua7/picture/raw/master/fa072798f34c00bf863046e0c1c58ed.png)

![7f0ca4896d6c9d28f7be2116505b3b1](https://gitee.com/lu-hua7/picture/raw/master/7f0ca4896d6c9d28f7be2116505b3b1.png)

![4382e16b855b7a21a812890e5ca6bf6](https://gitee.com/lu-hua7/picture/raw/master/4382e16b855b7a21a812890e5ca6bf6.png)