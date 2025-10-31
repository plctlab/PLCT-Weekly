# PLCT 开源进展·第 75 期·2025 年 10 月汇总

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
- https://github.com/openjdk/jdk/pull/26139 (8358696: Assert with extreme values for -XX:BciProfileWidth)
- https://github.com/openjdk/jdk/pull/27512 (8368732: RISC-V: Detect support for misaligned vector access via hwprobe)

2. Reviewed JDK-mainline PRs:
- https://github.com/openjdk/jdk/pull/26658 (8364570: Remove LockingMode related code from riscv64)
- https://github.com/openjdk/jdk/pull/26678 (8365047: Remove exception handler stub code in C2)
- https://github.com/openjdk/jdk/pull/26838 (8365206: RISC-V: compiler/c2/irTests/TestFloat16ScalarOperations.java is failing on riscv64)
- https://github.com/openjdk/jdk/pull/26854 (8365841: RISC-V: Several IR verification tests fail after JDK-8350960 without Zvfh)
- https://github.com/openjdk/jdk/pull/26855 (8365844: RISC-V: TestBadFormat.java fails when running without RVV)
- https://github.com/openjdk/jdk/pull/26883 (8365772: RISC-V: correctly prereserve NaN payload when converting from float to float16 in vector way)
- https://github.com/openjdk/jdk/pull/26935 (8366127: RISC-V: compiler/intrinsics/TestVerifyIntrinsicChecks.java fails when running without RVV)
- https://github.com/openjdk/jdk/pull/26944 (8365926: RISC-V: Performance regression in renaissance (chi-square))
- https://github.com/openjdk/jdk/pull/27047 (8363966: GHA: Switch cross-compiling sysroots to Debian trixie)
- https://github.com/openjdk/jdk/pull/26999 (8364936: Shenandoah: Switch nmethod entry barriers to conc_instruction_and_data_patch)
- https://github.com/openjdk/jdk/pull/26938 (8366747: RISC-V: Improve VerifyMethodHandles for method handle linkers)
- https://github.com/openjdk/jdk/pull/27510 (8368724: RISC-V: Remove AvoidUnalignedAccesses Flag)
- https://github.com/openjdk/jdk/pull/27506 (8368722: RISC-V: Several vector load/store tests fail without support for misaligned vector access)

3. Reviewed JDK-21u/25u mainline PRs:
- https://github.com/openjdk/jdk25u/pull/207 (8365926: RISC-V: Performance regression in renaissance (chi-square))
- https://github.com/openjdk/jdk21u-dev/pull/2121 (8362838: RISC-V: Incorrect matching rule leading to improper oop instruction encoding)

## Go

## OpenCV

## GNU Toolchain

## LLVM Team

## MLIR

### Buddy Compiler

**buddy-mlir**

**buddy-benchmark**

## Box64

## DynamoRIO

## llama.cpp

## coreboot for riscv

本期没有新的进展。

## openocd

本期没有新的进展。

## opensbi

- 通过Zkr初始化stack guard。[1](https://lists.infradead.org/pipermail/opensbi/2025-October/008930.html)
- 添加P8700 aclint支持。[1](https://lists.infradead.org/pipermail/opensbi/2025-October/009005.html)
- RPMI添加电压、设备功率和性能服务。[1](https://lists.infradead.org/pipermail/opensbi/2025-October/008950.html)
- 添加一个unknown nmi的sse event用于在内核发生消息触发panic。[1](https://lists.infradead.org/pipermail/opensbi/2025-October/008954.html)
- 把ariane的代码移动到通用平台。[1](https://lists.infradead.org/pipermail/opensbi/2025-October/008982.html)
- 添加指令模拟（Zba、 Zbb、 Zbc、 Zbs、 Zicbom、 Zicboz、 Zfhmin、 Zicond、 Zimop、 Zcmop、 Zcb、 Zfa、 Zawrs、 Zvbb、 Supm)。[1](https://lists.infradead.org/pipermail/opensbi/2025-October/008992.html)

## u-boot

本期没有新的进展。

## RevyOS (Debian for Xuantie)

### Debian

## RT-Thread

## PLCT罗云翔测试团队

## SG2042/SG2044 Upstream

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
