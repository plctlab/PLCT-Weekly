# PLCT 开源进展·第 74 期·2025 年 9 月汇总

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

1. Authored/Co-authored JDK-mainline PRs:
- https://github.com/openjdk/jdk/pull/26495 (8364150: RISC-V: Leftover for JDK-8343430 removing old trampoline call)

2. Reviewed JDK-mainline PRs:
- https://github.com/openjdk/jdk/pull/26101 (8360000: RISC-V: implement aot)
- https://github.com/openjdk/jdk/pull/26161 (8361504: RISC-V: Make C1 clone intrinsic platform guard more specific)
- https://github.com/openjdk/jdk/pull/26150 (8361449: RISC-V: Code cleanup for native call)
- https://github.com/openjdk/jdk/pull/26178 (8361532: RISC-V: Several vector tests fail after JDK-8354383)
- https://github.com/openjdk/jdk/pull/26238 ([TESTBUG] RISC-V: compiler/vectorization/runner/BasicIntOpTest.java fails with RVV but not Zvbb)
- https://github.com/openjdk/jdk/pull/26239 (8361836: RISC-V: Relax min vector length to 32-bit for short vectors)
- https://github.com/openjdk/jdk/pull/26328 (8362284: RISC-V: cleanup NativeMovRegMem)
- https://github.com/openjdk/jdk/pull/26370 (8362515: RISC-V: cleanup NativeFarCall)
- https://github.com/openjdk/jdk/pull/26318 (8362838: RISC-V: Incorrect matching rule leading to improper oop instruction encoding)
- https://github.com/openjdk/jdk/pull/26408 (8357694: RISC-V: Several IR verification tests fail when vlen=128)
- https://github.com/openjdk/jdk/pull/26409 (8362596: RISC-V: Improve _vectorizedHashCode intrinsic)
- https://github.com/openjdk/jdk/pull/26437 (8363898: RISC-V: TestRangeCheckHoistingScaledIV.java fails after JDK-8355293 when running without RVV)
- https://github.com/openjdk/jdk/pull/26481 (8364120: RISC-V: unify the usage of MacroAssembler::instruction_size)
- https://github.com/openjdk/jdk/pull/26719 (8365200: RISC-V: compiler/loopopts/superword/TestGeneralizedReductions.java fails with Zvbb and vlen=128)
- https://github.com/openjdk/jdk/pull/26738 (8365302: RISC-V: compiler/loopopts/superword/TestAlignVector.java fails when vlen=128)
- https://github.com/openjdk/jdk/pull/17413 (8322174: RISC-V: C2 VectorizedHashCode RVV Version)

## Go

## OpenCV

## GNU Toolchain

## LLVM Team
- 1. Upstream llvm-project 合并的patch:
  - [RISC-V] Add P-ext MC Support for Remaining Pair Operations  https://github.com/llvm/llvm-project/pull/159247
  - [VectorCombine] Support pattern bitop(bitcast(x), C) -> bitcast(bitop(x, InvC)): https://github.com/llvm/llvm-project/pull/155216 
  - [FuncSpec] Invalidate analysis by setting MadeChanges explicitly: https://github.com/llvm/llvm-project/pull/155833
  - [X86] Fold vpmadd52h/l for pattern X * 0 + Y --> Y: https://github.com/llvm/llvm-project/pull/156086
  - [X86] Fold X * Y + Z --> C + Z for vpmadd52l/vpmadd52h: https://github.com/llvm/llvm-project/pull/156293
  - [llvm-reduce] Treat CallBrInst as Branch: https://github.com/llvm/llvm-project/pull/156366
  - [X86] Compute the known bits for VPMADD52L/VPMADD52H in SimplifyDemandedBitsForTargetNode: https://github.com/llvm/llvm-project/pull/156847
  - [VectorCombine] Relax vector type constraint on bitop(bitcast, bitcast): https://github.com/llvm/llvm-project/pull/157245
  - [VectorCombine] Relax vector type constraint on bitop(bitcast, constant): https://github.com/llvm/llvm-project/pull/157246
  - [InstCombine] Preserve nneg in foldLogicCastConstant: https://github.com/llvm/llvm-project/pull/157865
  - [RISCV] Extend zvqdot matching to handle disjoint or: https://github.com/llvm/llvm-project/pull/157901
  - [VectorCombine] Add Ext and Trunc support in foldBitOpOfCastConstant: https://github.com/llvm/llvm-project/pull/157822
  - [X86] Handle undef/zero/ones cases after modifying Ops and Masks: https://github.com/llvm/llvm-project/pull/158428
  - [X86] Fold X * 1 + Z --> X + Z for VPMADD52L: https://github.com/llvm/llvm-project/pull/158516
  - [AArch64] Unfold adds when eliminating frame index with scalable offset: https://github.com/llvm/llvm-project/pull/158597
  - [AArch64] Fold uaddv(a) to a if the all lanes except the 0th are zeros: https://github.com/llvm/llvm-project/pull/159086
  - [RISCV] Disable slideup optimization on the inconsistent element type of EVec and ContainerVT: https://github.com/llvm/llvm-project/pull/159373
  - [Docs][RISCV]Remove experimental from Smctr, Ssctr,Sdext and Sdtrig https://github.com/llvm/llvm-project/pull/161058

