# PLCT 开源进展·第 73 期·2025 年 8 月汇总

## 卷首语

## 本期亮点

PLCT实验室的亮点产出通过「RuyiSDK」微信公众号（ID：RuyiSDK）和英文网站提供更新服务：

- https://plctlab.org/en/news/

为了减少冗余工作量，已经在微信公众号推送的中文信息默认不再搬运。

## RuyiSDK IDE

## RuyiSDK 包管理器

## V8 / Chromium

## Spidermonkey / Firefox

一般都是风平浪静。欢迎对 Firefox 开发感兴趣的同学来实习。

## OpenJDK

## Go

## OpenCV

## GNU Toolchain
- 添加了GCC的`--with-profiles`支持, 用来指定Profiles配置默认构建参数
  - https://patchwork.sourceware.org/project/gcc/patch/20250826092554.1903027-1-jiawei@iscas.ac.cn/

- 使用`--with-profiles`代替`--with-isa-spec`选项作为工具链构建配置参数，目前正在讨论中
  - https://github.com/riscv-collab/riscv-gnu-toolchain/pull/1760

- 支持了`Zvabd`扩展的Binutils部分
  - https://patchwork.sourceware.org/project/binutils/patch/20250818112925.393341-1-jiawei@iscas.ac.cn/
 
- 修复了`Zilsd/Zclsd`无错误信息提示的问题
  - https://patchwork.sourceware.org/project/binutils/patch/20250812133249.1656395-1-chendongyan@isrc.iscas.ac.cn/

- 提交了`Smmtt`扩展关于`mttp`和`msdcfg`地址分配的提案，正在审核中
  - https://github.com/riscv/riscv-smmtt/pull/189

- 更新了compiler-explorer中的Binutils版本到2.45
  - https://github.com/compiler-explorer/compiler-explorer/pull/8003
 
- 更新了RVP intrinsics文档中关于数据类型的定义，目前采用SIMD数据类型(与ARM一致)，其最终实现标准仍在讨论中，欢迎大家参与
  - https://github.com/pz9115/rvp-intrinsic-doc
  - https://lists.riscv.org/g/tech-p-ext/topic/114558149
 
- 添加了RVP intrinsics的GCC支持框架，修复了Binutils实现中的部分编码问题，对实现细节进行了技术分享,正在补全GCC支持中
  - https://github.com/ruyisdk/riscv-gcc/tree/p-dev
  - https://github.com/ruyisdk/riscv-binutils/tree/p-dev
  - https://docs.google.com/presentation/d/1_3Xii6NoFqyc3tLddEus7xT0JSyc-C-xNFhltcCNCuw/edit?usp=sharing
 
- 更新了Ruyisdk工具链的Release版本，修复了GCC版本号不正确的问题
  - https://github.com/plctlab/riscv-gnu-toolchain/releases/tag/2025.08.02
  - https://github.com/ruyisdk/riscv-gcc/commit/f1eda2ebd2c0a72474950df34ce5433612cc779f

## LLVM Team

## MLIR

### Buddy Compiler

**buddy-mlir**

**buddy-benchmark**

## Box64

## DynamoRIO

## llama.cpp

## coreboot for riscv

## openocd

## opensbi

## u-boot

## RevyOS (Debian for Xuantie)

### Debian

## RT-Thread

- [utest: re-org utest framework (initial version)][rtt-10534]
- [doxygen: fix build error][rtt-10599]
- [bsp:k230:add support for temperature sensor driver][rtt-10609]
- [bsp: k230: increase object name max length to 16][rtt-10612]
- [bsp: k230: Provide a unified interrupt header file][rtt-10615]
- [doxygen: add howto for utest][rtt-10638]
- [bsp:k230:add pdma support for uart driver][rtt-10639]

Articles:
- [[文章] 基于k230 01studio开发板上的rtthread操作系统上的温度传感器驱动移植](https://bbs.elecfans.com/jishu_2499183_1_1.html)

[rtt-10534]:https://github.com/RT-Thread/rt-thread/pull/10534
[rtt-10599]:https://github.com/RT-Thread/rt-thread/pull/10599
[rtt-10609]:https://github.com/RT-Thread/rt-thread/pull/10609
[rtt-10612]:https://github.com/RT-Thread/rt-thread/pull/10612
[rtt-10615]:https://github.com/RT-Thread/rt-thread/pull/10615
[rtt-10638]:https://github.com/RT-Thread/rt-thread/pull/10638
[rtt-10639]:https://github.com/RT-Thread/rt-thread/pull/10639

## PLCT罗云翔测试团队

## SG2042/SG2044 Upstream

- [[PATCH 0/4] Add SPI NOR DTS node for SG2042 SoC and boards using it][lk-sg204x-1]
- [[PATCH 0/4] irqchip/sg2042-msi: Set irq type according to DT configuration][lk-sg204x-2]
- [[PATCH v2 0/3] irqchip/sg2042-msi: Set irq type according to DT configuration][lk-sg204x-3]
- [[PATCH 0/5] Add PCIe support to Sophgo SG2042 SoC][lk-sg204x-4]

[lk-sg204x-1]:https://lore.kernel.org/linux-riscv/20250813-sfg-spidts-v1-0-99b7e2be89d9@gmail.com/
[lk-sg204x-2]:https://lore.kernel.org/linux-riscv/cover.1756103516.git.unicorn_wang@outlook.com/
[lk-sg204x-3]:https://lore.kernel.org/linux-riscv/cover.1756169460.git.unicorn_wang@outlook.com/
[lk-sg204x-4]:https://lore.kernel.org/linux-riscv/cover.1756344464.git.unicorn_wang@outlook.com/

## Milk-V Duo Upstream

## TPU-MLIR （甲辰计划 J123）

默认无更新。本项目 RISC-V 支持由实习生提供。

## LuaJIT

默认无更新。本项目 RISC-V 支持由实习生提供。

## gem5

默认无更新。目前无员工或实习生投入，欢迎投递简历继续做 RISC-V 支持。

## Spike

默认无更新。目前无员工或实习生投入，欢迎投递简历继续做 RISC-V 支持。

## QEMU

默认无更新。目前无员工或实习生投入，欢迎投递简历继续做 RISC-V 支持。

## RustSBI 小队

全实习生小队，独立宣传渠道。

## Nixpkgs

默认无更新。目前无员工或实习生投入。

## Fedora

全实习生小队，独立宣传渠道。

## The Aya Theorem Prover

默认无更新。目前无员工或实习生投入。

## Arch Linux

全实习生小队，独立宣传渠道。

## 参考链接

- [PLCT 实验室的开放职位（实习生）](https://github.com/plctlab/weloveinterns/blob/master/open-internships.md)
- [PLCT 开源进展 (PLCT Weekly)](https://github.com/plctlab/PLCT-Weekly)
- [PLCT 公开报告幻灯片（选集）](https://github.com/plctlab/PLCT-Open-Reports)
