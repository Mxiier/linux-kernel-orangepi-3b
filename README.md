# 描述
这个内核适用于香橙派3B v1.1硬件版本，当前内核源码版本：`6.11.11`

# 编译方法
在 `Ubuntu 22.04 LTS` 系统上的编译过程

* 克隆这个仓库
```
git clone https://github.com/Mxiier/linux-kernel-orangepi-3b.git
```

* 安装依赖环境
```
sudo apt update
sudo apt install build-essentail bc bison flex libncurses-dev gcc-aarch64-linux-gnu u-boot-tools libssl-dev
```
* 进入源代码目录
```
cd linux-kernel-orangepi-3b
```

* 设置交叉编译环境变量
```
export ARCH=arm64
export SUBARCH=arm64
export CROSS_COMPILE=aarch64-linux-gnu-
export KBUILD_OUTPUT=./out
```

* 设置编译的defconfig配置文件
```
make orangepi-3b_v1.1_defconfig
```

* 开始编译
```
make -j$(nproc --all)
```
编译完成的输出文件将保存到内核源代码目录下的 `out` 目录中。