- 2. plctlab llvm-project合并的patch:
  - fix bitrev C intrinsic test error https://github.com/plctlab/llvm-project/pull/75

- 3. ruyisdk llvm-project合并的patch:
  - [LLVM][XTHeadVector] fix vwcvt, vwcvtu https://github.com/ruyisdk/llvm-project/pull/163

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

- [doxygen: align code for kenerl object doc][rtt-10662]
- [utest/utest: intergare testcases into utest framework ][rtt-10665]
- [doxygen: updated doc for thread management subsystem][rtt-10666]
- [doxygen: fixed duplicated comments for cpu APIs][rtt-10674]
- [doxygen: fixed duplicated comments for scheduler APIs][rtt-10677]
- [doxygen: update doc for env to latest][rtt-10683]
- [utest: unify utest name][rtt-10698]
- [bsp/qemu-virt64-riscv: disable RT_USING_UTEST][rtt-10721]
- [bsp/cvitek: Increase the value of RT_NAME_MAX][rtt-10740]
- [utest: remove RT_UTEST_USING_ALL_CASES][rtt-10741]
- [utest: move core utest cases to under src/utest][rtt-10742]
- [utest: move driver related case under to drivers][rtt-10750]
- [doxygen: fixed build warning for RT_CAN_FILTER_ITEM_INIT][rtt-10758]
- [doxygen: cleanup code for group_object_management][rtt-10759]
- [doxygen: cleanup code for group_thread_management][rtt-10760]
- [bsp: k230: add rtc driver][rtt-10709]

技术文章：
- [[K230学习笔记 01] RTC](https://www.cnblogs.com/Ze-Hou/p/19115269)

[rtt-10662]:https://github.com/RT-Thread/rt-thread/pull/10662
[rtt-10665]:https://github.com/RT-Thread/rt-thread/pull/10665
[rtt-10666]:https://github.com/RT-Thread/rt-thread/pull/10666
[rtt-10674]:https://github.com/RT-Thread/rt-thread/pull/10674
[rtt-10677]:https://github.com/RT-Thread/rt-thread/pull/10677
[rtt-10683]:https://github.com/RT-Thread/rt-thread/pull/10683
[rtt-10698]:https://github.com/RT-Thread/rt-thread/pull/10698
[rtt-10721]:https://github.com/RT-Thread/rt-thread/pull/10721
[rtt-10740]:https://github.com/RT-Thread/rt-thread/pull/10740
[rtt-10741]:https://github.com/RT-Thread/rt-thread/pull/10741
[rtt-10742]:https://github.com/RT-Thread/rt-thread/pull/10742
[rtt-10750]:https://github.com/RT-Thread/rt-thread/pull/10750
[rtt-10758]:https://github.com/RT-Thread/rt-thread/pull/10758
[rtt-10759]:https://github.com/RT-Thread/rt-thread/pull/10759
[rtt-10760]:https://github.com/RT-Thread/rt-thread/pull/10760
[rtt-10709]:https://github.com/RT-Thread/rt-thread/pull/10709

## PLCT罗云翔测试团队

## SG2042/SG2044 Upstream

- [[PATCH] dts: sophgo: sg2042: added numa id description][lk-sg2042-1]
- [[PATCH v2 0/7] Add PCIe support to Sophgo SG2042 SoC][lk-sg2042-2]
- [[PATCH v3 0/7] Add PCIe support to Sophgo SG2042 SoC][lk-sg2042-3]
- [[PATCH v2 0/4] Add SPI NOR DTS node for SG2042 SoC and boards using it][lk-sg2042-4]
- [[PATCH v3 0/3] irqchip/sg2042-msi: Set irq type according to DT configuration][lk-sg2042-5]

[lk-sg2042-1]:https://lore.kernel.org/linux-riscv/20250910105531.519897-1-rabenda.cn@gmail.com/
[lk-sg2042-2]:https://lore.kernel.org/linux-riscv/cover.1757467895.git.unicorn_wang@outlook.com/
[lk-sg2042-3]:https://lore.kernel.org/linux-riscv/cover.1757643388.git.unicorn_wang@outlook.com/
[lk-sg2042-4]:https://lore.kernel.org/linux-riscv/20250916-sfg-spidts-v2-0-b5d9024fe1c8@gmail.com/
[lk-sg2042-5]:https://lore.kernel.org/linux-riscv/cover.1756953919.git.unicorn_wang@outlook.com/

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
