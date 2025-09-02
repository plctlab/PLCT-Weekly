# PLCT 开源进展·第 73 期·2025 年 8 月汇总

## 卷首语

## 本期亮点

PLCT实验室的亮点产出通过「RuyiSDK」微信公众号（ID：RuyiSDK）和英文网站提供更新服务：

- https://plctlab.org/en/news/

为了减少冗余工作量，已经在微信公众号推送的中文信息默认不再搬运。

## RuyiSDK IDE

## RuyiSDK 包管理器

## V8 / Chromium

-  优化StackPointerGreaterThanOp指令生成，现在会直接使用branch指令进行判断和跳转  
6862026: [riscv] Optimize StackPointerGreaterThanOp Compare and Branch | https://chromium-review.googlesource.com/c/v8/v8/+/6862026--  合并add/sub; sext.w指令成addw/subw  
6861481: [riscv] Optimize addi and signextend into addiw | https://chromium-review.googlesource.com/c/v8/v8/+/6861481
-  6838685: [riscv][turboshaft] Direct call for known functions | https://chromium-review.googlesource.com/c/v8/v8/+/6838685
-  6808522: [riscv][wasm][jspi][sandbox] Avoid writes to StackMemory from sandboxed code | https://chromium-review.googlesource.com/c/v8/v8/+/6808522
-  6726075: [risc-v] Use sign-extension (via `sext.w`) to replace `slliw` when the shift amount is zero (i.e., `slliw rd, rs, 0`). | https://chromium-review.googlesource.com/c/v8/v8/+/6726075
-  6808523: [riscv][wasm][growable-stacks] Record missing safepoint entry | https://chromium-review.googlesource.com/c/v8/v8/+/6808523

### Review:
- 6760111: [riscv] Implement register constraints for more operations | https://chromium-review.googlesource.com/c/v8/v8/+/6760111
- 6818294: [riscv] Improve ifdef guards. | https://chromium-review.googlesource.com/c/v8/v8/+/6818294
- 6820271: [riscv] Remove broken optimization in i8x16ReplaceLane | https://chromium-review.googlesource.com/c/v8/v8/+/6820271
- 6824703: [riscv] Fix xnor simulator and test. | https://chromium-review.googlesource.com/c/v8/v8/+/6824703
- 6818339: [riscv] Clean up MacroAssembler::StoreReturnAddressAndCall | https://chromium-review.googlesource.com/c/v8/v8/+/6818339
- 6818368: [riscv] Handle indirect pointer slots when recording writes | https://chromium-review.googlesource.com/c/v8/v8/+/6818368
- 6831542: [riscv][maglev] Fix compilation | https://chromium-review.googlesource.com/c/v8/v8/+/6831542
- 6813493: [riscv] Fix alignment of jump table entries in assembler tests | https://chromium-review.googlesource.com/c/v8/v8/+/6813493
- 6842298: [riscv] Allow trampoline blocking to generate code in jump table tests | https://chromium-review.googlesource.com/c/v8/v8/+/6842298
- 6859316: [riscv][liftoff] Block trampoline pool in OOL stack frame setup | https://chromium-review.googlesource.com/c/v8/v8/+/6859316
- 6760071: [riscv] Move forward declarations of Set{Hi20|Lo12}Offset | https://chromium-review.googlesource.com/c/v8/v8/+/6760071
- 6760110: [riscv] Add register constraints | https://chromium-review.googlesource.com/c/v8/v8/+/6760110
- 6760116: [riscv] Avoid temp and unique registers for ExtAddPairwise | https://chromium-review.googlesource.com/c/v8/v8/+/6760116
- 6760117: [riscv] Use register constraints for I8x16Shuffle | https://chromium-review.googlesource.com/c/v8/v8/+/6760117
- 6760118: [riscv] Avoid unnecessary moves | https://chromium-review.googlesource.com/c/v8/v8/+/6760118



## Spidermonkey / Firefox

一般都是风平浪静。欢迎对 Firefox 开发感兴趣的同学来实习。

## OpenJDK
1. Authored/Co-authored JDK-mainline PRs:
- https://github.com/openjdk/jdk/pull/25765 (8359270: C2: alignment check should consider base offset when emitting arraycopy runtime call)
- https://github.com/openjdk/jdk/pull/25696 (8358892: RISC-V: jvm crash when running dacapo sunflow after JDK-8352504)

2. Reviewed JDK-mainline PRs:
- https://github.com/openjdk/jdk/pull/25578 (8358310: ZGC: riscv, ppc ZPlatformAddressOffsetBits may return a too large value)
- https://github.com/openjdk/jdk/pull/25438 (8357695: RISC-V: Move vector intrinsic condition checks into match_rule_supported_vector)
- https://github.com/openjdk/jdk/pull/25412 (8357626: RISCV: Tighten up template interpreter method entry code)
- https://github.com/openjdk/jdk/pull/25502 (8357968: RISC-V: Interpreter volatile reference stores with G1 are not sequentially consistent)
- https://github.com/openjdk/jdk/pull/25520 (8358105: RISC-V: Optimize interpreter profile updates)
- https://github.com/openjdk/jdk/pull/25652 (8358634: RISC-V: Fix several broken documentation web-links)
- https://github.com/openjdk/jdk/pull/25743 (8359218: RISC-V: Only enable CRC32 intrinsic when AvoidUnalignedAccess == false)
- https://github.com/openjdk/jdk/pull/25709 (8359105: RISC-V: No need for acquire fence in safepoint poll during JNI calls)
- https://github.com/openjdk/jdk/pull/25848 (8359801: RISC-V: Simplify Interpreter::profile_taken_branch)
- https://github.com/openjdk/jdk/pull/25923 (8360179: RISC-V: Only enable BigInteger intrinsics when AvoidUnalignedAccess == false)
- https://github.com/openjdk/jdk/pull/25924 (8360169: Problem list CodeInvalidationReasonTest.java on linux-riscv64 until JDK-8360168 is fixed)
- https://github.com/openjdk/jdk/pull/25976 (8360520: RISC-V: C1: Fix primitive array clone intrinsic regression after JDK-8333154)
- https://github.com/openjdk/jdk/pull/26004 (8360707: Globally enumerate all blobs, stubs and entries)

3. Reviewed JDK-21u/17u mainline PRs:
- https://github.com/openjdk/jdk21u-dev/pull/1845 (8358310: ZGC: riscv, ppc ZPlatformAddressOffsetBits may return a too large value)
- https://github.com/openjdk/jdk17u-dev/pull/3678 (8357968: RISC-V: Interpreter volatile reference stores with G1 are not sequentially consistent)

4. Proposed JDK-25u mainline PRs:
- https://github.com/openjdk/jdk25u/pull/4 (8359218: RISC-V: Only enable CRC32 intrinsic when AvoidUnalignedAccess == false)
- https://github.com/openjdk/jdk25u/pull/5 (8360179: RISC-V: Only enable BigInteger intrinsics when AvoidUnalignedAccess == false)
- https://github.com/openjdk/jdk25u/pull/6 (8359270: C2: alignment check should consider base offset when emitting arraycopy runtime call)

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
